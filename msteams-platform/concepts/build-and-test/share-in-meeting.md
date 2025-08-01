---
title: Use Share in Meeting for Documents/Apps
description: Learn how to add the share in meeting button, which allows users to share any document or third-party app to the meeting stage.
ms.topic: reference
ms.localizationpriority: medium
keywords: Share in Meeting
ms.date: 10/29/2024
ms.owner: ryanbliss
---
# Share in meeting

Share in meeting allows users to share documents or third-party web apps to the meeting stage. The meeting participants can collaborate and interact with the third-party web apps or edit the documents together.

The following image shows the **Share in meeting** button on the web app:

:::image type="content" source="../../assets/images/share-in-teams-meeting/web-app.png" alt-text="Screenshot shows share in meeting button on the web app.":::

During the meeting, when a user selects the **Share in meeting** button from the third-party web app or document, it launches a deep link to the meeting stage and opens the app as a web view in the meeting stage. The following is the deep link format:

`msteams:/l/meeting-share?deeplinkId={GUID}&fqdn={string}&lm=deeplink&appContext={json encoded app context}`

## Prerequisites

* For the meeting participants to interact with third-party web apps or documents, they must have a meeting extension of the app or document installed in their Teams client. If they don't have meeting extension, Teams prompts participants to install the meeting extension.
* To share the entire app to stage, you must configure `meetingStage` and `meetingSidePanel` as frame contexts in the [app manifest](../../resources/schema/manifest-schema.md). Otherwise, meeting participants might not be able to view the content on stage.

## Enable share in meeting

The following are three different methods to enable share in meeting. You can use one of the methods depending on how much control you want on the **Share in meeting** buttons displayed on your webpage:

# [Method 1](#tab/method-1)

This method is the simplest way to display the share in meeting buttons with minimal customizations. You can customize the button styles, size, and languages.

You can scan your webpage to locate any HTML elements with the class name of type `teams-share-in-meeting-button` and dynamically generate **Share in meeting** buttons in your page.

1. Add the `launcher.js` script on your webpage.

   ```html
   <script async defer src="https://teams.microsoft.com/share/launcher.js"></script>
   ```

2. Add an HTML element on your webpage with the `teams-share-in-meeting-button` in the `class` attribute, the app ID (from manifest) in the `data-app-id` attribute, and the link to share in the `data-href` attribute. You can also include the `data-entity-name` and `data-entity-description` attributes.

   ```html
   <div
     class="teams-share-in-meeting-button"
     data-href="https://<link-to-be-shared>"
     data-app-id="<app-id>"
     data-entity-name="<app-name>"
     data-entity-description="<app-content-description>"
     >
   </div>
   ```

3. Following are the additional attributes to customize Share in meeting button:
   * `data-button-type`: Specifies the background color of the button (`primaryShareInMeeting` or `secondaryShareInMeeting`).
   * `data-button-size`: Specifies the size of the button in pixel.
   * `data-target`: Specifies whether the link opens in the same window, new tab, or a new window.
   * `data-locale`: Specifies the desired user language.

# [Method 2](#tab/method-2)

You can use this method to have some control over which button to render dynamically or when the script is executed. The script only executes when `window.shareToMicrosoftTeams.renderButtons()` is called. You can pass specific HTML elements through the `renderButtons({elements: [], shareInMeetingElements: [shareInMeetingButton])` API. You can customize the button styles, size, and languages.

The `async shareToMicrosoftTeams.renderButtons(options)` API renders all share button that have the class name **teams-share-button** or **teams-share-in-meeting-button** on the page. If an `options (optional)` object is supplied with a list of elements as shown in the following code, those elements are rendered into the **Share** buttons or **Share in meeting** buttons.

```javascript
options (optional): { elements?: HTMLElement[], shareInMeetingElements?: HTMLElement[] }
```

1. Add the `launcher.js` script on your webpage.

   ```html
   <script async defer src="https://teams.microsoft.com/share/launcher.js" onload="onLoadComplete()"></script>
   ```

