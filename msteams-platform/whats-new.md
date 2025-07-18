---
title: What's New for Developers in Teams
description: Learn about new Microsoft Teams developer features and updates to existing features, deprecation notes, and changes. Subscribe to the RSS feed for latest updates.
ms.topic: reference
ms.date: 05/29/2025
ms.localizationpriority: high
zone_pivot_groups: What-new-features
---

# What's new for developers in Microsoft Teams

::: zone pivot="ga-feature"

Discover Microsoft Teams platform features that are generally available (GA). You can now get latest Teams platform updates by subscribing to the RSS feed [![download feed](~/assets/images/RSSfeeds.png)](https://aka.ms/TeamsPlatformUpdates). For more information, see [configure RSS feed](#get-latest-updates).

## Microsoft Build 2025 :::image type="icon" source="assets/images/bullhorn.png" border="false"

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
| May 19, 2025 | Branding updates: </br> • Teams Toolkit is now Microsoft 365 Agents Toolkit </br> • Teams App Test Tool is now Microsoft 365 Agents Playground </br> • Teams App CLI, TeamFx CLI, and Teams Toolkit CLI are now Microsoft 365 Agents Toolkit CLI </br> • `teamsapp` CLI signature is now `atk` | [Microsoft 365 Agent Toolkit](/microsoft-365/developer/overview-m365-agents-toolkit?toc=%2Fmicrosoftteams%2Fplatform%2Ftoc.json&bc=%2Fmicrosoftteams%2Fplatform%2Fbreadcrumb%2Ftoc.json) |
| May 19, 2025 | Introducing Microsoft 365 admin center permission to view custom app analytics and the agent usage analytics for custom apps in Developer Portal | Tools and SDKs > Tools > Developer Portal for Teams > [Analyze app and agent usage in Developer Portal](/microsoftteams/platform/concepts/build-and-test/analyze-your-apps-usage-in-developer-portal?tabs=custom-apps-built-for-your-org) |
| May 16, 2025 | Use Meeting AI Insights API to fetch conversation summaries, action items, and mentions directly from Teams meetings | Build apps for Teams meetings and calls > Get meeting transcripts, recordings, and AI summaries > [Get AI-generated meeting summaries](graph-api/meeting-transcripts/meeting-insights.md) |
| May 13, 2025 | Introducing agent usage analytics for third-party apps in Developer Portal | Tools and SDKs > Tools > Developer Portal for Teams > [Analyze app and agent usage in Developer Portal](/microsoftteams/platform/concepts/build-and-test/analyze-your-apps-usage-in-developer-portal?tabs=thirdpartyapps) |

## Generally available

:::row:::
:::column:::

:::image type="icon" source="~/assets/images/general-availabe.png":::

:::column-end:::
:::column span="2":::

Teams platform features that are available to all app developers.</br>
**2025 July**
* ***July 10, 2025***: [Custom icons for Teams notifications help your app stand out and increase engagement through more personalized activity feed updates.](/graph/teams-send-activityfeednotifications#custom-activity-icons-in-activity-feed-notifications)</br>

**2025 May**

* ***May 29, 2025***: [Introducing app manifest v1.22 with support for custom activity icons and prefetch of nested app authentication tokens.](/microsoft-365/extensibility/schema/?view=m365-app-1.22&preserve-view=true)
* ***May 19, 2025***: [Introducing Microsoft 365 admin center permission to view custom app analytics and the agent usage analytics for custom apps in Developer Portal.](/microsoftteams/platform/concepts/build-and-test/analyze-your-apps-usage-in-developer-portal?tabs=custom-apps-built-for-your-org)
* ***May 19, 2025***: </br> Branding updates: </br> • Teams Toolkit is now Microsoft 365 Agents Toolkit. </br> • Teams App Test Tool is now Microsoft 365 Agents Playground. </br> • Teams App CLI, TeamFx CLI, and Teams Toolkit CLI are now Microsoft 365 Agents Toolkit CLI. </br> • `teamsapp` CLI signature is now referred as `atk`.
* ***May 16, 2025***: [Use Meeting AI Insights API to fetch conversation summaries, action items, and mentions directly from Teams meetings.](graph-api/meeting-transcripts/meeting-insights.md)
* ***May 13, 2025***: [Introducing agent usage analytics for third-party apps in Developer Portal](/microsoftteams/platform/concepts/build-and-test/analyze-your-apps-usage-in-developer-portal?tabs=thirdpartyapps).

:::column-end:::
:::row-end:::
<br/>

</br>

<details>

<summary><b>2025</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
| 30/04/2025 | Introducing streaming messages for bot apps. | Build bots and agents > Bot user experience > [Stream bot messages](bots/streaming-ux.md) |
| 21/04/2025 | Precache your tab app to optimize its initial load time. | Build tabs > Tab features > App caching for your tab app > [Debug tool for cached apps](tabs/how-to/app-caching.md#precaching-tab-apps) |
| 21/04/2025 | You can specify a 32x32 color icon with a transparent background to ensure a consistent appearance when your app runs in Outlook and Microsoft 365. | Publish your app or agent > Create Teams app package > [Color icon](concepts/build-and-test/apps-package.md#color-icon) |
| 21/04/2025 | Introducing custom engine agents support for Microsoft 365 Copilot Chat. | Build bots and agents > Teams AI library v1 > Build with Teams AI library > [Add support for Microsoft 365 Copilot Chat](bots/how-to/teams-conversational-ai/how-conversation-ai-get-started.md#add-support-for-microsoft-365-copilot-chat) |
| 10/04/2025 | Create personal scope apps that integrate seamlessly with Public Switched Telephone Network (PSTN) and Teams-to-Teams calls. | Build apps for Teams meetings and calls > [Build tabs for calling](apps-in-teams-meetings/build-tabs-for-calling.md) |
| 03/04/2025 | Enable OAuth authentication for API based message extension. | Add authentication > Enable authentication for API-based message extension > [Enable OAuth for API based message extension](messaging-extensions/api-based-oauth.md) |
| 27/03/2025 | Learn about the best practices to optimize tab app performance in Teams Android and iOS clients. | Resources > [Best practices for Teams mobile apps](resources/teams-mobile-best-practices.md) |
| 07/03/2025 | Introducing app manifest v1.20 with elementRelationshipSet, requirementSet, and intuneInfo properties. | App manifest > [App manifest](resources/schema/manifest-schema.md) |
| 07/03/2025 | Specify runtime requirements in app manifest to tailor your app's behavior in Microsoft 365 hosts. | [Extend your app across Microsoft 365 > Specify Microsoft 365 host runtime requirements in app manifest](m365-apps/specify-runtime-requirements.md) |
| 07/03/2025 | Enable Intune Mobile App Management (MAM) support for Outlook add-ins to ensure compliance with organizational data protection policies. | [Office.Mailbox interface](/javascript/api/outlook/office.mailbox) |
| 27/02/2025 | Create, manage, and customize your app package for declarative agents and other apps directly from Developer Portal. | Tools and SDKs > Tools > Developer Portal for Teams > [Manage your apps in Developer Portal](concepts/build-and-test/manage-your-apps-in-developer-portal.md#configure) |
| 05/02/2025 | Use third-party cloud storage for drag-dropped files in message compose areas.| Integrate with Teams > [Third-party storage app](concepts/device-capabilities/third-party-storage-capability.md) |
| 31/01/2025 | Create a scenario based custom engine agent using Teams Toolkit and Teams AI library. | [Build a custom engine agent using Teams AI library and Teams Toolkit](sbs-Teams-AI.yml) |
| 23/01/2025 | Plan for government and sovereign clouds. | Plan your app > Plan for special clouds > [Plan for government clouds](concepts/cloud-overview.md) |
| 09/01/2025 | Tab app caching is generally available. | Build tabs > Tab features > [App caching for your tab app](tabs/how-to/app-caching.md) |
| 09/01/2025 | AI label, citations, feedback buttons, and sensitivity labels in bot messages are generally available. | Build bots > Bot user experience > [Enhance AI-generated bot messages](bots/how-to/bot-messages-ai-generated-content.md) |

<br/>
</details>

</br>

<details>

<summary><b>2024</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
| 18/12/2024 | Introducing text customization for share to stage button. | Build apps for Teams meetings and calls > Configure apps for Teams meetings > Build apps for meeting stage > [Advanced share to stage APIs](apps-in-teams-meetings/build-apps-for-teams-meeting-stage.md#advanced-share-to-stage-apis) |
| 18/12/2024 | Introducing share to meeting from personal app. | Integrate with Teams > Share to Teams > Share to Teams from personal app or tab > [Share to meeting from personal app](concepts/build-and-test/share-to-teams-from-personal-app-or-tab.md#share-to-meeting-from-personal-app) |
| 16/12/2024 | Introducing multi parameters for API-based message extensions which allows more than one input type for query command. | Build message extensions > Build message extensions using API > Create API-based message extensions > [Multi parameters](messaging-extensions/create-api-message-extension.md#multi-parameters) |
| 13/12/2024 | Learn to extend bot-based message extension as an agent for Microsoft 365 Copilot. | Build message extensions > Build message extensions using Bot Framework > Search commands > [Extend bot-based message extension as agent](messaging-extensions/build-bot-based-agent.md) |
| 11/12/2024 | Enhanced user experience for Teams app installed from Teams Store or custom upload. | Publish your app > [Configure default options for Teams app](concepts/deploy-and-publish/add-default-install-scope.md) |
| 27/11/2024 | Terminology update. **Copilot agent** is referred to as **agent**. |  |
| 19/11/2024 | Terminology update. **Plugin** is referred to as **agent** for Microsoft 365 Copilot. |  |
| 18/11/2024 | Configure default landing capability for your bot or tab app to open your app with the default capability. | Publish your app > [Configure default options for Teams app](concepts/deploy-and-publish/add-default-install-scope.md#configure-your-apps-default-landing-capability) |
| 07/11/2024 | Build responsive Container layouts in Adaptive Cards. | Build cards and dialogs > Build cards > [Container layouts in Adaptive Cards](task-modules-and-cards/container-layouts.md) |
| 07/11/2024 | Visually represent data with charts in Adaptive Cards. | Build cards and dialogs > Build cards > [Charts in Adaptive Cards](task-modules-and-cards/cards/charts-in-adaptive-cards.md) |
| 07/11/2024 | Add conditionally enabled action buttons in Adaptive Cards. | Build cards and dialogs > Build cards > [Card actions](task-modules-and-cards/cards/cards-actions.md#conditional-enablement-of-action-buttons) |
| 07/11/2024 | Media elements in Adaptive Cards. | Build cards and dialogs > Build cards > [Media elements in Adaptive Card](task-modules-and-cards/cards/media-elements-in-adaptive-cards.md) |
| 07/11/2024 | Create engaging Adaptive Cards with borders and rounded corners, scrollable containers, compound button, Icons, and star ratings. | Build cards and dialogs > Build cards > [Borders and rounded corners](task-modules-and-cards/cards/cards-format.md#borders-and-rounded-corners-in-adaptive-cards), [scrollable containers](task-modules-and-cards/cards/cards-format.md#scrollable-containers-in-adaptive-cards), [compound button](task-modules-and-cards/cards/cards-format.md#compound-button-in-adaptive-cards), [Icons](task-modules-and-cards/cards/cards-format.md#icons-in-adaptive-card), and [star ratings](task-modules-and-cards/cards/cards-format.md#ratings-in-adaptive-cards) |
| 07/11/2024 | Build dependent inputs with typeahead search in Adaptive Cards. | Build cards and dialogs > Build cards > [Typeahead search in Adaptive Cards](task-modules-and-cards/cards/dynamic-search.md#dependent-inputs) |
| 07/11/2024 | Use Adaptive Card templates to design visually appealing and actionable Adaptive Cards. | Design your app > UI components > [Adaptive Cards](task-modules-and-cards/cards/design-effective-cards.md#adaptive-card-starter-collection) |
| 29/10/2024 | Share content to live and upcoming meetings with Share to Teams. | Integrate with Teams > Share to Teams > [Share to Teams from web apps](concepts/build-and-test/share-to-teams-from-web-apps.md) |
| 28/10/2024 | Enable API key and SSO authentication for your API-based message extension. | Add authentication > Enable authentication for API-based message extensions > [Overview](messaging-extensions/build-api-based-message-extension.md) |
| 28/10/2024 | Update bot or message extension app to use certificate or MSI for authentication. | Tools and SDKs > Tools > Teams Toolkit for Visual Studio Code > Prepare to build apps using Teams Toolkit > Develop your Teams app > [Use certificate or MSI for app authentication](toolkit/update-bot-me-app-to-use-certificate-or-msi-for-authentication.md) |
| 28/10/2024 | Debug apps in Teams desktop client to improve debugging performance and efficiency. | Tools and SDKs > Tools > Teams Toolkit for Visual Studio Code > Prepare to build apps using Teams Toolkit > Debug your Teams app > [Debug in Teams desktop client](toolkit/debug-apps-in-Teams-desktop-client.md) |
| 25/10/2024 | Introduced prompt suggestions for bots to create an engaging and insightful bot experience. | Build bots > Bot conversations > [Create prompt suggestions](bots/how-to/conversations/prompt-suggestions.md) |
| 17/10/2024 | Introducing app manifest v1.19 with copilotAgents, declarativeAgents, and defaultLanguageFile. | App manifest > [App manifest](/microsoftteams/platform/resources/schema/manifest-schema) |
| 17/10/2024 | Localize your agents. | Microsoft 365 Copilot extensibility > Work with the Copilot ecosystem > Agents are apps for Microsoft 365 > [Localizing your agent](/microsoft-365-copilot/extensibility/agents-are-apps#localizing-your-agent) |
| 17/10/2024 | Build a personal tab with offline functionality. | Build tabs > Create a tab > [Offline tabs](tabs/how-to/create-personal-tab.md#offline-tabs) |
| 13/09/2024 | Use app analytics in Developer Portal to analyze your app usage metrics to gain valuable insights into how users interact with your app. | Tools and SDKs > Tools > Developer Portal for Teams > [Analyze your apps usage in Developer Portal](concepts/build-and-test/analyze-your-apps-usage-in-developer-portal.md) |
| 26/08/2024 | Enhanced user experience for Teams app subscriptions purchased from Teams Store. | Monetize your app > Purchase and manage app subscriptions and licenses > [Subscription purchase experience](concepts/deploy-and-publish/appsource/prepare/end-user-purchase-experience.md#subscription-purchase-experience) |
| 22/08/2024 | Dev Tools for Teams tabs are available in the new Microsoft Teams client. | Test your app > Tabs > [Dev Tools for Microsoft Teams Tab](tabs/how-to/developer-tools.md) |
| 21/08/2024 | Use sample prompts to guide the users for using various plugins within Microsoft 365 Copilot. | Publish your app > Publish to the Teams Store > Review Copilot validation guidelines > [Sample prompts](concepts/deploy-and-publish/appsource/prepare/review-copilot-validation-guidelines.md#sample-prompts) |
| 31/07/2024 | Use app validation tool to validate your Teams app in Developer Portal for Teams. | Tools and SDKs > Tools > Developer Portal for Teams > [Publish](concepts/build-and-test/manage-your-apps-in-developer-portal.md#publish) |
| 03/07/2024 | share content to the meeting Stage simplifies app content sharing during meetings and provides a seamless multi-player viewing experience. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meetings > [Share to stage](apps-in-teams-meetings/build-apps-for-teams-meeting-stage.md#screen-share-content-to-meetings) |
| 26/06/2024 | Introduced AI label, citations, feedback buttons, and sensitivity labels in bot messages. | Build bots > Build conversations > [Bot messages with AI-generated content](bots/how-to/format-ai-bot-messages.md)|
| 26/06/2024 | Debug message extension app in Test Tool. |Tools and SDKs > Teams Toolkit for Visual Studio Code > Prepare to build apps using Teams Toolkit > Debug your Teams app > [Debug message extension app in Test Tool](bots/how-to/format-ai-bot-messages.md)|
| 24/06/2024 | Static tabs are generally available for chats, channels, and meetings. | Build tabs > [Build tabs for Teams](tabs/what-are-tabs.md)|
| 21/05/2024 | Introduced Assistants API to create powerful AI assistants capable of performing a variety of tasks. | Build bots > Teams AI library > [Overview](bots/how-to/teams%20conversational%20ai/teams-conversation-ai-overview.md#assistants-api) |
| 21/05/2024 | Get started with the process of building apps with Teams AI library using the LightBot sample. | Build bots > Teams AI library > [Quick start guide](bots/how-to/teams%20conversational%20ai/conversation-ai-quick-start.md)|
| 21/05/2024 | Introduced a step-by-step guide to build a custom engine agent to chat with your data using Teams AI library and Teams Toolkit. | Build bots > Teams AI library > Build custom engine agent > [Build custom engine agent using Teams Toolkit](teams-ai-library-tutorial.yml)|
| 21/05/2024 | Use Live Share sessions to enable seamless collaboration in Teams meetings, chats, and channels. | Build apps for Teams meetings and calls > Enhanced collaboration with Live Share > [Live Share collaborative contexts](apps-in-teams-meetings/teams-live-share-overview.md#live-share-collaborative-contexts)|
|17/05/2024|Deploy Teams app to container service.|Tools and SDKs > Teams Toolkit for Visual Studio Code > Host your app on Azure > [Deploy Teams app to container service](toolkit/deploy-Teams-app-to-container-service.md)|
|12/04/2024|Implement authentication in API-based search message extensions to provide secure and seamless access to your app.|Build message extensions > Build message extensions using API > [Authentication](messaging-extensions/build-api-based-message-extension.md)|
|12/04/2024|Introducing app manifest v1.17 with semanticDescription, samplePrompts, and dashboardCards.|[App manifest](resources/schema/manifest-schema.md)|
|12/04/2024|Outlook extensions specifies Outlook Add-ins within an app manifest and simplify the distribution and acquisition across the Microsoft 365 ecosystem.|App manifest > [extensions.requirements](resources/schema/manifest-schema.md#extensionsrequirements)|
|12/04/2024|Create Dashboardcards that can be pinned to a dashboard such as Microsoft Viva Connections to provide a summarized view of app information|App manifest > [dashboardCards](resources/schema/manifest-schema.md#dashboardcards)|
|12/04/2024|Share code snippets as richly formatted Adaptive Cards in Teams chats, channels, and meetings with the CodeBlock element.|Build cards and dialogs > [CodeBlock in Adaptive Cards](task-modules-and-cards/cards/cards-format.md#codeblock-in-adaptive-cards)|
|12/04/2024|Introduced bot configuration experience that helps you to enable the bot settings for users to configure their bot during installation and reconfigure the bot.|Build bots > [Bot configuration experience](bots/how-to/bot-configuration-experience.md)|
|10/04/2024|Define and deploy Outlook Add-ins in version 1.17 and later of the app manifest schema.|Extend your app across Microsoft 365 > [Outlook Add-ins](m365-apps/overview.md#outlook-add-ins)|
|04/04/2024|Added support for python in Teams AI library.|Build bots > Teams AI library > [Teams AI library](bots/how-to/teams-conversational-ai/teams-conversation-ai-overview.md)|
|04/04/2024|Stageview API with the openmode property allows you to open your app content in different Stageview experience.|Build tabs > [Open content in Stageview](tabs/open-content-in-stageview.md)|
|03/04/2024|Updated the common reasons for app validation failure to help your app pass the Teams Store submission process.|Publish your app > Publish to the Teams Store > [Common reasons for app validation failure](concepts/deploy-and-publish/appsource/common-reasons-for-app-validation-failure.md)|
|27/03/2024|Configure Teams deep links using the msteams:// and https:// protocol handlers.|Integrate with Teams > Create deep links > Overview > [Protocol handlers in deep links](concepts/build-and-test/deep-links.md#protocol-handlers-in-deep-links)|
|26/03/2024|Adaptive Cards responsive layout helps you to design cards to look great on any device in order to provide an enhanced user experience across chat, channels, and meeting chat.|Build cards and dialogs > Build cards > Format cards in Microsoft Teams > [Adaptive Card responsive layout](task-modules-and-cards/cards/cards-format.md#adaptive-card-responsive-layout)|
|07/03/2024|Introduced Adaptive Card Previewer to view the realtime changes for Visual Studio 2022.|Tools and SDKs > Tools > [Adaptive Card Previewer for Visual Studio](concepts/build-and-test/adaptive-card-previewer-vs.md)|
|07/03/2024|Introduced Teams App Test Tool that streamlines the debug process of bot-based apps for Visual Studio 2022.|Tools and SDKs > Tools > Teams Toolkit for Visual Studio > Prepare to build apps using Teams Toolkit > Debug your Teams app > [Debug bot using Teams App Test Tool](toolkit/toolkit-v4/debug-your-agents-playground-vs.md)|
|28/02/2024|Extend a Teams meeting app to work with Outlook.|Extend your app across Microsoft 365 > [Extend a Teams meeting app to Outlook](m365-apps/extend-m365-meeting-app.md)|
|28/02/2024|Design Teams app lightbox view to emphasize important information.|Design your app > UI components > [Lightbox view](concepts/design/design-teams-app-light-box-view.md)|
|15/02/2024|Share to Teams from personal app or tab for mobile clients.|Integrate with Teams > Share to Teams > [Share to Teams from personal app or tab](concepts/build-and-test/share-to-teams-from-personal-app-or-tab.md)|
|01/02/2024|Use Adaptive Card-based Loop components to build collaborative experiences within Teams message extensions that work across Microsoft 365.|Extend your app across Microsoft 365 > [Adaptive Card-based Loop components](m365-apps/cards-loop-component.md)|
|01/02/2024|Use application RSC permissions for chat scope.|Utilize Teams data with Microsoft Graph > Resource-specific consent > [RSC permissions for a chat or meeting](graph-api/rsc/resource-specific-consent.md#rsc-permissions-for-a-chat-or-meeting)|
|25/01/2024|Use Micro-capability templates to show rich unfurl previews of your links without installing your app in Microsoft Teams.|Build message extension > Build message extensions using Bot Framework > [Micro-capabilities for website links](messaging-extensions/how-to/micro-capabilities-for-website-links.md)|
|24/01/2024|Introduced advanced step-by-step guide to learn how to debug your AI chat bot using Teams App Test Tool.|[Debug your AI chat bot using Teams App Test Tool](sbs-teams-app-test-tool.yml)|
|19/01/2024|Use / to invoke message extensions from command box in the new Teams client.|Build message extension > [Build message extensions using Bot Framework](messaging-extensions/build-bot-based-message-extension.md)|
|04/01/2024|Apps for Teams meetings are available in Department of Defense (DoD) environment.|[Build apps for Teams meetings and calls](apps-in-teams-meetings/teams-apps-in-meetings.md)|

<br/>
</details>

</br>

<details>

<summary><b>2023</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
|20/12/2023|Incoming Webhooks are available in GCC High environment.|[Build webhooks and connectors](~/webhooks-and-connectors/what-are-webhooks-and-connectors.md)|
|20/12/2023|Introduced RSC permissions for users to access different resources.| Utilize Teams data with Microsoft Graph > [Resource-specific consent for your Teams app](graph-api/rsc/resource-specific-consent.md#rsc-permissions-for-user-access) |
|18/12/2023|App caching in chat, channel, and meeting tab scopes is available for iOS.| Build tabs > [App caching for your tab app](tabs/how-to/app-caching.md) |
|15/12/2023|Bots can mention tags in text messages and Adaptive Cards posted in Teams channels.| Build bots > Bot conversation > [Channel and group chat conversations with a bot](bots/how-to/conversations/channel-and-group-conversations.md#tag-mention) |
|12/12/2023|Use Teams AI library to build apps that can leverage LLMs to facilitate more natural conversational interactions with users, guiding that conversation into your apps skills.|Build bots > [Teams AI library](bots/how-to/teams-conversational-ai/teams-conversation-ai-overview.md)|
|21/11/2023|Terminology update. LOB apps is referred to as custom apps built for your org (LOB apps).||
|20/11/2023|Use captureImage API to capture an image or select media from the gallery for mobile clients.|Integrate device capabilities > [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md)|
|17/11/2023|Terminology update. Sideload is referred to as upload a custom app.||
|17/11/2023|Introduced Teams App Test Tool that streamlines the debug process of bot-based apps.|Tools and SDKs > Tools > Teams Toolkit for Visual Studio Code > Prepare to build apps using Teams Toolkit > Debug your Teams app > [Teams app Test Tool](toolkit/debug-your-agents-playground.md) |
|14/11/2023|Use callRecording API to fetch meeting recording from all meetings.|Build apps for Teams meetings and calls > [Get meeting transcripts and recordings using Graph APIs](graph-api/meeting-transcripts/overview-transcripts.md)|
|14/11/2023|Branding update. Azure Active Directory (Azure AD) is referred to as Microsoft Entra ID.||
|03/11/2023|Apps for Teams meetings are available in GCC High environment.|[Build apps for Teams meetings and calls](apps-in-teams-meetings/teams-apps-in-meetings.md)|
|25/10/2023|Configure your bot to receive meeting participant events. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meetings > [Meeting apps APIs](apps-in-teams-meetings/meeting-apps-apis.md#receive-meeting-participant-events)|
|11/10/2023|Introduced the new Microsoft Teams client to provide better experience for your apps and users. | Resources > [Introducing the new Microsoft Teams client](resources/teams-updates.md)|
|05/10/2023|Use callTranscript API to fetch meeting transcript from all meetings.|Build apps for Teams meetings and calls > [Get meeting transcripts and recordings using Graph APIs](graph-api/meeting-transcripts/overview-transcripts.md)|
|05/10/2023|You can rate apps on Microsoft Teams Store and offer feedback on your usage experience.|Publish your app > Publish to the Teams Store > [Maintain your published app](concepts/deploy-and-publish/appsource/post-publish/overview.md#ratings-and-review-for-teams-apps)|
|26/09/2023|Configure your bot with read receipt events to identify if the recipient has read the message sent by the bot.|Build bots > Messages in bot conversations > [Read receipts](bots/how-to/conversations/conversation-messages.md#receive-a-read-receipt)|
|26/09/2023|Use media elements such as audio or video clips to your Adaptive Card for enhanced media experience and user engagement.|Build cards and task modules > Build cards > [Media elements in Adaptive Card](task-modules-and-cards/cards/media-elements-in-adaptive-cards.md)|
| 06/09/2023|Generate a deep link to share content to stage in meetings.|Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Share in meeting](concepts/build-and-test/share-in-meeting.md)|
| 29/08/2023 | Use Microsoft Teams Store with intelligent search experience to display apps that are closest match to the user's specified characters.|Publish your app > [Publish to the Teams Store](concepts/deploy-and-publish/appsource/publish.md#teams-store-search-experience) |
| 28/08/2023 | Teams app manifest is now referred to as app manifest.|App manifest > [Overview](resources/schema/manifest-schema.md)|
| 16/08/2023 | Use Teams Toolkit Visual Studio v17.7 extension with many new app development features to get started with app development for Teams.|Tools and SDKs > Tools > [Teams Toolkit for Visual Studio](toolkit/toolkit-v4/agents-toolkit-fundamentals-vs.md) |
| 10/08/2023 | Send a proactive message using Microsoft Entra ID.|Build bots > Bot conversations > [Proactive messages](bots/how-to/conversations/send-proactive-messages.md)|
| 25/07/2023 | Use Collaborative Stageview to engage with your app content in a new Teams window.|Build tabs > [Tabs link unfurling and Stageview](tabs/tabs-link-unfurling.md#collaborative-stageview).
| 25/07/2023 | Use people icon in an Adaptive Card to view the images of users.|Build cards and task modules > Build cards > Review Teams Store validation guidelines > [Build cards](task-modules-and-cards/cards/cards-format.md#people-icon-in-an-adaptive-card) |
| 20/07/2023 | App caching for iOS personal tray | Build tabs > [App caching for iOS personal tray](tabs/how-to/app-caching.md) |
| 06/07/2023 | Use app icon badging to identify any app activity during a meeting | Build apps for Teams meetings and calls > Build in-meeting notification and app icon badging > [Use app icon badging to identify any app activity during a meeting](apps-in-teams-meetings/app-icon-badging-for-your-app.md) |
| 14/06/2023 | Added validation guidelines for Teams app powered by Artificial Intelligence (AI). | Publish your app > Publish to the Teams Store > Review Teams Store validation guidelines > [Apps powered by Artificial Intelligence](concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines.md#apps-powered-by-artificial-intelligence) |
| 02/06/2023 | Get real-time meeting events for channel meetings. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > Meeting apps APIs > [Get real-time Teams meeting events API](apps-in-teams-meetings/meeting-apps-apis.md#receive-real-time-teams-meeting-events) |
| 25/05/2023 | Use a deep link to open a tab app in meeting side panel in Teams mobile client. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Build tabs for meeting](apps-in-teams-meetings/build-tabs-for-meeting.md#deep-link-to-meeting-side-panel) |
|23/05/2023 |  Live Share SDK is now generally available. Use Live Share to transform Teams apps into collaborative multi-user experiences without writing any dedicated back-end code. | Build apps for Teams meetings and calls > Enhanced collaboration with Live Share > [Live Share SDK](apps-in-teams-meetings/teams-live-share-overview.md)|
|23/05/2023 | Use Teams app design guidelines to help you make quick and right decisions to design your app. | Design your app > [Overview](concepts/design/design-teams-app-overview.md)|
|17/05/2023 | Cater your app to a specific audience from the available list of countries or regions. | Publish your app > Publish to the Teams Store > Prepare your Teams Store submission > [Publish your app to specific countries or regions](concepts/deploy-and-publish/appsource/prepare/submission-checklist.md#publish-your-app-to-specific-countries-or-regions)|
| 17/05/2023 | Use the Teams Toolkit v5 extension with many new app development features to get started with app development for Teams using Visual Studio Code. | Tools and SDKs > Teams Toolkit > [Teams Toolkit Overview](toolkit/agents-toolkit-fundamentals.md)|
| 17/05/2023 | Updated Get started module with GitHub Codespaces and step-by-step guides aligned with Teams Toolkit v5. It also includes details for extending Teams app over Microsoft 365 and Outlook. | [Get started](get-started/get-started-overview.md)|
| 24/04/2023 | Develop your apps with a seamless transition between Teams Developer Portal and Teams Toolkit. | Tools and SDKs > Developer Portal for Teams > [Develop your apps with Teams Toolkit](concepts/build-and-test/develop-your-apps-with-toolkit.md) |
| 14/04/2023 | App update in any one context where the app is installed automatically updates the app in all the related contexts (chats, channels, and meetings). | Publish your app > [Upload your app in Teams](concepts/deploy-and-publish/apps-upload.md#update-your-app) |
| 06/04/2023 | Set up Microsoft license management for third-party SaaS apps in Partner Center as part of the offer publishing that allows easy management and tracking of licenses for third-party app subscriptions within Teams. | Monetize your app > [Set up Microsoft license management](~/concepts/deploy-and-publish/appsource/prepare/manage-third-party-apps-license.md) |
| 04/04/2023 | Tab apps in shared channels are available in Department of Defense (DoD) environment. | Build tabs > [Build apps for shared channels](~/concepts/build-and-test/shared-channels.md) |
| 23/03/2023 | Use apps in Teams meetings scheduled through public channels. | Build apps for Teams meetings and calls > [Overview](apps-in-teams-meetings/teams-apps-in-meetings.md) |
| 20/03/2023 | Bots are available in Department of Defense (DoD) environment. | Build bots > [Overview](bots/what-are-bots.md)|
| 20/03/2023 | Message extensions are available in Department of Defense (DoD) environment. | Build message extensions > [Overview](messaging-extensions/what-are-messaging-extensions.md)|
| 28/02/2023 | Use the resources and best practices to support the rollout of your Teams app in your customers’ organizations and facilitate adoption of your app. | Publish your app > adoption > [Drive customer adoption of your app](promote-app-adoption.md) |
| 27/02/2023 | Use Changelog to view the latest updates on Developer Portal about features, recent changes in APIs, and important bug fixes. | Tools and SDKs > Developer Portal for Teams > [Overview](concepts/build-and-test/teams-developer-portal.md#changelog-for-developer-portal) |
| 23/02/2023 | Enable single sign-on (SSO) authentication to access Adaptive Cards Universal Actions in a bot. | Add authentication > Enable SSO for your Teams app > Enable SSO for Adaptive Cards Universal Actions in your bot > [Overview](task-modules-and-cards/cards/Universal-actions-for-adaptive-cards/enable-sso-for-your-adaptive-cards-universal-action.md) |
|23/02/2023| Enable third party authentication to add user-specific views in instances where an Adaptive Card with Universal Action is shared. | Add authentication > Use third party IdP authentication > [Third party authentication for Adaptive Cards Universal Actions](task-modules-and-cards/cards/Universal-actions-for-adaptive-cards/authentication-flow-in-universal-action-for-adaptive-cards.md) |
|21/02/2023| Send notifications to specific participants on a meeting stage with targeted in-meeting notification. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Targeted in-meeting notification for apps in Teams](apps-in-teams-meetings/in-meeting-notification-for-meeting.md#targeted-in-meeting-notification) |
|20/02/2023| Plan, strategize, and execute your app growth in Teams to make it a successful app on the marketplace. | Grow your app > [Strategize and execute growth for your app](concepts/deploy-and-publish/appsource/post-publish/app-growth/overview-app-growth.md) |
|17/02/2023| Build a dashboard tab app that acts as a tool to track, analyze, monitor, display, and extract data. | Build Tabs > [Build a dashboard tab app](tabs/how-to/build-a-dashboard-tab-app.md#build-a-dashboard-tab-app) |
|09/02/2023| Build apps for anonymous users that support anonymous users to attend Teams meetings with an alternative authentication experience. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Build apps for anonymous users](apps-in-teams-meetings/build-apps-for-anonymous-user.md) |
|31/01/2023| Get update and soft delete activity notification in a bot when you edit, undelete or soft delete a message in a chat. | Build bots > Bot conversations > [Messages in bot conversations](bots/how-to/conversations/conversation-messages.md#get-edit-message-activity) |

</details>
</br>

<details>
<summary><b>2022</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
| 08/12/2022 | Introducing Teams developer documentation FAQs. | [Teams developer documentation FAQs](teams-faq.md) |
| 07/12/2022 | Introducing notification bot in Teams. | Build bots > Bot conversations > [Notification bot in Teams](bots/how-to/conversations/notification-bot-in-teams.md) |
| 07/12/2022 | Introducing command bot in Teams. | Build bots > Bot conversations > [Command bot in Teams](bots/how-to/conversations/command-bot-in-teams.md) |
| 29/11/2022 | Introducing plan analytics for your Teams app. | Plan your app > Plan analytics for your Teams app > [Overview](concepts/design/overview-analytics.md) |
| 23/11/2022 | Updated integrate location capabilities. | Integrate device capabilities > [Integrate location capabilities](concepts/device-capabilities/location-capability.md) |
| 22/11/2022 | Revamped enable SSO for your bot and message extension app. | Add authentication > Enable SSO for your Teams app > Enable SSO for your bot and message extension app > [Overview](bots/how-to/authentication/bot-sso-overview.md) |
| 18/11/2022 | Introducing zero install for link unfurling. | Build message extensions > Add link unfurling > [Zero install for link unfurling](messaging-extensions/how-to/link-unfurling.md#zero-install-for-link-unfurling) |
| 17/11/2022 | Updated Manifest schema v1.15. | App manifest > [Manifest schema v1.15](resources/schema/manifest-schema.md) |
| 16/11/2022 | Introducing Adaptive Cards overflow menu. | Build cards and task modules > Build cards > Format cards in Microsoft Teams > [Adaptive Cards overflow menu](task-modules-and-cards/cards/cards-format.md#adaptive-cards-overflow-menu) |
| 14/11/2022 | Introducing single sign-on for Visual Studio. | Tools and SDKs > Teams Toolkit > Use Teams Toolkit to create your app > Develop your Teams app > [Add single sign-on to your Teams app](toolkit/add-single-sign-on.md) |
| 02/11/2022 | Support global routing for bot APIs. | Build bots > Bot conversations > Proactive messages > [Create the conversation](bots/how-to/conversations/send-proactive-messages.md#create-the-conversation) |
| 10/27/2022 | Introducing Workflow bot for Teams. | Tools and SDKs > Teams Toolkit > Use Teams Toolkit to create your app > Develop your Teams app  > Create multi capability app > [Create Teams workflow bot](sbs-gs-workflow-bot.yml) |
| 10/26/2022 | Build an in-meeting app for enabling meeting participants to sign documents in real time. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meetings > [Build apps for Teams meeting stage](apps-in-teams-meetings/build-apps-for-teams-meeting-stage.md#build-an-in-meeting-document-signing-app) |
| 10/19/2022| Developer Portal for Teams is now available for GCC tenants. | Tools and SDKs > Developer Portal for Teams > [Overview](concepts/build-and-test/teams-developer-portal.md)|
| 10/13/2022| Configure NavBar and create an overflow menu for multiple actions. | Design your app > App capabilities > [Personal apps](concepts/design/personal-apps.md#configure-and-add-multiple-actions-in-navbar)|
| 10/13/2022| Configure back button of an app. | Design your app > App capabilities > [Personal apps](concepts/design/personal-apps.md#configure-back-button)|
| 10/12/2022| Apps are supported in instant meetings, one-on-one, and group calls. | Build apps for Teams meetings and calls > [Overview](apps-in-teams-meetings/teams-apps-in-meetings.md)|
| 10/12/2022| Live Share canvas | Build apps for Teams meetings and calls > Enhanced collaboration with Live Share > [Canvas](apps-in-teams-meetings/teams-live-share-canvas.md)|
| 09/29/2022|Teams mobile app now supports file downloads to local devices.|Integrate device capabilities > Integrate media capabilities > [File download on Teams mobile](concepts/device-capabilities/media-capabilities.md#file-download-on-teams-mobile)|
| 09/16/2022|Adaptive Cards in search based message extensions now support Universal Actions.|Build message extensions > Search commands > [Universal Actions for search based message extensions](messaging-extensions/how-to/search-commands/universal-actions-for-search-based-message-extensions.md)|
| 09/06/2022|Introduced code snippets for capturing videos using camera through `selectMedia` API.| Integrate device capabilities > Integrate media capabilities > [Code snippets](concepts/device-capabilities/media-capabilities.md#code-snippets)|
| 08/09/2022 | Introduced Teams Toolkit for Visual Studio 2022 | Tools and SDK > Teams Toolkit for Visual Studio > [Teams Toolkit overview for Visual Studio](toolkit/agents-toolkit-fundamentals.md) |
| 08/03/2022 | Share to Teams from personal app or tab | Integrate with Teams > Share to Teams > [Share to Teams from personal app or tab](concepts/build-and-test/share-to-teams-from-personal-app-or-tab.md) |
| 08/03/2022 | Added feature for retrieving meeting transcripts in the post-meeting scenario. | Build apps for Teams meetings and calls > Get meeting transcripts using Graph APIs > [Overview](graph-api/meeting-transcripts/overview-transcripts.md) |
| 08/03/2022 | Link unfurling for share to teams from web apps | Integrate with Teams > Share to Teams > [Share to Teams from web apps](concepts/build-and-test/share-to-teams-from-web-apps.md) |
| 08/01/2022| Notice: Developer Portal is now GA and App Studio is deprecated from August, 01, 2022. | Tools and SDK > [Developer Portal for Teams](concepts/build-and-test/teams-developer-portal.md) |
| 07/28/2022 | Add the Teams display picture and people card for in-meeting notification| Build apps for Teams meetings and calls > Enable and configure apps for Teams meetings > [Build in-meeting notification for Teams meeting](apps-in-teams-meetings/in-meeting-notification-for-meeting.md) |
| 07/28/2022 | Build shared channels in Teams | Build apps for Teams meetings and calls > [Shared channels](concepts/build-and-test/Shared-channels.md) |
| 07/28/2022|Introduced app manifest v1.14| App manifest > [App manifest schema for Teams](resources/schema/manifest-schema.md)|
| 07/26/2022|Suggested actions for bots| Build bots > Bot conversations > [Messages in bot conversations](bots/how-to/conversations/conversation-messages.md#send-suggested-actions)|
| 07/21/2022 | Introduced step by step guide to send activity feed notifications | Design your app > UI components> Activity feed notifications > [Send activity feed notification](sbs-graphactivity-feedbroadcast.yml) |
| 07/08/2022| Updates to send channel ID selected by user during app installation to bots via conversation and installation update events |  Build bots > Bot conversations > Conversation events in your Teams bot > [Conversation events in your Teams bot](bots/how-to/conversations/subscribe-to-conversation-events.md) |
| 06/16/2022 | Updated media capabilities to support desktop and mobile| Integrate device capabilities > [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md)|
| 06/08/2022 | Optional card feedback for success message| Build cards and task modules > Build cards > [Form completion feedback](task-modules-and-cards/cards/cards-actions.md#form-completion-feedback)|
| 06/03/2022 | Updated Add authentication module for enabling SSO for tab app with new structure and procedures | Add authentication > Tabs > [Enable single sign-on in a tab app](tabs/how-to/authentication/tab-sso-overview.md) |
| 05/24/2022 | Additional tips for rapid approval to publish your app linked to a SaaS offer | Publish to the Teams Store > Overview > [Additional tips for rapid approval to publish your app linked to a SaaS offer](~/concepts/deploy-and-publish/appsource/publish.md#additional-tips-for-rapid-approval-to-publish-your-app-linked-to-a-saas-offer) |
| 05/24/2022 | Submit your Outlook- and Office-enabled apps to the Teams Store | Extend your app across Microsoft 365 > [Overview](m365-apps/overview.md) |
| 05/24/2022 | App guidance and what's new in TeamsJS version 2.0.0| Tools and SDKs > [Teams JavaScript client SDK](tabs/how-to/using-teams-client-library.md)  |
| 05/24/2022 | Introduced app manifest version 1.13 | App manifest > [Manifest schema for Microsoft Teams](resources/schema/manifest-schema.md) |
| 5/24/2022|Bots and Message extensions in GCC and GCCH| • Plan your app > [Overview](concepts/cloud-overview.md#teams-app-capabilities) </br> • Build bots > [Overview](bots/what-are-bots.md) </br> • Build message extensions > [Overview](messaging-extensions/what-are-messaging-extensions.md) |
|04/26/2022|Uninstall behavior for personal app with bot | Build bots > Bot conversations > [Uninstall behavior updates in personal apps with bots](bots/how-to/conversations/subscribe-to-conversation-events.md#uninstall-behavior-for-personal-app-with-bot)|
| 04/22/2022 | Test preview for monetized apps | Monetize your app > [Test preview for monetized apps](concepts/deploy-and-publish/appsource/prepare/test-preview-for-monetized-apps.md)
| 04/22/2022 | In-app purchase flow for monetization of apps | Monetize your app > [In-app purchases](concepts/deploy-and-publish/appsource/prepare/in-app-purchase-flow.md)
| 04/28/2022 | Common reasons for app validation failure | Publish your app > Publish to the Teams Store > [Common reasons for app validation failure](concepts/deploy-and-publish/appsource/common-reasons-for-app-validation-failure.md)|
| 04/20/2022 |  Set up CI/CD pipelines | Tools and SDKs > Teams Toolkit for Visual Studio Code >  [Set up CI/CD pipelines](toolkit/use-CICD-template.md)|
| 04/19/2022 | Upload your app in Microsoft Teams | Publish your app > [Upload your app](concepts/deploy-and-publish/apps-upload.md)|
| 04/01/2022 | Introduced step-by-step guide to create Teams conversational bot| Build bots > Bot conversations > Channel and group conversations > [Step-by-step guide to create Teams conversational bot](sbs-teams-conversation-bot.yml) |
| 03/30/2022 | Updated the Get started module with Blazor app using tabs and bots|  Get started > [Build your first app using Blazor](sbs-gs-blazorupdate.yml)|
| 03/30/2022 | Device permissions for the browser | Integrate device capabilities > [Device permissions for the browser](concepts/device-capabilities/browser-device-permissions.md) |
| 03/29/2022 |Integrate People Picker | Integrate with Teams > [Integrate People Picker](concepts/device-capabilities/people-picker-capability.md)
| 03/23/2022 | Introduced step-by-step guide to unfurl links in Teams using bot | Build message extensions > Add link unfurling > [Unfurl links in Teams using bot](sbs-botbuilder-linkunfurling.yml)|  
| 03/22/2022 | Added information on debug process| • Tools and SDKs> Teams Toolkit for Visual Studio Code > [Debug your Teams app locally](toolkit/debug-local.md) </br> • Tools and SDKs> Teams Toolkit for Visual Studio Code > [Debug background process](toolkit/debug-background-process.md)|
| 03/14/2022 | Introduced step-by-step guide to build and test a connector in Microsoft Teams | Build webhooks and connectors > Create connectors for Microsoft 365 Groups > [Build Teams connectors](sbs-teams-connectors.yml)|
| 03/10/2022 | Added information on Moodle LMS and Microsoft 365 plugins | Integrate with Teams > Moodle LMS > [Moodle learning management system](resources/moodle-overview.md)|  
| 03/03/2022 | How to add authentication using external OAuth provider| Add authentication > Tabs > [Use external OAuth providers](tabs/how-to/authentication/auth-oauth-provider.md) |
| 02/25/2022 | Introduced step-by-step guide to invoke task modules in Teams| Build cards and task modules > Build task modules > Use task modules from bots > [Invoke task module from Teams](sbs-botbuilder-taskmodule.yml)|
| 02/24/2022| Introduced step-by-step guide to build action based message extension | Build Message Extensions > Action commands > Define action commands > [Build action based message extension](sbs-meetingextension-action.yml)|
| 02/24/2022 | Introduced step-by-step guide to build search based message extension | Build message extensions > Search commands > Define search commands > [Build search based message extension](sbs-messagingextension-searchcommand.yml)|
| 02/24/2022 | Introduced step-by-step guide to create Outgoing Webhooks | Build webhooks and connectors > Create Outgoing Webhooks > [Create Outgoing Webhooks](sbs-outgoing-webhooks.yml)|
| 02/23/2022 | Microsoft Teams Store ranking parameters| Publish your app > Publish to the Teams Store > [Microsoft Teams Store ranking parameters](concepts/deploy-and-publish/appsource/post-publish/teams-store-ranking-parameters.md)|
| 02/18/2022 | Introduced extensive Glossary for the Microsoft Teams Developer Documentation to help you find the definition about a term quickly | [Glossary](~/get-started/glossary.md) |
| 02/18/2022 | Updated the Overview module for mapping Teams app to organizational goals, user story, and exploring Teams app features | Overview > [Teams app that fits](overview.md) |
| 02/18/2022 | Updated the App fundamentals module to Plan your app to include mapping use cases to Teams features, and app planning checklist | Plan your app > [Overview](~/concepts/app-fundamentals-overview.md) |
| 02/17/2022 | What to expect after you submit your app?| Publish your app > Publish to the Teams Store > [Overview](concepts/deploy-and-publish/appsource/publish.md) |
| 02/15/2022 | Introduced step-by-step guide how to upload files to Teams from a bot | Build bots > Send and receive files > [Step-by-step guide how to upload files to Teams from a bot](sbs-file-handling-in-bot.yml) |
| 02/11/2022 | Shared meeting stage| • Build apps for Teams meetings > [Shared meeting stage](apps-in-teams-meetings/build-tabs-for-meeting.md) </br> • Build apps for Teams meetings > [Build apps for Teams meetings](apps-in-teams-meetings/build-apps-for-teams-meeting-stage.md) </br> • App manifest > Public developer preview > [Developer preview manifest schema](resources/schema/manifest-schema-dev-preview.md)|
| 02/08/2022 | Introduced step-by-step guide to create Calling and Meeting bot| Build bots > Calls and meetings bots > Register calls and meetings bot > [Step-by-step guide to create Calling and Meeting bot](sbs-calling-and-meeting.yml) |
| 02/02/2022 | Introduced app manifest version 1.12 | App manifest > [App manifest schema](resources/schema/manifest-schema.md) |
| 01/25/2022 | Send real-time captions API | Build apps for Teams meetings > Meeting apps API references> [Advanced meeting APIs](apps-in-teams-meetings/meeting-apps-apis.md)|
| 01/19/2022 | Adaptive Cards form completion feedback |  Build cards and task modules > Build cards > [Form completion feedback](task-modules-and-cards/cards/cards-actions.md#form-completion-feedback)|
| 01/17/2022 | People Picker in Adaptive Cards for desktop | Build cards and task modules > Build cards > [People Picker in Adaptive Cards](task-modules-and-cards/cards/people-picker.md)|

</details>
</br>
<details>
<summary><b>Older updates</b></summary>

Explore updates from the previous GA releases listed here.

</br>
<details>
<summary><b>2021</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
|12/24/2021| Introduced step-by-step guide to grant Tab device permissions | App fundamentals > Device capabilities > [Step-by-step guide to grant Tab device permissions](sbs-tab-device-permissions.yml) |
|12/23/2021| Introduced step-by-step guide to create Tabs with Adaptive Cards| Add authentication > Tabs > Use SSO authentication > [Step-by-step guide to create Tabs with Adaptive Cards](sbs-tab-with-adaptive-cards.yml) |
|12/21/2021 | Updated the Get started JavaScript, C#, and Node.js modules for Teams Toolkit 3.0.0 | • Get started > [Build your first app with JavaScript](sbs-gs-javascript.yml) <br> • Get started > [Build your first app with C# or .NET](sbs-gs-csharp.yml) <br> • Get started> [Build your first app with Node.js](sbs-gs-nodejs.yml) |
|12/20/2021| Introduced step-by-step guide for tabs and message extensions with Single sign-on (SSO) | Add authentication > Tabs > Use SSO authentication > [Step-by-step guide with SSO for tabs and message extensions](sbs-tabs-and-messaging-extensions-with-SSO.yml)|
|12/20/2021| Introduced step-by-step guide to create meeting content bubble | Build apps for Teams meetings > Enable and configure apps for meetings > [Step-by-step guide to create meeting content bubble](sbs-meeting-content-bubble.yml) |
|12/09/2021| Introduced step-by-step guide to meeting Stageview | Build apps for Teams meetings > Enable and configure apps for meetings > [Step-by-step guide to create meetings Stageview](sbs-meetings-stage-view.yml)|
|12/13/2021 | Introduced guidelines for app linked to SaaS offer | Publish your app > Publish to the Teams Store > Review Teams Store validation guidelines > [Guidelines for apps linked to SaaS offer](concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines.md#apps-linked-to-saas-offer)|
|12/09/2021| Introduced step-by-step guide to create meeting side panel | Build apps for Teams meetings > Enable and configure apps for meetings > [Step-by-step guide to create meeting side panel in Teams](sbs-meetings-sidepanel.yml)|
|12/01/2021 | Introduced new Teams Store icon | • Design your app > App capabilities > [Designing your personal app for Microsoft Teams](concepts/design/personal-apps.md)</br> • Design your app > UI components > [Designing your Microsoft Teams app with advanced UI components](concepts/design/design-teams-app-advanced-ui-components.md) |
|11/24/2021| Introduced step-by-step guide to generate meeting token | Build apps for Teams meetings > Enable and configure apps for meetings > [Step-by-step guide to create meeting token in Teams](sbs-meeting-token-generator.yml)|
|11/17/2021| Updated Teams Store validation guidelines|[Teams Store validation guidelines](~/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines.md)|
|11/17/2021| Static and dynamic typeahead search for desktop and mobile users | • Build cards and task modules > Build cards > [Typeahead search in Adaptive Cards](task-modules-and-cards/cards/dynamic-search.md) </br> • Build cards and task modules > Build cards > Overview >  [Typeahead search in Adaptive Cards](task-modules-and-cards/what-are-cards.md#typeahead search-in-adaptive-cards) </br> • Build cards and task modules > Overview > [Cards and task modules](task-modules-and-cards/cards-and-task-modules.md)|
|11/13/2021| Bots can be enabled to receive all channel messages using resource-specific consent (RSC) | • Build bots > Bot conversations > Messages in bot conversations > [Receive all channel messages with RSC](~/bots/how-to/conversations/channel-messages-for-bots-and-agents.md) </br> • Build bots > Bot conversations > [Bot conversation overview](~/bots/how-to/conversations/conversation-basics.md) </br> • Build bots > Bot conversations > [Channel and group conversations](~/bots/how-to/conversations/channel-and-group-conversations.md) |
|10/28/2021| Monetize your Teams app with a transactable SaaS offer | Publish your app > Publish to the Teams Store > [Include a SaaS offer with your Teams app](~/concepts/deploy-and-publish/appsource/prepare/include-saas-offer.md) |
|10/25/2021| Updated Get started module for Microsoft Teams Developer Documentation with new structure and procedures in a step-by-step guide | Get started > [Get started with your first Teams app](get-started/get-started-overview.md) |
|10/20/2021| Meeting stage is now available in GA | Build apps for Teams meetings > [Enable and configure your apps for Teams meetings](apps-in-teams-meetings/build-tabs-for-meeting.md) |
|10/20/2021| Meeting Details API and real-time Teams meeting events | Build apps for Teams meetings > [Get meeting details API](apps-in-teams-meetings/meeting-apps-apis.md) |
|10/18/2021| Tabs link unfurling and Stageview | Build tabs > [Tabs link unfurling and Stageview](tabs/tabs-link-unfurling.md) |
|10/08/2021| New best practices for designing Adaptive Cards | Design your app > UI components > [Designing Adaptive Cards for your Teams app](task-modules-and-cards/cards/design-effective-cards.md) |
|10/05/2021| Hide Teams app until Admin allows to un-hide the app | Design your app > [Block apps by default for users until an admin approves](concepts/deploy-and-publish/add-default-install-scope.md#block-apps-by-default-for-users-until-an-admin-approves) |
|10/05/2021| Plan your apps for Teams mobile | App fundamentals > [Plan responsive tabs for Teams mobile](concepts/design/plan-responsive-tabs-for-teams-mobile.md) |
|10/04/2021| New Developer Portal for Teams introduced for managing your Teams apps | Tools and SDK > [Developer Portal for Teams](concepts/build-and-test/teams-developer-portal.md) |
|09/21/2021|Teams supports Microsoft Entra Object ID and UPN in user mention for bots and Incoming Webhooks | • Build cards and task modules > Build cards > [Microsoft Entra Object ID and UPN in user mention](task-modules-and-cards/what-are-cards.md#support-for-azure-ad-object-id-and-upn-in-user-mention) </br> • Build cards and task modules > Build cards > [Cards- Overview](task-modules-and-cards/cards/cards-format.md#format-cards-with-markdown) |
|08/16/2021| Support for input validation on Adaptive Cards (v1.3 for all capabilities) and Universal Actions (v1.4 for bot sent cards) | • Adaptive Cards > Authoring cards > [Input validation](/adaptive-cards/authoring-cards/input-validation)</br> • Build cards and task modules > Build cards > Universal actions for Adaptive Cards > [Universal Actions for Adaptive Cards v1.4](task-modules-and-cards/cards/universal-actions-for-adaptive-cards/overview.md) |
|08/30/2021| Custom Together Mode scenes feature combines participants into a single virtual scene and places their video streams in pre-determined seats | Build apps for Teams meetings > [Custom Together Mode scenes](~/apps-in-teams-meetings/teams-together-mode.md) |
|08/25/2021| Introduced step-by-step guide to create a Teams bot with Single sign-on (SSO) | Add authentication > Bots > [Step-by-step guide to create Teams bot with SSO](sbs-bots-with-sso.yml) |
|08/19/2021| Installation update event received when you install a bot to a conversation thread | Build bots > Bot conversations > [Installation update event](bots/how-to/conversations/subscribe-to-conversation-events.md#installation-update-event) |
|08/12/2021|Build tabs with Adaptive Cards| Build tabs > [Build tabs with Adaptive Cards](tabs/how-to/build-adaptive-card-tabs.md) |
|07/08/2021|Teams mobile adds support for apps in meetings | Build apps for Teams meetings > [Build apps for Teams meeting](apps-in-teams-meetings/build-apps-for-teams-meeting-stage.md) |
|06/28/2021|Integrate People Picker capability | Integrate with Teams > [Integrate People Picker capability](concepts/device-capabilities/people-picker-capability.md) |  
|06/25/2021| Introduced step-by-step guide to send proactive messages | Build bots > Bot conversation > Proactive messages > [Step-by-step guide to send proactive messages](sbs-send-proactive.yml) |
|06/09/2021| Stageview for images in Adaptive Cards with `allowExpand` attribute | Build cards and task modules > Build cards > [Stageview for images in Adaptive Cards](task-modules-and-cards/cards/cards-format.md#stageview-for-images-in-adaptive-cards) |
|05/31/2021| Conversational tabs | Build tabs > [Start and continue conversations about content in your tabs](~/tabs/how-to/conversational-tabs.md) |
|05/24/2021| Updated Teams app design guidelines with mobile patterns | Design your app > [Designing your Teams app](~/concepts/design/design-teams-app-overview.md) |
|05/13/2021| Added information on mConnect and Skooler | Integrate with Teams > Moodle LMS > [Moodle learning management system](resources/moodle-overview.md)|
|05/10/2021| App manifest v1.10 released | App manifest > [Manifest schema](resources/schema/manifest-schema.md) |
|05/10/2021| New app customization feature | Design your app > [Enable orgs to customize your app](concepts/design/enable-app-customization.md) |
|05/07/2021| Deep links for audio and video calls in chat | Integrate with Teams > [Deep links](concepts/build-and-test/deep-link-workflow.md#deep-link-to-start-an-audio-video-call-with-users) |
|04/30/2021|New guidance on how to publish apps to the Teams Store | • Publish to the Teams Store > [Publish your app to the Teams Store](concepts/deploy-and-publish/appsource/publish.md)</br> • Publish to the Teams Store > [Teams Store validation guidelines](concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines.md) |
|04/29/2021 | Support for Universal Actions for Adaptive Cards v1.4 | Build cards and task module > Build cards > Universal actions for Adaptive Cards > [Universal Actions for Adaptive Cards](task-modules-and-cards/cards/universal-actions-for-adaptive-cards/overview.md) |
|04/29/2021 | User Specific Views | Build cards and task module > Build cards > Universal actions for Adaptive Cards > [User Specific Views](task-modules-and-cards/cards/universal-actions-for-adaptive-cards/User-Specific-Views.md) |
|04/29/2021 | Sequential Workflows | Build cards and task module > Build cards > Universal actions for Adaptive Cards > [Sequential Workflows](task-modules-and-cards/cards/universal-actions-for-adaptive-cards/Sequential-Workflows.md) |
|04/29/2021 | Up to date cards | Build cards and task module > Build cards > Universal actions for Adaptive Cards > [Up to date cards](task-modules-and-cards/cards/universal-actions-for-adaptive-cards/Up-To-Date-Views.md) |
|04/08/2021| App customization feature | • Design your apps > [Design teams app overview](concepts/design/enable-app-customization.md)</br> • Tools and SDKs > [Developer Portal](concepts/build-and-test/teams-developer-portal.md) </br> • App manifest > Public developer preview > [Manifest schema](resources/schema/manifest-schema-dev-preview.md) |
|03/18/2021| Notice: Update to version 4.10 or above of the Bot Framework SDK, as we've started with the deprecation process for `TeamsInfo.getMembers` and `TeamsInfo.GetMembersAsync`. | Build bots > [Bot API Changes for Team/Chat Members](resources/team-chat-member-api-changes.md) |
|03/05/2021|Default install scope and group capability | Publish your app > [Default install scope and group capability](concepts/deploy-and-publish/add-default-install-scope.md) |
|03/05/2021|Reorder personal app tabs | Build tabs > [Reorder the chat tab in personal apps](tabs/how-to/create-personal-tab.md#reorder-tabs) |
|03/04/2021|Information masking in Adaptive Cards | Build cards and task modules > Build cards > [Information masking in Adaptive Cards](task-modules-and-cards/cards/cards-format.md#information-masking-in-adaptive-cards) |
|02/19/2021|Added location capabilities. | • App fundamentals > Device capabilities > [Overview](concepts/device-capabilities/device-capabilities-overview.md) </br> • App fundamentals > Device capabilities > [Request device permissions](concepts/device-capabilities/native-device-permissions.md) </br> • App fundamentals > Device capabilities > [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md) </br> • App fundamentals > Device capabilities > [Integrate QR or barcode scanner capability](concepts/device-capabilities/qr-barcode-scanner-capability.md) </br> • App fundamentals > Device capabilities > [Integrate location capabilities](concepts/device-capabilities/location-capability.md) |
|02/18/2021|Added QR or barcode scanner capability.| • App fundamentals > Device capabilities > [Overview](concepts/device-capabilities/device-capabilities-overview.md) </br> • App fundamentals > Device capabilities > [Request device permissions](concepts/device-capabilities/native-device-permissions.md) </br> • App fundamentals > Device capabilities > [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md) </br> • App fundamentals > Device capabilities > [Integrate QR or barcode scanner capability](concepts/device-capabilities/qr-barcode-scanner-capability.md) |
|02/09/2021|Added microphone capability information in device capabilities overview. |• App fundamentals > Device capabilities > [Overview](concepts/device-capabilities/device-capabilities-overview.md) </br> App fundamentals > • Device capabilities > [Request device permissions](concepts/device-capabilities/native-device-permissions.md) </br> • App fundamentals > Device capabilities > [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md)|

<br>

</details>

<br>

<details>
<summary><b>2020</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
|11/30/2020|Identity platform integration with Teams Toolkit and Visual Studio Code for tabs |[Single sign-on authentication with Teams Toolkit and Visual Studio Code for tabs](toolkit/add-single-sign-on.md)|
|11/16/2020|Teams app manifest updated to version 1.8.|[Reference: Manifest schema for Microsoft Teams](resources/schema/manifest-schema.md)|
|11/10/2020|Teams bot design guidelines |[Bot design guidelines](bots/design/bots.md)|
|09/30/2020|Sending and receiving files to bots on mobile devices is now supported |[Send and receive files through your bot](resources/bot-v3/bots-files.md)|
|09/22/2020|New information for getting started with Teams development |[Build your first Teams app overview](build-your-first-app/build-first-app-overview.md)|
|09/18/2020|Support for in-meeting Teams apps (Release Preview) |[Apps in Teams meetings](apps-in-teams-meetings/teams-apps-in-meetings.md)|
|08/19/2020|Import Teams messages with Microsoft Graph |[Import third-party platform messages to Teams using Microsoft Graph](graph-api/import-messages/import-external-messages-to-teams.md)
|08/12/2020 |Adaptive Cards support in incoming webhook moved to GA |[Send Adaptive Cards using an incoming webhook](~/webhooks-and-connectors/how-to/connectors-using.md#send-adaptive-cards-using-an-incoming-webhook) |
|08/10/2020|Get started building Teams apps with the Visual Studio Toolkit |[Build apps with the Microsoft Teams Toolkit and Visual Studio Code](toolkit/visual-studio-overview.md) |
|08/06/2020|Support for Tabs SSO authentication |[Develop an SSO Microsoft Teams Tab](tabs/how-to/authentication/tab-sso-overview.md) |
|07/27/2020 | Graph proactive bots and messages (Public Preview) |[Enable proactive bot installation and proactive messaging in Teams with Microsoft Graph](graph-api/proactive-bots-and-messages/graph-proactive-bots-and-messages.md)|
|07/22/2020 |Mobile device capability updates |[Request device permissions for your Microsoft Teams tab](concepts/device-capabilities/native-device-permissions.md) |
|07/20/2020|Teams App Validation Tool for AppSource submissions |[Teams App Validation Tool](concepts/deploy-and-publish/appsource/prepare/submission-checklist.md)
|07/15/2020|Create a virtual assistant for Teams |[Virtual Assistant for Microsoft Teams](samples/virtual-assistant.md)|
|07/14/2020|Surfacing a native loading indicator documentation |[Showing a native loading indicator](tabs/how-to/create-tab-pages/content-page.md#show-a-native-loading-indicator)
|07/01/2020|Get started building Teams apps with the Visual Studio Code Toolkit |[Build apps with the Microsoft Teams Toolkit and Visual Studio Code](sbs-gs-javascript.yml) |
|07/01/2020|Single sign-on for tabs GA for Teams web and desktop clients |[Single Sign-On (SSO)](tabs/how-to/authentication/tab-sso-overview.md)|
|06/05/2020| Manifest schema updated to version 1.7.| [Reference: Manifest schema for Microsoft Teams](resources/schema/manifest-schema.md)|
|05/18/2020|Integrate Power Virtual Agents with Teams |[Integrate a Power Virtual Agents chatbot with Microsoft Teams](bots/how-to/add-power-virtual-agents-bot-to-teams.md)|
|04/01/2020|Integrate WFM systems with Shifts Connector for Teams |[Microsoft Teams Shifts WFM connectors](samples/shifts-wfm-connectors.md)
|03/24/2020 | Added support for retrieving a single member of a conversation, and additional support for retrieving paged members | [Get Teams context for your bot](~/bots/how-to/get-teams-context.md) |

<br>

</details>

<br>

<details>
  
<summary><b>2019</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
| 12/26/2019 | The `replyToId` parameter in payloads sent to a bot is no longer encrypted, allowing you to use this value to construct deep links to these messages. Message payloads include the encrypted values in the parameter `legacy.replyToId`.  |
| 11/05/2019 | Single sign-on using the Teams JavaScript SDK. | [Single sign-on](tabs/how-to/authentication/tab-sso-overview.md) |
| 10/31/2019 | Conversational bots and message extension documentation updated to reflect the 4.6 Bot Framework SDK. Documentation for the v3 SDK is available in the Resources section. | All bot and message extension documentation |
| 10/31/2019 | New documentation structure, and major article refactoring. Report any dead links or 404s by creating a GitHub Issue. | All of them! |
| 09/13/2019 | Request bot is installed from action-based message extension. | [Initiate actions with message extensions](resources/messaging-extension-v3/create-extensions.md#request-to-install-your-conversational-bot)
| 08/28/2019 | Support for private channels in tabs and Connectors. | [Get context for your tab](tabs/how-to/access-teams-context.md#retrieve-context-in-private-channels) |
| 06/20/2019 | Share an external website, from an external website, into a Teams channel. | [Share to Teams](concepts/build-and-test/share-to-teams-overview.md). |
| 05/25/2019 | Respond with bot message from task module. | [Respond with bot message from task module](resources/messaging-extension-v3/create-extensions.md#respond-with-an-adaptive-card-message-sent-from-a-bot) |
| 05/25/2019 | Bots in group chats. | [Interact with a bot in group chat or channel](~/concepts/bots/bot-conversations/bots-conv-channel.md) |
| 05/20/2019 | App manifest localization. | [App localization](~/publishing/apps-localization.md) |
| 05/20/2019 | Message actions. | [Message Actions](resources/messaging-extension-v3/create-extensions.md#action-type-message-extensions) |
| 05/20/2019 | Link unfurling (custom URL previews). | [Link unfurling](messaging-extensions/how-to/link-unfurling.md)|
| 05/06/2019 | Application Certification program for Teams Store apps. | [Application Certification](~/concepts/deploy-and-publish/appsource/post-publish/overview.md#complete-microsoft-365-certification) |
| 05/06/2019 | App Templates are now available | [App Templates](~/samples/app-templates.md) |
| 04/23/2019 | Action-based Message Extensions are now available. | [Action-based Message Extensions](~/concepts/messaging-extensions/create-extensions.md) |
| 02/18/2019 | Creating deep links to private chat. | [Deep linking to a chat](concepts/build-and-test/deep-link-teams.md#deep-link-to-navigate-to-chat-messages) |
| 01/23/2019 | Surfacing SKU and licenceType information in the tab context. | [Tab Context](~/concepts/tabs/tabs-context.md) |

</details>

<br>

<details>
<summary><b>2018</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
| 11/12/2018 | Tabs in group chat are now available in the released version of Teams. The tabs section is updated for clarity.| [Configurable tabs](~/concepts/tabs/tabs-configurable.md) |
| 11/09/2018 | You can now create deep links to private chats between users. | [Deep linking to a chat](concepts/build-and-test/deep-link-teams.md#deep-link-to-navigate-to-chat-messages) |
| 11/08/2018 | SharePoint Framework 1.7 and a new feature to use Microsoft Teams tab as a SharePoint Framework web part is shipped. | [Tabs in SharePoint](~/concepts/tabs/tabs-in-sharepoint.md) |
| 11/05/2018 | The **task module** feature is released. A task module allows you to create modal pop-up experiences in your Teams application, from both bots and tabs. Inside the pop-up, you can run your own custom HTML/JavaScript code, show an `<iframe>`-based widget such as a YouTube or Microsoft Stream video, or display an [Adaptive Card](/adaptive-cards/). | [Task module Overview](~/concepts/task-modules/task-modules-overview.md), [task module in tabs](~/concepts/task-modules/task-modules-tabs.md),  [task module in bots](~/concepts/task-modules/task-modules-bots.md) |
| 10/05/2018 | Formatting information for cards is updated and tested in the desktop, iOS, and Android clients for Teams. | [Cards](~/concepts/cards/cards.md), [Card formatting](~/concepts/cards/cards-format.md) |
| 09/24/2018 | Calls and online meetings APIs for Microsoft Graph is released to beta, and Teams apps can now interact with users in rich ways using voice and video. | [Calls and online meetings bots](~/concepts/calls-and-meetings/registering-calling-bot.md), [Real-time media concepts](~/concepts/calls-and-meetings/real-time-media-concepts.md), [Registering a calling bot](~/concepts/calls-and-meetings/registering-calling-bot.md), [Debugging and local testing](~/concepts/calls-and-meetings/debugging-local-testing-calling-meeting-bots.md), [Application-hosted media](~/concepts/calls-and-meetings/requirements-considerations-application-hosted-media-bots.md), [Handling incoming call notifications](~/concepts/calls-and-meetings/call-notifications.md) |
| 09/11/2018 | Tab configuration pages are now taller. | [Tab Design](tabs/design/tabs.md) |
| 08/15/2018 | Adaptive Cards are now supported in Teams.|[Adaptive Card actions in Teams](task-modules-and-cards/cards/cards-reference.md#adaptive-card) |
| 08/10/2018 | Client support for Dev Tools.| [Dev Tools for the Microsoft Teams Desktop Client](~/resources/dev-preview/developer-preview-tools.md)|
| 08/08/2018 | Message extensions now support multiple commands. | [composeExtensions.commands](~/resources/schema/manifest-schema.md#composeextensionscommands)|
| 08/07/2018 | Inline configuration is now supported in Connectors. The Connectors documentation is revised and expanded for clarity.| [Connectors](~/concepts/connectors/connectors.md)|
| 08/06/2018 | Your bot can now send and receive files. | [Send and receive files through your bot](~/bots/how-to/bots-filesv4.md)|
| 07/23/2018 | Information about app recertification is added to the publishing section. |[Manifest permissions](resources/schema/manifest-schema.md#permissions)|
| 07/16/2018 | Additional space is allocated to the tab configuration page. | [The tab configuration page is significantly taller](tabs/design/tabs.md)|
| 07/12/2018 | Information on guest access. | [Guest access in Microsoft Teams](/microsoftteams/guest-access#guest-access-overview)|
| 06/07/2018 | Information for the Microsoft Teams Tenant App Catalog is added. | [Publish your Microsoft Teams app](~/publishing/apps-publish.md)|
| 05/29/2018 | Adaptive Cards are supported in Teams. | [Adaptive Card actions in Teams](task-modules-and-cards/cards/cards-reference.md) |
| 04/17/2018 | replyToID is added to the payload for the `Invoke` and `MessageBack` card actions. This is especially useful if you need to update the message that the card action came from. | [Card actions](~/concepts/cards/cards-actions.md)|
| 04/12/2018 | Added this topic to track changes to the Teams programming interface and this documentation set. | [What's new](~/whats-new.md)|
| 04/10/2018 | Changed authentication URLs to consistently use the tenant ID in the path. | [Authentication flow for Tabs](~/concepts/authentication/auth-flow-tab.md), [Microsoft Entra Tab authentication](~/concepts/authentication/auth-tab-AAD.md)|
| 04/06/2018 | Added design guidelines for using the Command Box. |[Command box](~/resources/design/framework/command-box.md)|
| 04/02/2018 | Using bots to send notifications for your app. |[Notification-only bots](~/concepts/bots/bots-notification-only.md)|
| 03/27/2018 | Expanded documentation for proactive messaging. |[Starting a conversation](./concepts/bots/bot-conversations/bots-conv-proactive.md)|
| 03/15/2018 | Refactored documentation for cards. |[Cards](~/concepts/cards/cards.md), [Card actions](~/concepts/cards/cards-actions.md), [Card formatting](~/concepts/cards/cards-format.md), [Card reference](~/concepts/cards/cards-reference.md)|
| 02/27/2018 | Added sample code to demonstrate AsTeamsChannelAccounts() method. |[Get context for your bot](~/concepts/bots/bots-context.md)|
| 02/05/2018 | Added topics for getting started using C#. |[Get started on the Microsoft Teams platform with C#/.NET](./get-started/get-started-dotnet-app-studio.md)|

</details>
</details>
</details>

::: zone-end

::: zone pivot="dev-preview"

Discover Microsoft Teams platform features that are in developer preview. You can now get latest Teams platform updates by subscribing to the RSS feed [![download feed](~/assets/images/RSSfeeds.png)](https://aka.ms/TeamsPlatformUpdates). For more information, see [configure RSS feed](#get-latest-updates).

## Microsoft Build 2025 :::image type="icon" source="assets/images/bullhorn.png" border="false"

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
| May 19, 2025 | Introducing Teams AI library v2. This new library consolidates all the SDKs needed to create collaborative agents for Microsoft Teams | [Teams AI library v2 (preview)](/microsoftteams/platform/teams-ai-library/welcome) |
| May 16, 2025 | Increase app engagement with custom activity icons in activity feed notifications | Build tabs > Tab features > Send activity feed notifications > [Custom activity icons in activity feed notifications](/graph/teams-send-activityfeednotifications?toc=%2Fmicrosoftteams%2Fplatform%2Ftoc.json&bc=%2Fmicrosoftteams%2Fplatform%2Fbreadcrumb%2Ftoc.json&tabs=desktop%2Chttp#custom-activity-icons-in-activity-feed-notifications) |

## Developer preview

:::row:::
:::column:::

:::image type="icon" source="~/assets/images/developer-preview.png":::

:::column-end:::
:::column span="2":::

Developer preview is a public program that provides early access to unreleased Teams platform features.
<!--
**2025 May**

* ***May 16, 2025***: [Increase app engagement with custom activity icons in activity feed notifications](/graph/teams-send-activityfeednotifications?toc=%2Fmicrosoftteams%2Fplatform%2Ftoc.json&bc=%2Fmicrosoftteams%2Fplatform%2Fbreadcrumb%2Ftoc.json&tabs=desktop%2Chttp#custom-activity-icons-in-activity-feed-notifications).

* ***May 06, 2025***: [Introducing Teams AI library v2. This new library consolidates all the SDKs needed to create collaborative agents for Microsoft Teams](/microsoftteams/platform/teams-ai-library/welcome/overview).
-->
<br/>

<details>

<summary><b>2025</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ---------------- |
| 10/04/2025 | Introducing custom engine agents support for Microsoft 365 Copilot Chat. | Build bots and agents > Teams AI library v1 > [Build with Teams AI library](bots/how-to/teams-conversational-ai/how-conversation-ai-get-started.md#add-support-for-microsoft-365-copilot-chat) |
| 17/03/2025 | Precache your tab app to optimize its initial load time | Build tabs > Tab features > [App caching for your tab app](tabs/how-to/app-caching.md#precaching-tab-apps) |
| 19/02/2025 | Introducing stop stream generation button for streaming bot messages | Build bots > Bot user experience > [Stream bot messages](bots/streaming-ux.md) |
| 03/02/2025 | Create personal scope apps that integrate seamlessly with Public Switched Telephone Network (PSTN) and Teams-to-Teams calls | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Build tabs for meeting](apps-in-teams-meetings/build-tabs-for-meeting.md) |

</details>
</br>

<details>

<summary><b>2024</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ---------------- |
| 19/11/2024 | Introduced optional `abbreviated` property for app display name on the app bar. | App manifest > Public developer preview > Public developer preview app manifest > [name](~/resources/schema/manifest-schema-dev-preview.md#name) |
| 18/11/2024 | Stream bot messages to deliver the bot's response to users in real-time. | Build bots > Build custom engine agent > [Stream bot messages](bots/streaming-ux.md) |
| 17/10/2024 | Learn about runtime requirements in app manifest to tailor your app's behavior in Microsoft 365 hosts. | Extend your app across Microsoft 365 > [Specify Microsoft 365 host runtime requirements in app manifest](m365-apps/specify-runtime-requirements.md) |
| 17/10/2024 | Learn about copilotExtensions renamed to copilotAgents in developer preview app manifest. | App manifest > Public developer preview app manifest > [copilotAgents](resources/schema/manifest-schema-dev-preview.md#copilotagents) |
| 16/09/2024 | Learn about requirements for the validation of your agent to increase its chances of being listed on Teams Store. | Publish to the Teams Store > [Validation guidelines for agents](concepts/deploy-and-publish/appsource/prepare/review-copilot-validation-guidelines.md) |
| 16/09/2024 | Explore the development guidance to build agents. | Build message extensions > Bot Framework > Search commands > [Guidelines to create and upgrade agents](messaging-extensions/dev-guidelines-agents.md) |
| 03/09/2024 | Introduced nested app authentication for single-page applications that are embedded in host environment. | Add authentication > [Enable nested app authentication](concepts/authentication/nested-authentication.md)|
| 14/06/2024 | Introduced preapproval of RSC permissions for admins to control RSC permissions for app installation. | Utilize Teams data with Microsoft Graph > Resource-specific consent > [Preapproval of RSC permissions](graph-api/rsc/preapproval-instruction-docs.md) |
| 23/05/2024 | Leverage AI label, citations, feedback buttons, and sensitivity labels in your bot's messages. | Build bots > Bot conversations > [Format AI bot messages](bots/how-to/format-ai-bot-messages.md) |
| 23/05/2024 | Enhance your Copilot message extension agent to hand off a conversation to your custom engine agent.| Build message extensions > Build message extensions using Bot Framework > Search commands > [Copilot handoff](bots/how-to/conversations/bot-copilot-handoff.md)|
| 14/05/2024 | Introduced a new manifest property to let potential customers contact you with queries before they can confidently adopt your app.| App manifest > [Public developer preview](resources/schema/manifest-schema-dev-preview.md#developercontactinfo)|
| 07/05/2024 | You can specify a 32x32 color icon with a transparent background to ensure a consistent appearance when your app runs in Outlook and Microsoft 365.| Publish your app > [32x32 color icon](concepts/build-and-test/apps-package.md#outline-icon)|
| 15/03/2024 | Extend static tabs to channels with a customizable experience. | [Build tabs for Teams](tabs/what-are-tabs.md) |
| 12/02/2024 | Build API-based message extension using Developer Portal for Teams. | Build message extension > [Build API-based message extension](messaging-extensions/build-api-based-message-extension.md) |
| 06/02/2024 | Introduced `systemDefault` reserved activity type for send activity feed notifications| Build tabs > [Send activity feed notifications](tabs/send-activity-feed-notification.md#requirements-to-use-the-activity-feed-notification-apis)|
|25/01/2024| Actions help to integrate your app into your user's workflow by enabling easy discoverability and seamless interaction with the content. | Extend your app across Microsoft 365 > [Actions in Microsoft 365](m365-apps/actions-in-m365.md)|
|12/01/2024| Introduced Teams Toolkit command line interface v3. | Tools and SDKs > Tools > [Teams Toolkit command line interface](toolkit/teams-toolkit-CLI.md)|

</details>
</br>

<details>
<summary><b>2023</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ----------------|
|27/11/2023| Extend an action-based Teams message extension across Microsoft 365. | Extend your app across Microsoft 365 > [Extend m365 teams message extension](~/m365-apps/extend-m365-teams-message-extension.md)|
|14/11/2023| Build a bot-based message extension and extend the message extension as agent for Microsoft 365 Copilot and also check the guidelines to create or upgrade a message extension agent for Microsoft 365 Copilot. | Build message extensions > Build message extensions using Bot Framework > Search commands > [Extend bot-based message extension as agent](messaging-extensions/build-bot-based-agent.md) and [Guidelines for agents](messaging-extensions/dev-guidelines-agents.md) |
|02/11/2023| Introduced Adaptive Card Previewer in public developer preview. | Tools > [Adaptive Card Previewer](concepts/build-and-test/adaptive-card-previewer.md)|
|25/10/2023| Introduced the `extensions` property in public developer preview app manifest schema. | App manifest > [Public developer preview](resources/schema/manifest-schema-dev-preview.md#extensions)|
|25/10/2023| Build message extensions using API (API-based) to interact directly with third-party data, apps, and services. | Build message extensions > [Build message extensions using API](messaging-extensions/api-based-overview.md)|
|28/09/2023| Configure your bot during installation or after installation from the team or group chat where the bot is installed. | Build bots > [Bot configuration experience](bots/how-to/bot-configuration-experience.md)|
|31/08/2023| The new Teams client supports light theme for apps in Teams meetings. | Build tabs > [Get context for your tab](tabs/how-to/access-teams-context.md#handle-theme-change)|
|28/08/2023| Teams app manifest is now referred to as app manifest. | App manifest > [App manifest schema](resources/schema/manifest-schema.md)|
|21/08/2023| Introduced the new Microsoft Teams client to provide better experience for your apps and users | Resources > [Introducing the new Microsoft Teams client](resources/teams-updates.md)|
|21/08/2023| Use Adaptive Card-based Loop components to build collaborative experiences within Teams message extensions that work across Microsoft 365. | Extend your app across Microsoft 365 > [Adaptive Card-based Loop components](m365-apps/design-loop-components.md)|
|08/08/2023| Use callRecording API to fetch meeting recording from all meetings. | Build apps for Teams meetings and calls > [Get meeting transcripts and recordings using Graph APIs](graph-api/meeting-transcripts/overview-transcripts.md)|
|31/07/2023| Bots can mention tags in Adaptive Cards. |Build bots > Bot conversations > Message in bot conversations > Channel and group chat conversation with a bot > [Bots can mention tags in Adaptive Cards](bots/how-to/conversations/channel-and-group-conversations.md#tag-mention)|
|31/07/2023| Bots can mention tags in Adaptive Cards. |Build bots > Bot conversations > Message in bot conversations > Channel and group chat conversation with a bot > [Bots can mention tags in Adaptive Cards](bots/how-to/conversations/channel-and-group-conversations.md#tag-mention)|
|13/07/2023| Extend static tabs to group chat or meetings with a customizable experience. |Build tabs > [Overview](tabs/what-are-tabs.md)|
| 25/05/2023 | Use a deep link to open a tab app in meeting side panel in Teams mobile client. | Build apps for Teams meetings and calls > Enable and configure apps for Teams meeting > [Build tabs for meeting](apps-in-teams-meetings/build-tabs-for-meeting.md#deep-link-to-meeting-side-panel) |
|23/05/2023 | Teams AI library helps you build AI-powered Teams apps. | Build Bots > [Teams AI library](bots/how-to/teams-conversational-ai/teams-conversation-ai-overview.md)|
|23/05/2023| Extend Microsoft 365 Copilot to integrate with Microsoft Teams apps to turn your app into the most powerful productivity tool. | [Extend Microsoft 365 Copilot](messaging-extensions/how-to-extend-copilot.md)|
|31/01/2023| Send notifications to specific participants on a meeting stage with targeted in-meeting notification. |Build apps for Teams meetings and calls > Enable and configure apps for meetings > Build in-meeting notification for Teams meeting > Build tabs for meeting > [Targeted in-meeting notification](apps-in-teams-meetings/in-meeting-notification-for-meeting.md#targeted-in-meeting-notification)|
|30/01/2023| Enable app caching to improve subsequent launch time of the apps to the meeting side panel.|Build tabs > [App caching for your tab app](tabs/how-to/app-caching.md) |

</details>
</br>

<details>
<summary><b>2022</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
|05/12/2022| Use share in meeting to share any document or third-party app to the meeting stage.|Build apps for Teams meetings and calls > Enable and configure apps for meetings > [Share in meeting](concepts/build-and-test/share-in-meeting.md) |
|10/11/2022| Enable bots to receive all conversation messages without being @mentioned in relevant contexts.|Build bots > Bot conversations > Message in bot conversations > [Receive all conversation messages with RSC](bots/how-to/conversations/channel-messages-for-bots-and-agents.md) |
| 09/23/2022 | Use apps in Teams meetings scheduled through public channels. | Build apps for Teams meetings and calls > [Apps for Teams meetings and calls](apps-in-teams-meetings/teams-apps-in-meetings.md) |
| 08/23/2022 | Share apps to the Teams meeting stage in mobile. | Build apps for Teams meetings and calls > [Enable and configure apps for meetings](apps-in-teams-meetings/teams-apps-in-meetings.md) |
| 08/03/2022 | Use toggle incoming audio API to toggle the incoming audio state setting for the user in Teams meeting stage from mute to unmute or vice-versa. | Build apps for Teams meetings and calls > [Meeting apps API references](/microsoftteams/platform/apps-in-teams-meetings/api-references?tabs=dotnet) |
| 08/02/2022| Use Collaboration controls to build custom collaborative experiences and integrate with Microsoft 365 services. | Integrate with Teams > [Collaboration controls](samples/collaboration-control.md) |
|05/24/2022| Use Live Share to transform Teams apps into collaborative multi-user experiences without writing any dedicated back-end code. | Build apps for Teams meetings > Enhanced collaboration with Live Share > [Overview](apps-in-teams-meetings/teams-live-share-overview.md) |
| 10/28/2021 |Enable bots to receive all channel messages using resource-specific consent (RSC). | • Build bots > Bot conversations > [bot conversation overview](~/bots/how-to/conversations/conversation-basics.md) </br> • Build bots > Bot conversations > [channel and group conversations](~/bots/how-to/conversations/channel-and-group-conversations.md) |
| 06/16/2021 | Use resource-specific consent permissions to allow the app to access the data of a specific instance of a resource type. | • Utilize Teams data with Microsoft Graph > [Resource-specific consent](graph-api/rsc/resource-specific-consent.md) </br> • Test your app > Microsoft Graph > [Test resource-specific consent permissions in Teams](graph-api/rsc/test-resource-specific-consent.md)|

For more information, see [public developer preview for Teams](~/resources/dev-preview/developer-preview-intro.md).

</details>
</br>

::: zone-end

::: zone pivot="dep-feature"

Discover Microsoft Teams platform features that are deprecated. You can now get latest Teams platform updates by subscribing to the RSS feed [![download feed](~/assets/images/RSSfeeds.png)](https://aka.ms/TeamsPlatformUpdates). For more information, see [configure RSS feed](#get-latest-updates).

## Deprecated

:::row:::
:::column:::

:::image type="icon" source="~/assets/images/deprecated.png":::

:::column-end:::
:::column span="2":::

Teams platform features that aren't available.

* ***February 07, 2025***: Support for Yeoman generator is deprecated from Teams developer documentation.

:::column-end:::
:::row-end:::

<details>
<summary><b>2024</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
| 01/17/2025 | Copilot plugin as a message extension in Teams meeting is deprecated. |
| 01/16/1015 | [Future-proof your app for third-party cookie deprecation across major browsers.](resources/samesite-cookie-update.md#third-party-cookies-deprecation) |
| 02/08/2024| The Collaboration controls for model-driven applications are retired. |  |
| 25/07/2024| Teams, Outlook, and Microsoft 365 web domains are migrating to `*.cloud.microsoft` domain. Configure your app before September 2024 to ensure continued functionality. | Extend your app across Microsoft 365 > Teams tabs in Microsoft 365 and Outlook > [Enable Teams personal tab for Microsoft 365](m365-apps/extend-m365-teams-personal-tab.md#configure-content-security-policy-headers) |
| 16/07/2024| The existing Microsoft 365 (previously called Office 365) connectors across all cloud platforms are nearing deprecation, and the creation of new Microsoft 365 connectors will soon be blocked. For more information on the schedule and how the Workflows app provides a more flexible and secure experience, see [retirement of Microsoft 365 connectors within Microsoft Teams](https://devblogs.microsoft.com/microsoft365dev/retirement-of-office-365-connectors-within-microsoft-teams/). | [Build webhooks and connectors](webhooks-and-connectors/what-are-webhooks-and-connectors.md) |
| 30/04/2024| In tab experiences, tab margins are deprecated. | |
| 12/04/2024| The `packageName` property is deprecated as part of app manifest v1.17. | |
| 10/04/2024| Location and Media APIs aren't supported in the new Teams client. We recommend using HTML5 Geolocation and Media. | Integrate device capabilities > [Integrate location capabilities](concepts/device-capabilities/location-capability.md#location-apis) and [Integrate media capabilities](concepts/device-capabilities/media-capabilities.md#media-capability-apis) |
| 10/04/2024| The `window.alert`, `window.confirm`, and `window.prompt` APIs used to display a dialog aren't supported in the [new Teams Client](resources/teams-updates.md#limitations). We recommended you to render a dialog within your own frame. | Resources > [Know about New Microsoft Teams client](resources/teams-updates.md#limitations)|
| 01/04/2024| Azure AD PowerShell is deprecated on March 30, 2024. To interact with Microsoft Entra ID, we recommend you to migrate to Microsoft Graph PowerShell. | [Microsoft Graph PowerShell overview](/powershell/microsoftgraph/overview)|
| 02/02/2024 | Teams, Outlook, and Microsoft 365 web domains are migrating to `*.cloud.microsoft` domain. Configure your app before June 2024 to ensure continued functionality. |Extend your app across Microsoft 365 > Teams tabs in Microsoft 365 and Outlook > [Enable Teams personal tab for Microsoft 365](m365-apps/extend-m365-teams-personal-tab.md#configure-content-security-policy-headers)|
| 02/02/2024 | The Collaboration controls for model-driven applications **are** set to retire by May 2024. We recommend removing the Collaboration controls and Collaboration connector from all Power Apps solutions and prepare users for the upcoming Collaboration controls retirement. | |

</details>

<details>
<summary><b>2023</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
| 05/05/2023| Adaptive Card tabs **will be** deprecated in the new Microsoft Teams. Apps are expected to be available in the new Microsoft Teams by June 2023. If your app is using Adaptive Card tabs, we recommend you to rebuild the tab as a web-based tab. | Build tabs > [Overview](tabs/what-are-tabs.md)|
| 17/05/2023 | Teams Toolkit v4 extension within Visual Studio Code **will be** deprecated. We recommend that you use Teams Toolkit v5 within Visual Studio Code for building your Teams app. | Tools and SDKs > Teams Toolkit for Visual Studio Code > [Teams Toolkit Overview](toolkit/agents-toolkit-fundamentals.md)|
| 11/10/2023 | Adaptive Card tabs **are** deprecated in the new Microsoft Teams. If your app is using Adaptive Card tabs, we recommend you to rebuild the tab as a web-based tab. | Build tabs > [Overview](tabs/what-are-tabs.md) |

</details>

<details>
<summary><b>2022</b></summary>

| **Date** | **Update** | **Find here** |
| -------- | --------- | ------------------ |
|01/08/2022 | App Studio is deprecated, use Developer Portal for Teams.| Tools and SDKs > Tools > [Developer Portal for Teams](concepts/build-and-test/teams-developer-portal.md)|

</details>

::: zone-end

## Teams app template catalog

Along with new features, we also provide [production-ready Teams app templates](samples/app-templates.md) that you can deploy right away or modify to your needs. Newly added templates are indicated with a star ☆.

## Submit your feedback

We encourage Teams developers to ask questions, file bugs, submit feature requests, and make contributions. You can submit feedback through any of the [available channels](feedback.md).

## Get latest updates

You can get the latest Teams platform updates by configuring to the [RSS feed](https://aka.ms/TeamsPlatformUpdates).

### To configure RSS feed

1. Open Teams.
1. Select **Teams** from the left pane.
1. Select a channel in the team.
1. Select ellipsis &#x25CF;&#x25CF;&#x25CF; and from the dropdown list, select **Connectors**.
1. Search for **RSS** in the **Connectors** dialog box that appears.
1. Select **Configure**.
1. Enter a name in **Enter a name for your RSS connection.**.
1. Enter **<https://aka.ms/TeamsPlatformUpdates>** in **Address for RSS feed**.
1. Select the frequency of the feed from the **Digest frequency** dropdown list.
1. Select **Save**.
