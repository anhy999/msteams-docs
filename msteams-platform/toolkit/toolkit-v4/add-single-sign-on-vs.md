---
title: Enable SSO for Teams App
author: surbhigupta
description: In this module, learn how to add single sign-on (SSO) of Microsoft 365 Agents Toolkit, enable SSO support, update your application to use SSO.
ms.author: surbhigupta
ms.localizationpriority: medium
ms.topic: overview
ms.date: 05/20/2022
---

# Add single sign-on to your Teams app

Microsoft Teams provides single sign-on (SSO) function for an app to obtain signed in Teams user token to access Microsoft Graph and other APIs. Microsoft 365 Agents Toolkit (previously known as Teams Toolkit) facilitates the interaction by abstracting some of the Microsoft Entra ID flows and integrations behind some simple APIs. This enables you to add SSO features easily to your Teams app.

## Enable SSO in Agents Toolkit for Visual Studio

Teams provides SSO function for an app using Agents Toolkit for Microsoft Visual Studio.

1. Open **Visual Studio**.

1. Select **Project** > **Microsoft 365 Agents Toolkit** > **Add Authentication Code**.

    :::image type="content" source="../../assets/images/toolkit-v2/toolkit-vs/vs-add-authentication-code.PNG" alt-text="Screenshot shows the option to add authentication code.":::

Agents Toolkit helps you generate the authentication files in **TeamsFx-Auth** folder, including the app manifest (previously called Teams app manifest) template file for Microsoft Entra application and authentication redirect pages. Link the files to your Teams application by updating authentication configurations to ensure the SSO works for your application.

* In the Microsoft Entra app manifest file, specify the URIs (Uniform Resource Identifier) such as, the URI to identify the Microsoft Entra authentication app and the redirect URI for returning token.
* In the app manifest file, add the SSO application to link it with Teams application.
* Add SSO application information in Agents Toolkit configuration files in order to make sure the authentication app can be registered on backend service and start Agents Toolkit when you're debugging or previewing Teams application.

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI+ran+into+an+issue%5D+Enable+single+sign-on+in+Agents+Toolkit+for+Visual+Studio&&author=%40surbhigupta&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs%23enable-single-sign-on-in-agents-toolkit-for-visual-studio&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs.md&documentVersionIndependentId=f5590168-8c16-04cb-4c56-a7d76ea7d935&platformId=42e04429-d075-6f28-28fa-ae0f0380ff5f&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B%2A%2Amsteams%2A%2A)

## Teams tab application