2. Create an HTML element and specify the required attributes. After the launcher script is fully loaded, ensure that the rendering logic is executed.

   ```javascript
   async function onLoadComplete() {
      const shareInMeetingButton = document.createElement("div");
      shareInMeetingButton.setAttribute("data-app-id", "<app-id>");
      shareInMeetingButton.textContent = "Share Test App"
      shareInMeetingButton.setAttribute("data-href", "<app-content-url>");
      shareInMeetingButton.setAttribute("data-button-type", "secondaryShareInMeeting");
      shareInMeetingButton.setAttribute("data-locale", "fr-CA");
      await window.shareToMicrosoftTeams.renderButtons({elements: [], shareInMeetingElements: [shareInMeetingButton]});
   }  
   ```

# [Method 3](#tab/method-3)

You can use this method to have complete control over how the script is called and when to generate the button using the `window.shareToMicrosoftTeams.shareInMeetingClickHandler` API. You can control how and where the buttons are generated. You only need to attach the `window.shareToMicrosoftTeams.shareInMeetingClickHandler` API to the `onclick` attribute of the button. It can be attached to a link, button, dropdown menu, and so on. You have complete control of how the UI appears.

The `async shareInMeetingClickHandler(content: IShareInMeetingContent)` API creates a callback handler for Share in meeting button, which can be executed by selecting a button or menu.

1. Add the `launcher.js` script on your webpage.

   ```html
   <script async defer src="https://teams.microsoft.com/share/launcher.js" onload="onLoadComplete()"></script>
   ```

2. Create an HTML element and add the `shareToMicrosoftTeams.shareInMeetingClickHandler` to its `onClick` attribute. After the launcher script is fully loaded, ensure that the onclick logic is created.

   ```javascript
   async function onLoadComplete() {
      var customShareInMeetingButton = document.createElement("a");
      customShareInMeetingButton.onclick = window.shareToMicrosoftTeams.shareInMeetingClickHandler({
      url: "<app-content-url>",
      appId: "<app-id>",
      entityName: "<app-entity-name>",
      entityDescription: "<app-content-description>",
      });
   }
   ```

---

The following are the launcher.js definitions:

| Property | HTML attribute | Type | Required | Default | Description |
| -------------- | ---------------------- | --------------------- | ------- |  ------- |---------------------------------------------------------------------- |
| url | `data-href` | String | Yes | NA | URL of the app content to share. |
| appId | `data-app-id` | String | Yes | NA | ID of the app to share. |
| entityName | `data-entity-name` | String | No | NA | App entity name. |
| entityDescription | `data-entity-description` | String | No | NA | Description of app content to share. |
| locale | `data-locale` | String | No | en-US | User preferred language. |
| target | `data-target` | String | No | self | Specifies whether the link opens in the same window, new tab, or new window. |
| buttonType | `data-button-type` | String | No | primaryShareInMeeting | Specifies the button background color: `primaryShareInMeeting` or `secondaryShareInMeeting`. |
| buttonSize | `data-button-size` | String | No | NA | Button size in pixels. |

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI+ran+into+an+issue%5D+Enable+share+in+meeting&&author=%40surbhigupta&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Fconcepts%2Fbuild-and-test%2Fshare-in-meeting%3Ftabs%3Dmethod-1%23enable-share-in-meeting&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Fconcepts%2Fbuild-and-test%2Fshare-in-meeting.md&documentVersionIndependentId=e6fac06a-05f4-569d-cd2f-04648f8c1c23&platformId=52dfe6dc-7b1e-7f4d-4f87-87a07c550114&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B%2A%2Amsteams%2A%2A)

## End user experience on third-party apps

After you enable Share in meeting on third-party apps, you can share the apps to the meeting stage. To access, follow the steps:

If meeting extension is installed:

1. Open the web app in the browser and select **Share in meeting**.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/web-app-share-button.png" alt-text="Screenshot shows share in meeting button on web app."lightbox="../../assets/images/share-in-teams-meeting/web-app.png":::

1. Select **Start sharing**.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/share.png" alt-text="Screenshot shows how to share apps in teams meeting.":::

1. The web app is shared to meeting stage and all the participants can interact and edit together.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/share-stage.png" alt-text="Screenshot shows app shared to the teams meeting stage.":::

