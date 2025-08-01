---
title: CI/CD templates
author: MuyangAmigo
description: Learn how to use CI/CD pipeline templates in GitHub, set up pipeline with Azure DevOps, and Jenkins for Teams Application Developers CI/CD templates.
ms.author: surbhigupta
ms.localizationpriority: medium
ms.topic: overview
ms.date: 02/06/2025
---

# Set up CI/CD pipelines

You can set up a Continuous Integration and Continuous Deployment (CI/CD) pipeline for Microsoft Teams apps created with Microsoft 365 Agents Toolkit (previously known as Teams Toolkit). A Teams app CI/CD pipeline consists of three parts:

1. Build the project.

1. Deploy the project to cloud resources.

1. Generate Teams app package.

> [!NOTE]
> To create a pipeline for a Teams app, it's required to prepare the necessary cloud resources, such as Azure Web App, Azure Functions, or Azure Static Web App, and configure the app settings.

To build the project, you must compile the source code and create the required deployment artifacts. There are two methods to deploy the artifacts:

* [Set up CI/CD pipelines](#set-up-cicd-pipelines-with-agents-toolkit-cli) with Microsoft 365 Agents Toolkit CLI(previously known as Teams Toolkit CLI). *[Recommended]*

* [Set up CI/CD pipelines using your own workflow](#set-up-cicd-pipelines-using-your-own-workflow). *[Optional]*

## Set up CI/CD pipelines with Agents Toolkit CLI

> [!NOTE]
> Use Agents Toolkit version 5.6.0 or a later.

You can use [Agents Toolkit command line interface (CLI)](Teams-Toolkit-CLI.md) to set up CI/CD pipeline for your Teams app.

### Prerequisites

| **Item** | **Description** |
| --- | --- |
| Set up required resources for your Teams app, such as Teams app ID, bot ID, and so on. | • Manually extract the resources from the `manifest.json` file under the `appPackage` folder. <br> • Automatically generate to run the `Provision` command in Agents Toolkit. |
| Configure Azure resources |• Manually prepare the resources by examining the bicep files under the `infra` folder. <br> • Automatically prepare the resources using the `Provision` command in Teams Toolkit.|
| Ensure you've a properly configured service principal with appropriate access policies on resources. | The `atk` command-line interface (CLI) supports Azure login through certificate-based authentication or password-based authentication (application secret). You can either [create a service principal with certificate-based authentication](/cli/azure/azure-cli-sp-tutorial-3) and save the generated certificate, `appId` (client ID) and `tenant` (tenant ID) or [create a secret](/entra/identity-platform/howto-create-service-principal-portal) and save the client ID, client secret, and tenant ID of the service principal. <br> :::image type="content" source="../assets/images/toolkit-v2/service-principal.png" alt-text="Screenshot shows the service principal secret."::: <br> For more information about service principal, see: <br> • [Create service principal using Entra portal](/entra/identity-platform/howto-create-service-principal-portal). <br> • [Create service principal using Azure CLI](/cli/azure/azure-cli-sp-tutorial-1?tabs=bash). |

After you've completed the prerequisites, let's set up a pipeline:

* [Set up pipeline with GitHub](#set-up-pipeline-with-github).

* [Set up pipeline with Azure DevOps](#set-up-pipeline-with-azure-devops).

### Set up pipeline with GitHub

To set up the pipeline with GitHub, follow these steps:

1. Open Visual Studio Code.

1. Create a `cd.yml` file in your project under `.github/workflows` folder and add the following code in the file:
   # [Certificate-based authentication](#tab/certificate)
    ```yaml
    on:
      push:
        branches:
          - main
    jobs:
      build:
        runs-on: ubuntu-latest
        env:
          TEAMSAPP_CLI_VERSION: "3.0.4"
          # Add extra environment variables here so that teamsapp cli can use them.
    
        steps:
          - name: "Checkout GitHub Action"
            uses: actions/checkout@v4
    
          - name: Setup Node 20.x
            uses: actions/setup-node@v1
            with:
              node-version: "20.x"
    
          - name: install cli
            run: |
              npm install @microsoft/atk-cli@${{env.TEAMSAPP_CLI_VERSION}}

          - name: Retrieve the secret and decode it to a file
            env:
              CERTIFICATE_BASE64: ${{ secrets.AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64 }}
            run: |
              echo $CERTIFICATE_BASE64 | base64 --decode > cert.pem
    
          - name: Login Azure by service principal
            run: |
              npx atk auth login azure --username ${{vars.AZURE_SERVICE_PRINCIPAL_CLIENT_ID}}  \
              --service-principal true \
              --tenant ${{vars.AZURE_TENANT_ID}} \
              --password cert.pem \
              --interactive false
    
          - name: Deploy to hosting environment
            run: |
              npx atk deploy --ignore-env-file true \
              --interactive false
    
          - name: Package app
            run: |
              npx atk package
    
          - name: upload appPackage
            uses: actions/upload-artifact@v4
            with:
              name: artifact
              path: appPackage/build/appPackage.zip
    ```
   # [Password-based authentication](#tab/secret)
    ```yaml
    on:
      push:
        branches:
          - main
    jobs:
      build:
        runs-on: ubuntu-latest
        env:
          TEAMSAPP_CLI_VERSION: "3.0.4"
          # Add extra environment variables here so that atk cli can use them.
    
        steps:
          - name: "Checkout GitHub Action"
            uses: actions/checkout@v4
    
          - name: Setup Node 20.x
            uses: actions/setup-node@v1
            with:
              node-version: "20.x"
    
          - name: install cli
            run: |
              npm install @microsoft/atk-cli@${{env.TEAMSAPP_CLI_VERSION}}
    
          - name: Login Azure by service principal
            run: |
              npx atk auth login azure --username ${{vars.AZURE_SERVICE_PRINCIPAL_CLIENT_ID}}  \
              --service-principal true \
              --tenant ${{vars.AZURE_TENANT_ID}} \
              --password ${{secrets.AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET }} \
              --interactive false
    
          - name: Deploy to hosting environment
            run: |
              npx atk deploy --ignore-env-file true \
              --interactive false
    
          - name: Package app
            run: |
              npx atk package
    
          - name: upload appPackage
            uses: actions/upload-artifact@v4
            with:
              name: artifact
              path: appPackage/build/appPackage.zip
    ```
    
    > [!NOTE]
    > The default pipeline triggers when push events occur on the main branch. You've the option to modify it to suit your specific requirements.

1. Go to GitHub.

1. Update the following variables and secrets you created during the prerequisites:

    * # [Certificate-based authentication](#tab/certificate)
      `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`, `AZURE_TENANT_ID`, and `AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64`. `AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64` is the Base64 string encoded content of the certificate that you've generated.

      :::image type="content" source="../assets/images/toolkit-v2/repo-settings.png" alt-text="Screenshot shows the repo settings.":::

      > [!NOTE]
      > The `AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64` variable must be set as secret.
      > Use the [GitHub environment](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment#environment-variables) for different variable sets.

      # [Password-based authentication](#tab/secret)
      `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`, `AZURE_TENANT_ID`, and `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET`

      :::image type="content" source="../assets/images/toolkit-v2/repo-settings.png" alt-text="Screenshot shows the repo settings.":::

      > [!NOTE]
      > The `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET` variable must be set as secret.
      > Utilize the [GitHub environment](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment#environment-variables) to use different sets of variables.

    * Go to the `m365agents.yml` file. In the `deploy` stage, the values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `BOT_AZURE_APP_SERVICE_RESOURCE_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/teamsappyml.png" alt-text="Screenshot shows the bot Azure app service resource ID in m365agents.yml file.":::

    * Go to the `appPackage/manifest.json` file. The values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `TEAMS_APP_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/manifest.png" alt-text="Screenshot shows the Teams app ID in manifest file.":::

1. In the GitHub, navigate to your repository’s **Settings** and select **Secrets and variables** > **Actions**.

    Update the variable keys that you've gathered for the following variables:

    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`
    * `AZURE_TENANT_ID`
    * `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET` or `AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64`
    * `BOT_AZURE_APP_SERVICE_RESOURCE_ID`
    * `TEAMS_APP_ID`

    Add the variables defined in your repo directly into your yml file, excluding the following three variables:

    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`
    * `AZURE_TENANT_ID`
    * `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET` or `AZURE_SERVICE_PRINCIPAL_CERTIFICATE_BASE64`

      :::image type="content" source="../assets/images/toolkit-v2/modification.png" alt-text="Screenshot shows the modified pipeline yml.":::

1. Run the pipeline.

    Push code to the repo to trigger pipeline.

    > [!NOTE]
    > You don't need to commit env files under env folder to the repo. The env variables required for executing the CI/CD pipeline are already set in the repo variables.

    After the pipeline executes successfully, the log displays that the code is deployed to Azure and the `appPackage` is generated in the artifacts.

    :::image type="content" source="../assets/images/toolkit-v2/artifact.png" alt-text="Screenshot shows the `appPackage` is generated in the artifacts.":::

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI%20ran%20into%20an%20issue%5D%20Set%20up%20pipeline%20with%20GitHub&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Fuse-cicd-template%3Ftabs%3Dcertificate%23set-up-cicd-pipelines-with-agents-toolkit-cli&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Fuse-CICD-template.md&documentVersionIndependentId=d56615f7-9333-d20c-8c83-0effb602995a&author=surbhigupta&platformId=396c4625-cebb-e1bc-08b1-86720a7b0620&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B**msteams**)

### Set up pipeline with Azure DevOps

To set up the pipeline with Azure DevOps, follow these steps:

1. Open Visual Studio Code.

1. Create a `cd.yml` file in your project and add the following code in the file:

    # [Certificate-based authentication](#tab/certificate)
    ```yaml
    trigger:
      - main
    
    pool:
      vmImage: ubuntu-latest
    
    variables:
      TEAMSAPP_CLI_VERSION: 3.0.4
    
    steps:
      - task: NodeTool@0
        inputs:
          versionSpec: "20"
          checkLatest: true
    
      - script: |
          npm install @microsoft/atk-cli@$(TEAMSAPP_CLI_VERSION)
        displayName: "Install CLI"

      - task: DownloadSecureFile@1  
        name: certFile  
        displayName: 'Download Certificate File'  
        inputs:  
          secureFile: 'azure_sp_cert.pem' 
    
      - script: |
          npx atk auth login azure --username $(AZURE_SERVICE_PRINCIPAL_CLIENT_ID) --service-principal true --tenant $(AZURE_TENANT_ID) --password $(certFile.secureFilePath) --interactive false
        displayName: "Login Azure by service principal"
    
      - script: |
          npx atk deploy --ignore-env-file true --interactive false
        displayName: "Deploy to Azure"
        workingDirectory: $(System.DefaultWorkingDirectory)
    
      - script: |
          npx atk package
        displayName: "Package app"
        workingDirectory: $(System.DefaultWorkingDirectory)
    
      - publish: $(System.DefaultWorkingDirectory)/appPackage/build/appPackage.zip
        artifact: artifact
    ```

    # [Password-based authentication](#tab/secret)
    ```yaml
    trigger:
      - main
    
    pool:
      vmImage: ubuntu-latest
    
    variables:
      TEAMSAPP_CLI_VERSION: 3.0.4
    
    steps:
      - task: NodeTool@0
        inputs:
          versionSpec: "20"
          checkLatest: true
    
      - script: |
          npm install @microsoft/atk-cli@$(TEAMSAPP_CLI_VERSION)
        displayName: "Install CLI"
    
      - script: |
          npx atk auth login azure --username $(AZURE_SERVICE_PRINCIPAL_CLIENT_ID) --service-principal true --tenant $(AZURE_TENANT_ID) --password $(AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET) --interactive false
        displayName: "Login Azure by service principal"
    
      - script: |
          npx atk deploy --ignore-env-file true --interactive false
        displayName: "Deploy to Azure"
        workingDirectory: $(System.DefaultWorkingDirectory)
    
      - script: |
          npx atk package
        displayName: "Package app"
        workingDirectory: $(System.DefaultWorkingDirectory)
    
      - publish: $(System.DefaultWorkingDirectory)/appPackage/build/appPackage.zip
        artifact: artifact
    ```

    > [!NOTE]
    > The default pipeline triggers when push events occur on the main branch. You can modify it to meet your specific requirements.

1. Push the code to the repo.

1. Setup Azure pipeline.

    After you push your code to the repo, navigate to **Pipelines** and select **New pipeline**. Select your repo and the existing yml file to configure your pipeline.

1. # [Certificate-based authentication](#tab/certificate)
   Update the following variables and set the certificate that you've created during the prerequisites:
    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`, `AZURE_TENANT_ID`

    * Go to the `m365agents.yml` file. In the `deploy` stage, the values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `BOT_AZURE_APP_SERVICE_RESOURCE_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/teamsappyml.png" alt-text="Screenshot shows the bot Azure app service resource ID in m365agents.yml file.":::

    * Go to the `appPackage/manifest.json` file. The values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `TEAMS_APP_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/manifest.png" alt-text="Screenshot shows the Teams app ID in manifest file.":::

    You need to set the following key name variables in the repo:

    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`
    * `AZURE_TENANT_ID`
    * `BOT_AZURE_APP_SERVICE_RESOURCE_ID`
    * `TEAMS_APP_ID`

    To set variables in your pipeline, go to your pipeline and select **Edit** > **Variables**.

    In your Azure DevOps project, navigate to **Pipelines** > **Library** and add a new secure file. Upload the certificate (.pem) file and name the file as `azure_sp_cert.pem`.

   # [Password-based authentication](#tab/secret)
   Update the following variables and secrets that you've created during the prerequisites:
    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`, `AZURE_TENANT_ID`, and `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET`

    * Go to the `m365agents.yml` file. In the `deploy` stage, the values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `BOT_AZURE_APP_SERVICE_RESOURCE_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/teamsappyml.png" alt-text="Screenshot shows the bot Azure app service resource ID in m365agents.yml file.":::

    * Go to the `appPackage/manifest.json` file. The values enclosed in `${{}}` are the required variable keys. If you've used the `provision` command from Agents Toolkit, you can locate the values in the environment files in the `.env` folder.

      Set the `TEAMS_APP_ID` as a repository variable:

      :::image type="content" source="../assets/images/toolkit-v2/manifest.png" alt-text="Screenshot shows the Teams app ID in manifest file.":::

    You need to set the following key name variables in the repo:

    * `AZURE_SERVICE_PRINCIPAL_CLIENT_ID`
    * `AZURE_TENANT_ID`
    * `AZURE_SERVICE_PRINCIPAL_CLIENT_SECRET`
    * `BOT_AZURE_APP_SERVICE_RESOURCE_ID`
    * `TEAMS_APP_ID`

    To set variables in your pipeline, go to your pipeline and select **Edit** > **Variables**.

    > [!NOTE]
    > For security purposes, select the **Keep this value secret** checkbox if it's necessary.

    :::image type="content" source="../assets/images/toolkit-v2/secret.png" alt-text="Screenshot shows the keep this value secret in new variable page.":::

1. Run the pipeline.

    Push code to the repo to trigger pipeline.

    > [!NOTE]
    > There's no need to commit env files under env/ folder to the repo. The env variables required for executing the CI/CD pipeline are already established in the pipeline variables.

    After the pipeline executes successfully, the log displays that the code is deployed to Azure and the `appPackage` is generated in the artifacts.

    :::image type="content" source="../assets/images/toolkit-v2/published.png" alt-text="Screenshot shows the pipeline runs successfully.":::

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI%20ran%20into%20an%20issue%5D%20Set%20up%20pipeline%20with%20Azure%20DevOps&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Fuse-cicd-template%3Ftabs%3Dcertificate%23set-up-pipeline-with-azure-devops&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Fuse-CICD-template.md&documentVersionIndependentId=d56615f7-9333-d20c-8c83-0effb602995a&author=muyangamigo&platformId=396c4625-cebb-e1bc-08b1-86720a7b0620&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B**msteams**)
## Set up CI/CD pipelines using your own workflow

If Agents Toolkit CLI doesn't meet your pipeline requirements, you can develop a custom deployment process that suits your needs. This section provides guidance on deploying to Azure with custom methods.

> [!NOTE]
> If you already have a complete CI/CD pipeline for deploying to your Azure resource, and your Teams app needs to read environment variables during runtime, configure these environment variables in the settings of your Azure resource. For post-deployment testing, see [generate Teams app package](#generate-teams-app-package).

The `atk deploy` command executes the actions defined in the `deploy` stage of the `m365agents.yml` file. The `deploy` stage consists of `build` and `deploy` actions. To create a custom deployment method, rewrite these actions based on your specific requirements and preferences.

As an example, a basic bot TypeScript project has the following deploy stage in its `m365agents.yml`:

```yaml
deploy:
  # Run npm command
  - uses: cli/runNpmCommand
    name: install dependencies
    with:
      args: install
  - uses: cli/runNpmCommand
    name: build app
    with:
      args: run build --if-present
  # Deploy your application to Azure App Service using the zip deploy feature.
  # For additional details, refer to this link.
  - uses: azureAppService/zipDeploy
    with:
      # Deploy base folder
      artifactFolder: .
      # Ignore file location, leave blank will ignore nothing
      ignoreFile: .webappignore
      # The resource id of the cloud resource to be deployed to.
      # This key will be generated by arm/deploy action automatically.
      # You can replace it with your existing Azure Resource id
      # or add it to your environment variable file.
      resourceId: ${{BOT_AZURE_APP_SERVICE_RESOURCE_ID}}
```

These actions perform the following tasks:

* Run `npm install` and `npm build` to build the project.
* Deploy code to Azure app service.

You can customize these actions in your CI/CD pipeline. Here's an example that utilizes GitHub's actions:

```yaml
# build
- name: Setup Node 20.x
  uses: actions/setup-node@v1
  with:
    node-version: '20.x'
- name: 'npm install, build'
  run: |
    npm install
    npm run build --if-present

- name: 'zip artifact for deployment'
  run: |
    zip -r deploy.zip . --include 'node_modules/*' 'lib/*' 'web.config'

# deploy
- name: 'Login via Azure CLI'
  uses: azure/login@v1
  with:
    client-id: ${{ vars.CLIENT_ID }}
    tenant-id: ${{ vars.TENANT_ID }}
    subscription-id: ${{ vars.SUBSCRIPTION_ID }}

- name: 'Run Azure webapp deploy action using azure RBAC'
  uses: azure/webapps-deploy@v2
  with:
    app-name: ${{ vars.AZURE_WEBAPP_NAME }}
    package: deploy.zip
```

Agents Toolkit supports Teams app projects, written in various programming languages and designed for hosting on different Azure services. The following actions for building and deploying. Use these actions when setting CI/CD deployment pipelines.

Build:

| Language | GitHub | Azure Pipeline |
|---|---|---|
|JS or TS |[actions/setup-node](https://github.com/actions/setup-node) |[NodeTool@0](/azure/devops/pipelines/tasks/reference/node-tool-v0) |
|C# |[actions/setup-dotnet](https://github.com/actions/setup-dotnet) |[DotNetCoreCLI@2](/azure/devops/pipelines/tasks/reference/dotnet-core-cli-v2) |

Deploy:

| Resource | GitHub | Azure Pipeline |
|---|---|---|
|Azure App Service |[azure/webapps-deploy](https://github.com/Azure/webapps-deploy) |[AzureWebApp@1](/azure/devops/pipelines/tasks/reference/azure-web-app-v1) |
|Azure Functions |[Azure/functions-action](https://github.com/Azure/functions-action) |[AzureFunctionApp@2](/azure/devops/pipelines/tasks/reference/azure-function-app-v2) |
|Azure Static Web Apps |[Azure/static-web-apps-deploy](https://github.com/Azure/static-web-apps-deploy)|[AzureStaticWebApp@0](/azure/devops/pipelines/tasks/reference/azure-static-web-app-v0) |

### Credential needed for login to Azure

When you deploy app code to Azure App Service, Azure Functions, or Azure Container App through CI/CD, you need a service principal for Azure login. You can log in to Azure using a service principal in two ways:

* OpenID Connect (OIDC):

  * For GitHub action, see how to [use the Azure login action with OpenID Connect](/azure/developer/github/connect-from-azure#use-the-azure-login-action-with-openid-connect).

  * For Azure pipeline, see how to [create an Azure Resource Manager service connection that uses workload identity federation](/azure/devops/pipelines/library/connect-to-azure#create-an-azure-resource-manager-service-connection-that-uses-workload-identity-federation).

* Secret: Agents Toolkit CLI supports sign-in using a service principal with a secret. For more information, see how to [create a new client secret](/entra/identity-platform/howto-create-service-principal-portal).

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI%20ran%20into%20an%20issue%5D%20Set%20up%20CI%2FCD%20pipelines%20using%20your%20own%20workflow&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Fuse-cicd-template%3Ftabs%3Dcertificate%23credential-needed-for-login-to-azure&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Fuse-CICD-template.md&documentVersionIndependentId=d56615f7-9333-d20c-8c83-0effb602995a&author=muyangamigo&platformId=396c4625-cebb-e1bc-08b1-86720a7b0620&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B**msteams**)

## Generate Teams app package

To publish your Teams app, the `appPackage` is required. You can automatically create the `appPackage.zip` using the `atk package` command in `atk` CLI. If you're unable to use `atk` CLI, follow these steps to manually create the `appPackage`:

1. Prepare a `appPackage` folder.
1. Place the `manifest.json` file in the `appPackage` folder. The default `manifest.json` file in Agents Toolkit project contains placeholders, denoted by ${{}}. Replace these placeholders with the correct values.
1. Place your app icons in the `appPackage` folder. To prepare your app icon, see [app icons](../concepts/build-and-test/apps-package.md#app-icons).
1. Zip the files in the `appPackage` folder.

## See also

* [Quick Start for GitHub Actions](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow)
* [Create your first Azure DevOps Pipeline](/azure/devops/pipelines/create-first-pipeline)
* [Create your first Jenkins Pipeline](https://www.jenkins.io/doc/pipeline/tour/hello-world/)
* [Manage your apps with the Developer Portal for Microsoft Teams](../concepts/build-and-test/teams-developer-portal.md)