1. Update Microsoft Entra app manifest:
`TeamsFx-Auth/aad.manifest.template.json` file is a Microsoft Entra app manifest template. You can copy and paste this file to any folder of your project, and rename as `aad.manifest.json` and take note of the path to this file. The following updates in the template to create/update a Microsoft Entra app for SSO:

    * `identifierUris`: It's used to uniquely identify and access the resource. Set the correct redirect URIs into `identifierUris` to successfully identify this app. For more information, see [identifierUris attribute](/azure/active-directory/develop/reference-app-manifest#identifieruris-attribute).

        ```json
            "identifierUris":[
              "api://${{TAB_DOMAIN}}/${{AAD_APP_CLIENT_ID}}"
            ]
        ```

    * `redirectUris`: It lists registered redirect_uri values that Microsoft Entra ID accepts as destinations when returning tokens. Set necessary redirect URIs into `redirectUris` to successfully return token. For more information, see [redirectUris attribute](/entra/identity-platform/reference-microsoft-graph-app-manifest#web-attribute).

        ```json
            "web": {
            "redirectUris": [
             "${{TAB_ENDPOINT}}/auth-end.html"
            ]
            }
        ```

        > [!NOTE]
        > Use `${{ENV_NAME}}` to reference variables in `env/.env.{TEAMSFX_ENV}`.

        ```json
            "web": {
             "redirectUris": [
              "${{TAB_ENDPOINT}}/auth-end.html"
             ]
            },
            "spa": {
             "redirectUris": [
              "${{TAB_ENDPOINT}}/auth-end.html?clientId=${{AAD_APP_CLIENT_ID}}",
              "${{TAB_ENDPOINT}}/blank-auth-end.html"
             ]
            }
        ```

    * "name": It replaces the value with your expected Microsoft Entra app name.

1. Open your app manifest file, add `WebApplicationInfo` property with the value of your SSO app. For more information, see [webApplicationInfo](../../resources/schema/manifest-schema.md#webapplicationinfo).

    ```JSON
        "webApplicationInfo": {
          "id": "${{AAD_APP_CLIENT_ID}}",
          "resource": "SAME_AS_YOUR_IDENTIFIERURIS"
        }
    ```

      > [!NOTE]
      > Update the value of resource to your `identifierUris` configed in step 1, and use `${{ENV_NAME}}` to reference envs in `env/.env.{TEAMSFX_ENV}`.

1. Open the `appPackage/manifest.json` file, and add the following code:

      ```JSON
      "webApplicationInfo": {
        "id": "${{AAD_APP_CLIENT_ID}}",
        "resource": "api://${{TAB_DOMAIN}}/${{AAD_APP_CLIENT_ID}}"
      }
      ```

1. Update the `m365agents.yml` file and the `m365agents.local.yml` file.

   Add Microsoft Entra related changes and configs into your `yml` files:

    * Add `aadApp/create` under `provision`: Create new Microsoft Entra apps used for SSO. For more information, see [aadApp/create](https://github.com/OfficeDev/TeamsFx/wiki/Available-actions-in-Teams-Toolkit#aadappcreate).

        > [!NOTE]
        > You can add any missing parameters under `writeToEnvironmentFile` directly in your .yml file.

    * Add `aadApp/update` under `provision`: Update your Microsoft Entra app with Microsoft Entra app manifest in step 1. For more information, see [aadApp/update](https://aka.ms/teamsfx-actions/aadapp-update).

    * Update `file/createOrUpdateJsonFile`:
      Add the following environment variables when you debug locally:
        1. ClientId: Microsoft Entra app client ID.
        1. ClientSecret: Microsoft Entra app client secret.
        1. OAuthAuthority: Microsoft Entra app oauth authority.

       For more information, see [file/updateJson](https://github.com/OfficeDev/TeamsFx/wiki/Available-actions-in-Teams-Toolkit#fileupdatejson).

    * In both the `m365agents.yml` file and the `m365agents.local.yml` file add the following code under the `provision` to create Microsoft Entra app.

      ```yml
      - uses: aadApp/create
        with:
          name: "YOUR_AAD_APP_NAME"
          generateClientSecret: true
          signInAudience: "AzureADMyOrg"
        writeToEnvironmentFile:
          clientId: AAD_APP_CLIENT_ID
          clientSecret: SECRET_AAD_APP_CLIENT_SECRET
          objectId: AAD_APP_OBJECT_ID
          tenantId: AAD_APP_TENANT_ID
          authority: AAD_APP_OAUTH_AUTHORITY
          authorityHost: AAD_APP_OAUTH_AUTHORITY_HOST
      ```

      > [!NOTE]
      > Replace the value of "name" with your expected Microsoft Entra app name.

    * Add the following lines under `provision` to configure Microsoft Entra app with Microsoft Entra app template in the step 1.

      ```json
      - uses: aadApp/update
        with:
          manifestPath: "YOUR_PATH_TO_AAD_APP_MANIFEST"
          outputFilePath : ./build/aad.manifest.${{TEAMSFX_ENV}}.json
      ```

      > [!NOTE]
      > Replace the value of `manifestPath` with the relative path of Microsoft Entra app manifest noted in step 1. For example: `./aad.manifest.json`

    In the `m365agents.local.yml` file:
    * Add the following code under `provision` to add Microsoft Entra related configs to local debug service.

        > [!NOTE]
        > If the `file/createOrUpdateJsonFile` section is configured in `m365agents.local.yml`, then you can skip the following step.

         ```json
            - uses: file/createOrUpdateJsonFile
              with:
                target: ./appsettings.Development.json
                appsettings:
                  TeamsFx:
                    Authentication:
                      ClientId: ${{AAD_APP_CLIENT_ID}}
                      ClientSecret: ${{SECRET_AAD_APP_CLIENT_SECRET}}
                      InitiateLoginEndpoint: ${{TAB_ENDPOINT}}/auth-start.html
                      OAuthAuthority: ${{AAD_APP_OAUTH_AUTHORITY}}
         ```

1. Update Infra
   Microsoft Entra related configs need to be configured in your remote service. The following example shows the configs on Azure Webapp.
     1. TeamsFx__Authentication__ClientId: Microsoft Entra app client ID.
     2. TeamsFx__Authentication__ClientSecret: Microsoft Entra app client secret.
     3. TeamsFx__Authentication__OAuthAuthority: Microsoft Entra app oauth authority.
  
   Example for TeamsFx Tab template.

   Open `infra/azure.parameters.json` and add following lines into `parameters`:

    ```json
   "tabAadAppClientId": {
     "value": "${{AAD_APP_CLIENT_ID}}"
   },
   "tabAadAppClientSecret": {
     "value": "${{SECRET_AAD_APP_CLIENT_SECRET}}"
   },
   "tabAadAppOauthAuthorityHost": {
     "value": "${{AAD_APP_OAUTH_AUTHORITY_HOST}}"
   },
   "tabAadAppTenantId": {
     "value": "${{AAD_APP_TENANT_ID}}"
   }
    ```
  
   Open the `infra/azure.bicep` file, find the code:

   ```
   param location string = resourceGroup().location
   ```

   Update the code as:

   ```
   param tabAadAppClientId string
   param tabAadAppOauthAuthorityHost string
   param tabAadAppTenantId string
   @secure()
   param tabAadAppClientSecret string
   ```

   In the `infra/azure.bicep` file, find the code:

   ```
   resource webApp 'Microsoft.Web/sites@2021-02-01' = {
      kind: 'app'
      location: location
      name: webAppName
      properties: {
        serverFarmId: serverfarm.id
        httpsOnly: true
        siteConfig: {
          appSettings: [
            {
              name: 'WEBSITE_RUN_FROM_PACKAGE'
              value: '1'
            }
          ]
          ftpsState: 'FtpsOnly'
        }
      }
    }
   ```

   Update the code as:

   ```
   resource webApp 'Microsoft.Web/sites@2021-02-01' = {
      kind: 'app'
      location: location
      name: webAppName
      properties: {
        serverFarmId: serverfarm.id
        httpsOnly: true
        siteConfig: {
          ftpsState: 'FtpsOnly'
        }
      }
    }

    resource  webAppConfig  'Microsoft.Web/sites/config@2021-02-01' = {
      name: '${webAppName}/appsettings'
      properties: {
        WEBSITE_RUN_FROM_PACKAGE: '1'
        TeamsFx__Authentication__ClientId: tabAadAppClientId
        TeamsFx__Authentication__ClientSecret: tabAadAppClientSecret
        TeamsFx__Authentication__InitiateLoginEndpoint: 'https://${webApp.properties.defaultHostName}/auth-start.html'
        TeamsFx__Authentication__OAuthAuthority: uri(tabAadAppOauthAuthorityHost, tabAadAppTenantId)
      }
    }
   ```

1. Update `appsettings.json` and `appsettings.Development.json` files for Microsoft Entra related configs needs to be configured to your .NET project settings:

    ```json
    TeamsFx: {
          Authentication: {
            ClientId: AAD app client id
            ClientSecret: AAD app client secret,
            InitiateLoginEndpoint: Login Endpoint,
            OAuthAuthority: AAD app oauth authority
          }
        }
    ```

    > [!NOTE]
    > You can use `$ENV_NAME$` to reference envs in local/remote service.

   Example for TeamsFx Tab template.
  
   Open `appsettings.json` and `appsettings.Development.json` files, and update the code:

    ```json
    "TeamsFx": { 
         "Authentication": { 
           "ClientId": "$clientId$", 
           "ClientSecret": "$client-secret$",
           "InitiateLoginEndpoint": "$TAB_ENDPOINT$/auth-start.html",
           "OAuthAuthority": "$oauthAuthority$"
         } 
       }
    ```

1. Your environment is ready and you can update your code to add SSO to your Teams app. You can find samples:
    * TeamsFx SDK: <https://www.nuget.org/packages/Microsoft.TeamsFx/>
    * Sample Code: under `TeamsFx-Auth/Tab`
  
   Example for TeamsFx Tab template.

   * Create `Config.cs` and update the code as:

        ```c
        using Microsoft.TeamsFx.Configuration;
        
             namespace {{YOUR_NAMESPACE}}
             {
                 public class ConfigOptions
                 {
                     public TeamsFxOptions TeamsFx { get; set; }
                 }
                 public class TeamsFxOptions
                 {
                     public AuthenticationOptions Authentication { get; set; }
                 }
             }
        ```

     > [!NOTE]
     > You need to replace `{{YOUR_NAMESPACE}}` with your namespace name.

   * Move the `TeamsFx-Auth/Tab/GetUserProfile.razor` file to `Components/`.
   * Add the `GetUserProfile` component to your razor page, for example:

      ```
      <h1>Hello, World</h1>
      <GetUserProfile />
      ```

    * Open the `Program.cs` file, find the code:

        ```csharp
        builder.Services.AddScoped<MicrosoftTeams>();
        ``````

      and update the code as:

      ```csharp
                var config = builder.Configuration.Get<ConfigOptions>();
                builder.Services.AddTeamsFx(config.TeamsFx.Authentication);
          ```

     > [!NOTE]
     > You need to exclude the sample code under the `TeamsFx-Auth` file to avoid build failure by adding following code into the `.csproj` file:

      ```csharp
          <ItemGroup>
          <Compile Remove="TeamsFx-Auth/**/*" />
          <None Include="TeamsFx-Auth/**/*" />
          <Content Remove="TeamsFx-Auth/Tab/GetUserProfile.razor"/>
        </ItemGroup>
          ```

   * Download `auth-start.html` and `auth-end.html` files from [GitHub Repo](https://github.com/OfficeDev/TeamsFx/tree/dev/templates/csharp/sso-tab/wwwroot) to `{ProjectDirectory}/wwwroot`.

1. To check the SSO app works as expected, run the `Local Debug` in Visual Studio.

1. You can also run the app in cloud by selecting the `Provision in the cloud` and then `Deploy to the cloud`.

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI+ran+into+an+issue%5D+Teams+tab+application&&author=%40surbhigupta&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs%23teams-tab-application&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs.md&documentVersionIndependentId=f5590168-8c16-04cb-4c56-a7d76ea7d935&platformId=42e04429-d075-6f28-28fa-ae0f0380ff5f&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B%2A%2Amsteams%2A%2A)

## Teams bot application

1. Update Microsoft Entra app manifest in the `TeamsFx-Auth/aad.manifest.template.json` file.
1. You can copy the file to any folder of your project, and rename as the `aad.manifest.json` file and note the path to this file for later reference. Make the following updates in the template to create or update a Microsoft Entra app for SSO.

   * `identifierUris`: Used to uniquely identify and access the resource. You need to set correct Redirect URIs into "identifierUris" for successfully identify this app. For more information, see [identifierUris attribute](/azure/active-directory/develop/reference-app-manifest#identifieruris-attribute).

    Example for TeamsFx Bot Template:

    ```
    "identifierUris":[
      "api://botid-${{BOT_ID}}"
    ]
    ```

    > [!NOTE]
    > You can use `${{ENV_NAME}}` to reference variables in the `env/.env.{TEAMSFX_ENV}` file.

   * `redirectUris`: It lists registered redirect_uri values that Microsoft Entra ID accepts as destinations when returning tokens. You need to set necessary Redirect URIs into "redirectUris" for successfully returning token. For more information, see [redirectUris attribute](/entra/identity-platform/reference-microsoft-graph-app-manifest#web-attribute).

    Example:

    ```
    "web": {
     "redirectUris": [
      "https://${{BOT_DOMAIN}}/bot-auth-end.html"
     ]
    }
    ```

   * "name": Replace the value with your expected Microsoft Entra app name.

1. Update app manifest.
  
   * A `WebApplicationInfo` object needs to be added into your app manifest to enable SSO in the Teams app. For more information, see [webApplicationInfo](../../resources/schema/manifest-schema.md#webapplicationinfo).

    For example: open your app manifest template, and append the following object in app manifest:

    ```
    "webApplicationInfo": {
      "id": "${{AAD_APP_CLIENT_ID}}",
      "resource": "SAME_AS_YOUR_IDENTIFIERURIS"
    }
    ```

    > [!NOTE]
    > You need to update the value of resource to your `identifierUris` configured in step 1.i, and use `${{ENV_NAME}}` to reference envs in `env/.env.{TEAMSFX_ENV}`.

    Example for TeamsFx Bot template:

    Open the `appPackage/manifest.json` file, and add the following property in the app manifest file:

    ```
    "webApplicationInfo": {
      "id": "${{AAD_APP_CLIENT_ID}}",
      "resource": "api://botid-${{BOT_ID}}"
    }
    ```

    * You can register your command under `commands` in `commandLists` of your bot:

    ```
    {
      "title": "YOUR_COMMAND_TITLE",
      "description": "YOUR_COMMAND_DESCRIPTION"
    }
    ```

    Example for TeamsFx Bot template:

    ```
    {
      "title": "show",
      "description": "Show user profile using Single Sign On feature"
    }
    ```

    Remember to delete the previous 'helloWorld' command since it isn't used.

    * Also add bot domain to `validDomain`:

    ```
    "validDomains": [
      "${{BOT_DOMAIN}}"
    ]
    ```

1. Update `m365agents.yml` and `m365agents.local.yml` files:
   Microsoft Entra related changes and configs needs to be added into your `yml` files:
    * Add `aadApp/create` under `provision` for creating new Microsoft Entra apps used for SSO. For more information, see [available actions in Agents Toolkit](https://github.com/OfficeDev/TeamsFx/wiki/Available-actions-in-Teams-Toolkit#aadappcreate).

        > [!NOTE]
        > You can add any missing parameters under `writeToEnvironmentFile` directly in your .yml file.

    * Add `aadApp/update` under `provision` for updating your Microsoft Entra app with Microsoft Entra app manifest in step 1. For more information, see [aadApp/update](https://github.com/OfficeDev/TeamsFx/wiki/Available-actions-in-Teams-Toolkit#aadappupdate).

    * Update `file/createOrUpdateJson` File for adding the following environment variables during local debug:
        1. ClientId: Microsoft Entra app client ID.
        1. ClientSecret: Microsoft Entra app client secret.
        1. OAuthAuthority: Microsoft Entra app oauth authority.
      For more information, see [file/updateJson](https://github.com/OfficeDev/TeamsFx/wiki/Available-actions-in-Teams-Toolkit#fileupdatejson).

   Example for TeamsFx Bot template

   In both `m365agents.yml` and `m365agents.local.yml` files:
    * Add the code under `provision` to create Microsoft Entra app.

        > [!NOTE]
        > If the `aadApp/create` section is missing under `provision` in your .yml file, you can copy and paste the required section into it.

    ```yml
    - uses: aadApp/create
         with:
           name: "YOUR_AAD_APP_NAME"
           generateClientSecret: true
           signInAudience: "AzureADMyOrg"
         writeToEnvironmentFile:
             clientId: AAD_APP_CLIENT_ID
             clientSecret: SECRET_AAD_APP_CLIENT_SECRET
             objectId: AAD_APP_OBJECT_ID
             tenantId: AAD_APP_TENANT_ID
             authority: AAD_APP_OAUTH_AUTHORITY
             authorityHost: AAD_APP_OAUTH_AUTHORITY_HOST
    ```

      > [!NOTE]
      > Replace the value of "name" with your expected Microsoft Entra app name.

    * Add the code under `provision` to configure Microsoft Entra app with Microsoft Entra app template in the step 1.

        ```json
        - uses: aadApp/update
                with:
                  manifestPath: "./aad.manifest.json"
                  outputFilePath : ./build/aad.manifest.${{TEAMSFX_ENV}}.json
        ```

      > [!NOTE]
      > Replace the value of "manifestPath" with the relative path of Microsoft Entra app manifest noted in step 1.
            For example, './aad.manifest.json'

   In the `m365agents.local.yml` file:
    * Update `file/createOrUpdateJsonFile` under `provision` to add Microsoft Entra related configs to local debug service.

        > [!NOTE]
        > If the `file/createOrUpdateJsonFile` section is configured in `m365agents.local.yml`, then you can skip the following step.

        ```json
        - uses: file/createOrUpdateJsonFile
                with:
                  target: ../ProjecName/appsettings.Development.json
                  appsettings:
                    BOT_ID: ${{BOT_ID}}
                    BOT_PASSWORD: ${{SECRET_BOT_PASSWORD}}
                    TeamsFx:
                      Authentication:
                        ClientId: ${{AAD_APP_CLIENT_ID}}
                        ClientSecret: ${{SECRET_AAD_APP_CLIENT_SECRET}}
                        OAuthAuthority: ${{AAD_APP_OAUTH_AUTHORITY}}/${{AAD_APP_TENANT_ID}}
                        ApplicationIdUri: api://botid-${{BOT_ID}}
                        Bot:
                          InitiateLoginEndpoint: https://${{BOT_DOMAIN}}/bot-auth-start
        ```

1. Update Infra Microsoft Entra related configs to configure remote service. The following example shows the configs on Azure Webapp.
    1. TeamsFx__Authentication__ClientId: Microsoft Entra app client ID.
    1. TeamsFx__Authentication__ClientSecret: Microsoft Entra app client secret.
    1. TeamsFx__Authentication__OAuthAuthority: Microsoft Entra app oauth authority.
    1. TeamsFx__Authentication__Bot__InitiateLoginEndpoint: Auth start page for Bot.
    1. TeamsFx__Authentication__ApplicationIdUri: Microsoft Entra app identifies URIs.

   Example for TeamsFx Bot template:

   Open the `infra/azure.parameters.json`file, add the code to `parameters`:

   ```
   "m365ClientId": {
     "value": "${{AAD_APP_CLIENT_ID}}"
   },
   "m365ClientSecret": {
     "value": "${{SECRET_AAD_APP_CLIENT_SECRET}}"
   },
   "m365TenantId": {
     "value": "${{AAD_APP_TENANT_ID}}"
   },
   "m365OauthAuthorityHost": {
     "value": "${{AAD_APP_OAUTH_AUTHORITY_HOST}}"
   }
   ```

   Open the `infra/azure.bicep` file and find the code:

   ```
   param location string = resourceGroup().location
   ```

   Update the code as:

   ```
   param location string = resourceGroup().location
   param m365ClientId string
   param m365TenantId string
   param m365OauthAuthorityHost string
   param m365ApplicationIdUri string = 'api://botid-${botAadAppClientId}'
   @secure()
   param m365ClientSecret string
   ```

   Add the code before output:

   ```
   resource webAppSettings 'Microsoft.Web/sites/config@2021-02-01' = {
     name: '${webAppName}/appsettings'
     properties: {
         TeamsFx__Authentication__ClientId: m365ClientId
         TeamsFx__Authentication__ClientSecret: m365ClientSecret
         TeamsFx__Authentication__Bot__InitiateLoginEndpoint: uri('https://${webApp.properties.defaultHostName}', 'bot-auth-start')
         TeamsFx__Authentication__OAuthAuthority: uri(m365OauthAuthorityHost, m365TenantId)
         TeamsFx__Authentication__ApplicationIdUri: m365ApplicationIdUri
         BOT_ID: botAadAppClientId
         BOT_PASSWORD: botAadAppClientSecret
         RUNNING_ON_AZURE: '1'
     }
   }
   ```

   > [!NOTE]
   > If you want add additional configs to your Azure Webapp, add the configs in the webAppSettings.

1. Update the `appsettings.json` file and the `appsettings.Development.json` file for Microsoft Entra related configs that needs to be configured to your .NET project settings:

    ```
    TeamsFx: {
      Authentication: {
        ClientId: AAD app client id
        ClientSecret: AAD app client secret,
        OAuthAuthority: AAD app oauth authority,
        ApplicationIdUri: AAD app identify uri,
        Bot: {
          InitiateLoginEndpoint: Auth start page for Bot
        }
      }
    }
    ```

    > [!NOTE]
    > You can use `$ENV_NAME$` to reference envs in local/remote service.

   Example for TeamsFx Bot template:

   Open `appsettings.json` and `appsettings.Development.json` files, and add the code:

   ```
   "TeamsFx": {
     "Authentication": {
       "ClientId": "$clientId$",
       "ClientSecret": "$client-secret$",
       "OAuthAuthority": "$oauthAuthority$",
       "ApplicationIdUri": "$applicationIdUri$",
       "Bot": {
         "InitiateLoginEndpoint": "$initiateLoginEndpoint$"
       }
     }
   }
   ```

1. Update your code to add SSO to your Teams app.
  
   You can find samples code:

    * TeamsFx SDK: [https://www.nuget.org/packages/Microsoft.TeamsFx/](https://www.nuget.org/packages/Microsoft.TeamsFx/)
    * Sample Code: under `TeamsFx-Auth/Bot`

   Example for TeamsFx Bot template:

   * Open `Config.cs` and add following classes to the namespace:

    ```
    using Microsoft.TeamsFx.Configuration;

    namespace {{YOUR_NAMESPACE}}
    {
        public class TeamsFxOptions
        {
            public AuthenticationOptions Authentication { get; set; }
        }

        public class ConfigOptions
        {
            public string BOT_ID { get; set; }
            public string BOT_PASSWORD { get; set; }
            public TeamsFxOptions TeamsFx { get; set; }
        }
    }
    ```

    > [!NOTE]
    > Replace the `{{YOUR_NAMESPACE}}` property with your namespace name.
  
   * Move `TeamsFx-Auth/Bot/SSO` and `TeamsFx-Auth/Bot/Pages` files to `/`.

     > [!NOTE]
     > Remember to replace `{{YOUR_NAMESPACE}}` with your project namespace.

   * Open the `Program.cs` file, and find the code:

    ```
    builder.Services.AddSingleton<BotFrameworkAuthentication, ConfigurationBotFrameworkAuthentication>();
    ```

      Update the code as:

    ```
    builder.Services.AddRazorPages();

    // Create the Bot Framework Adapter with error handling enabled.                                        
    builder.Services.AddSingleton<IBotFrameworkHttpAdapter, AdapterWithErrorHandler>();

    builder.Services.AddSingleton<IStorage, MemoryStorage>();
    // Create the Conversation state. (Used by the Dialog system itself.)
    builder.Services.AddSingleton<ConversationState>();

    // The Dialog that will be run by the bot.
    builder.Services.AddSingleton<SsoDialog>();

    // Create the bot as a transient. In this case the ASP Controller is expecting an IBot.
    builder.Services.AddTransient<IBot, TeamsSsoBot<SsoDialog>>();

    builder.Services.AddOptions<BotAuthenticationOptions>().Configure(options =>
    {
      options.ClientId = config.TeamsFx.Authentication.ClientId;
      options.ClientSecret = config.TeamsFx.Authentication.ClientSecret;
      options.OAuthAuthority = config.TeamsFx.Authentication.OAuthAuthority;
      options.ApplicationIdUri = config.TeamsFx.Authentication.ApplicationIdUri;
      options.InitiateLoginEndpoint = config.TeamsFx.Authentication.Bot.InitiateLoginEndpoint;
    });
    ```

    Find the code:

    ```
    builder.Services.AddSingleton<HelloWorldCommandHandler>();
    builder.Services.AddSingleton(sp =>
    {
      var options = new ConversationOptions()
      {
        Adapter = sp.GetService<CloudAdapter>(),
        Command = new CommandOptions()
        {
          Commands = new List<ITeamsCommandHandler> { sp.GetService<HelloWorldCommandHandler>() }
        }
      };

      return new ConversationBot(options);
    });
    ```

    Update the code as:

    ```
    builder.Services.AddSingleton(sp =>
    {
      var options = new ConversationOptions()
      {
        Adapter = sp.GetService<CloudAdapter>(),
        Command = new CommandOptions()
        {
          Commands = new List<ITeamsCommandHandler> { }
        }
      };

      return new ConversationBot(options);
    });
    ```

    Find and delete the code:

      ```
      // Create the bot as a transient. In this case the ASP Controller is expecting an IBot.
      builder.Services.AddTransient<IBot, TeamsBot>();
      ```

    Find the code:

      ```
      app.UseEndpoints(endpoints =>
      {
        endpoints.MapControllers();
      });
      ```

      Update the code as:

      ```
      app.UseEndpoints(endpoints =>
      {
        endpoints.MapControllers();
        endpoints.MapRazorPages();
      });
      ```
  
    > [!NOTE]
    > You need to exclude the sample code under `TeamsFx-Auth` to avoid build failure by adding the following code to `.csproj` file:

    ```
    <ItemGroup>
      <Compile Remove="TeamsFx-Auth/**/*" />
      <None Include="TeamsFx-Auth/**/*" />
      <Content Remove="TeamsFx-Auth/Tab/GetUserProfile.razor"/>
    </ItemGroup>
    ```

1. To check if SSO app works as expected, run the `Local Debug` in Visual Studio.

1. You can also run the app in cloud by selecting `Provision in the cloud` and then select `Deploy to the cloud` to update your app.

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI+ran+into+an+issue%5D+Teams+bot+application&&author=%40surbhigupta&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs%23teams-bot-application&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Ftoolkit%2Ftoolkit-v4%2Fadd-single-sign-on-vs.md&documentVersionIndependentId=f5590168-8c16-04cb-4c56-a7d76ea7d935&platformId=42e04429-d075-6f28-28fa-ae0f0380ff5f&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B%2A%2Amsteams%2A%2A)

## See also

* [Microsoft 365 Agents Toolkit Overview](agents-toolkit-fundamentals-vs.md)
* [Prerequisites for creating your Teams app](tools-prerequisites-vs.md)
* [Enable SSO for tab app](~/tabs/how-to/authentication/tab-sso-overview.md)
* [Enable SSO for your bot and message extension](~/bots/how-to/authentication/bot-sso-overview.md)
* [Prepare accounts to build your Teams app](tools-prerequisites-vs.md#accounts-to-build-your-teams-app)
