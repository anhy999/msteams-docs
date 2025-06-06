## Deploy your app to Azure

Deployment consists of two steps. First, Azure creates necessary cloud resources (also known as provisioning). Then, Azure copies your app's code into the created cloud resources. For this tutorial, you'll deploy the bot app.
<br>
<br>
<details>
<summary>What's the difference between Provision and Deploy?</summary>
<br>
The <b>Provision</b> step creates resources in Azure and Microsoft 365 for your app, but doesn't copy code (HTML, CSS, or JavaScript) to the resources. The <b>Deploy</b> step copies the code for your app to the resources you created during the provision step. It's common to deploy multiple times without provisioning new resources. Since the provision step can take some time to complete, it's separate from the deployment step.
</details>
<br>

# [Visual Studio Code](#tab/vscode)

Select the Microsoft 365 Agents Toolkit :::image type="icon" source="~/assets/images/toolkit-v2/toolkit-sidebar-icon.png"::: icon in the Visual Studio Code sidebar.

1. Select **Provision**.

   :::image type="content" source="~/assets/images/toolkit-v2/provisioning-commands.png" alt-text="Screenshot shows the selection of provision in the cloud under Agents toolkit.":::

1. Select a subscription to use for the Azure resources.

    :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/select-resource.png" alt-text="Screenshot shows the subscription to use for the Azure resources.":::

   Your app is hosted using Azure resources.

    A dialog warns you that costs may be incurred when running resources in Azure.

1. Select **Provision**.

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/provision-warning.png" alt-text="Screenshot shows a dialog box that costs may be incurred when running resources in Azure.":::

   The provisioning process creates resources in the Azure cloud. It may take some time. You can monitor the progress by watching the dialogs in the bottom-right corner. After a few minutes, you see the following notice:

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/deploy-provision-successmsgext.png" alt-text="Screenshot shows a notice, which displays hellomsg successfully provisioned in the cloud.":::

    If you want, you can view the provisioned resources. For this tutorial, you don't need to view resources.

    The provisioned resource appears in the **ENVIRONMENT** section.

    :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/provisioned-resources-env.png" alt-text="Screenshot shows the resource being provisioned in the environment section.":::

1. Select **Deploy** from the **LIFECYCLE** panel after provisioning is complete.

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/deploy-cloud.png" alt-text="Screenshot shows deploy to cloud highlighted in red.":::

   As with provisioning, deployment takes some time. You can monitor the process by watching the dialogs in the bottom-right corner. After a few minutes, you see a completion notice.

Now, you can use the same process to deploy your Bot and Message Extension apps to Azure.

# [Command Line](#tab/cli)

In your terminal window:

1. Run `atk provision`.

   ``` bash
   atk provision
   ```

   When prompted, select an Azure subscription to use Azure resources.

   Your app is hosted using Azure resources.

1. Run `atk deploy`.

   ``` bash
   atk deploy
   ```

---

## Run the deployed app

Once the provisioning and deployment steps are complete:

1. Open the debug panel (**Ctrl+Shift+D** / **⌘⇧-D** or **View > Run**) from Visual Studio Code.
1. Select **Launch Remote (Edge)** from the launch configuration dropdown.
1. Select the **Start debugging (F5)**. You're prompted to upload the custom bot app to Teams.

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/launch-remote.png" alt-text="Screenshot shows the debug and launch app remotely.":::

1. Select **Add**.

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/add-mex-app.png" alt-text="Screenshot of the app details dialog to add the app to Teams.":::

1. Select **Open** to open the app in personal scope.

   Alternatively, you can either search and select the required scope or select a channel, chat, or meeting from the list, and move through the dialog to select **Go**.

   :::image type="content" source="~/assets/images/toolkit-v2/deploy-azure/add-scope.png" alt-text="Screenshot of the scope selection dialog with the list of shared scopes.":::

   You successfully added your bot app to the Teams client.

    :::image type="content" source="~/assets/images/toolkit-v2/first-bot/bot-app-learn-local-debug.png" alt-text="Screenshot shows the learn card in the bot on Teams client.":::  