If meeting extension isn't installed:

1. Open the web app in the browser and select **Share in meeting**.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/web-app-share-button.png" alt-text="Screenshot shows share in meeting button on web app."lightbox="../../assets/images/share-in-teams-meeting/web-app.png":::

1. To install the meeting extension app, select **Add**.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/meeting-extension-app.png" alt-text="Screenshot shows add button to install meeting extension app.":::

1. Select **Start sharing**.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/share.png" alt-text="Screenshot shows start sharing button to share your app in meeting.":::

1. The web app is shared to meeting stage and all the participants can interact and edit together.

   :::image type="content" source="../../assets/images/share-in-teams-meeting/share-stage.png" alt-text="Screenshot shows app shared to the teams meeting stage experience.":::

> [!div class="nextstepaction"]
> [I ran into an issue](https://github.com/MicrosoftDocs/msteams-docs/issues/new?template=Doc-Feedback.yaml&title=%5BI+ran+into+an+issue%5D+End+user+experience+on+third-party+apps&&author=%40surbhigupta&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fmicrosoftteams%2Fplatform%2Fconcepts%2Fbuild-and-test%2Fshare-in-meeting%3Ftabs%3Dmethod-1%23end-user-experience-on-third-party-apps&contentSourceUrl=https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fmsteams-docs%2Fblob%2Fmain%2Fmsteams-platform%2Fconcepts%2Fbuild-and-test%2Fshare-in-meeting.md&documentVersionIndependentId=e6fac06a-05f4-569d-cd2f-04648f8c1c23&platformId=52dfe6dc-7b1e-7f4d-4f87-87a07c550114&metadata=*%2BID%253A%2Be473e1f3-69f5-bcfa-bcab-54b098b59c80%2B%250A*%2BService%253A%2B%2A%2Amsteams%2A%2A)

## Generate a deep link to share content to stage in meetings

You can also generate a deep link to share the app to stage and start or join a meeting. When a deep link is selected in an app by a user who is part of an ongoing meeting, then the app is shared to the stage and a permission pop-up window appears. Users can grant access to the participants to collaborate with an app.

:::image type="content" source="../../assets/images/integrate-with-teams/screenshot-of-pop-up-permission.png" alt-text="The screenshot is an example that shows a permission pop-up window.":::

When a user isn't in a meeting then the user is redirected to the Teams calendar where they can join a meeting or initiate instant meeting (Meet now).

:::image type="content" source="../../assets/images/integrate-with-teams/Instant-meetnow-pop-up.png" alt-text="The screenshot is an example that shows a pop-up window when there's no ongoing meeting.":::

Once the user initiates an instant meeting (Meet now), they can add participants and interact with the app.

:::image type="content" source="../../assets/images/integrate-with-teams/Screenshot-ofmeet-now-option-pop-up.png" alt-text="The screenshot is an example that shows an option to add participants and how to interact with the app.":::

To add a deep link to share content in meetings, see [deep link to share content to stage in meetings](deep-link-workflow.md#deep-link-to-share-content-to-stage-in-meetings).

> [!NOTE]
> For your app to pass validation, when you create a deep link from your website, web app, or Adaptive Card, use **Share in meeting** as the string or copy.

## Code sample

| **Sample name** | **Description** | **.NET** |**Node.js** | Manifest |
|-----------------|-----------------|----------------|----------------|----------------|
| Meeting Stageview | This sample app demonstrates how to enable and configure applications for Microsoft Teams meetings, allowing users to interact with a shared meeting stage using the Live Share SDK. |[View](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/meetings-stage-view/csharp)|[View](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/meetings-stage-view/nodejs)|[View](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/meetings-stage-view/csharp/demo-manifest)|

## See also

* [Apps for Teams meetings and calls](../../apps-in-teams-meetings/teams-apps-in-meetings.md)
* [Share to Teams from web apps](share-to-teams-from-web-apps.md)
* [Share to Teams from personal app or tab](share-to-teams-from-personal-app-or-tab.md)
* [Create deep links](deep-links.md)
* [Adaptive Cards](../../task-modules-and-cards/cards/cards-reference.md#adaptive-card)
