---
title: Copy of test 3 vis
deprecated: false
hidden: false
metadata:
  robots: index
---
Discover the prerequisites, a step-by-step guide to create an app push campaign, and detailed explanations for each section here.

<Callout icon="📘" theme="info">
  ### Prerequisites

  Integrate Netcore SDK in your application. Refer [here](https://cedocs.netcorecloud.com/docs/app) to integrate App SDK into your application
</Callout>

# Steps to Create App Push

Follow the steps to create an App push campaign.

1. Log in to the Netcore CE dashboard.
2. Click the **Create** button on the dashboard homepage.<br />OR<br />Navigate to **Engage** > **Campaigns** >  **Create**.
3. Select **Engage with users** > **App Push** under **Campaigns**.  Select the App push type you want to create. The available App push types are **Regular campaign**, **A/B Campaign**, **Split** and **Multi Message**.


<Image src="https://files.readme.io/3db93ee432dac864403d2b3d16880e9205024c7f59bf790e310543fe50f006b9-CreateAppPush-ezgif.com-crop.gif" alt="Create an App Push Notification" align="center" width="80% " caption="Create an App Push Notification" border={true} />


## Setup

<Accordion title="4. Setup: Add the campaign details here." icon="fa-gear">

Refer to the table below for details on the sections available under **Setup**.

| Sections          | Description                                                                                                                                                                               |
| :---------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Campaign Name** | Enter a unique name for this app push campaign.<ul><li>Maximum length: 255 characters</li><li>Allowed characters: alphanumeric, space, a hyphen, underscore, and ampersands (&)</li></ul> |
| **App(s)**        | Choose the app(s) where this notification will appear.                                                                                                                                    |
| **Add tags**      | Add relevant tags to organize and categorize this campaign. You can select up to five tags.                                                                                               |

Fill in all the required sections and proceed.

### Advanced Settings

<UTMParametersAppPush />

</Accordion>

## Audience

<Accordion title="5. Define the target audience for your campaign in the Audience section." icon="fa-users">

The **Audience** section lets you select who to target your App Push. It has the following sections:

### Target Audience

Choose a specific segment or list to define the audience for the App push campaign. Pick up to five user segments or lists. Use for targeting based on historical behavior captured by server-side user segments.


<Image src="https://files.readme.io/40d970c8a6c2a749816a481d0b2e15796eeb42587eadac1f49e56a877c8bf14f-TargetAudience.png" alt="Select your target audience for the campaign" align="center" width="80% " caption="Select your target audience for the campaign" border={true} />


**Target Audience** has the following options:

- **All Contacts**: Target all users in your contact list when creating campaigns.

<AllContactsEnableOrDisable />

- **Segments/List**: Select from existing lists or segments to target specific contacts. Search for the desired segment or list by name and add it to your campaign with a checkbox selection.
- **Ad-hoc segment**: This lets you instantly create segments, view user counts, and integrate them into your campaign targeting.
- **User data table (UDT)**: This is a specialized collection of contact information that includes additional attributes such as email addresses, physical addresses, and other personal details. UDT provides detailed information about contacts to help personalize and target campaigns.

### Exclude Contacts

Select suppression segments or lists to exclude specific users from campaign targeting. You can select up to 15 segments or lists for exclusion.


<Image src="https://files.readme.io/404ab392766a61f2fae90a0c33d4bdb446d74d8ae57e1e3af5d09b60fa41cf7e-ExcludeContactsAPN.png" alt="Exclude contacts from your campaign" align="center" width="60% " caption="Exclude Contacts from your Campaign" border={true} />


</Accordion>

## Content

<Accordion title="6. Create the content of the app push under the Content section." icon="fa-pen-to-square">

After the basic setup and defining the target audience, **Content** is the section where you can add the content for your campaign. You can **Create new layout**, use from **existing APN templates**, or select from the **Advance layouts** listed on this screen.

<Callout icon="👍" theme="okay">
  ### Use Your Active Brandkit

  Ensure you have a Brandkit enabled and active to use it while creating **App Push campaign content**. Refer [here](https://cedocs.netcorecloud.com/docs/setup-brand-kit) to learn how to enable and setup Brandkit.
</Callout>

Several layouts are available to suit your message and audience. Here is an explanation of each layout.

| Layout                 | Description                                                                                                                 | Use Case                                                             |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------- |
| **Overlay on Image**   | This layout allows you to display a message over an image.                                                                  | Promote a new product with a captivating image and a call to action. |
| **Timer**              | This layout allows you to add a countdown timer to create urgency.                                                          | Notify users that a flash sale will be ending soon.                  |
| **Carousel** (**E2E**) | This layout lets users swipe through multiple images or messages.                                                           | Showcase a series of related products or features.                   |
| **Edge to Edge**       | This layout allows you to expand the notification to cover the entire width of the screen.                                  | Highlight a major update or announcement with maximum visibility.    |
| **Rating**             | This layout allows you to include a rating option for quick feedback.                                                       | Ask users to rate their experience after completing a purchase.      |
| **Small Image**        | This layout allows you to show a small image alongside the notification text.                                               | Share a product image with a quick update or offer.                  |
| **Progress Bar**       | This layout allows you to display a bar indicating progress toward a goal.                                                  | Inform users of their progress in a download or achievement.         |
| **Multi icon**         | This layout allows you to display multiple icons within a single notification to represent different actions or categories. | Show multiple options or features at a glance.                       |
| **Quick reply**        | This layout enables users to respond instantly from the notification using predefined reply options.                        | Let users respond quickly without opening the app.                   |
| **Product set**        | This layout allows you to showcase a set of products within a single notification, each with its own image and action.      | Highlight multiple products in a single notification.                |

<Callout icon="📘" theme="info">
  ### Using Timer and Progress Bar in Journeys

  Ensure to follow these points while using **Timer** and **Progress Bar** layouts.

  - The journey end time must be less than or equal to the timer or progress bar end-time.
  - The timer can run for a maximum of 24 hours. If the journey exceeds this, users may receive expired timer notifications.
  - The **TTL** (**Time To Live**) must not exceed the timer or progress bar endtime. If it does, notifications may be delivered after the timer has expired, showing the timer end message to users.
</Callout>

When you create or select an Advanced layout, the **Customize Your Template** screen appears. Here, you can add and customize app push notification content. The left pane updates the mobile preview on the right, showing how it will appear to users.


<Image src="https://files.readme.io/4dc6310586be8ac952f7215ec63b42c76f2816ec9474ba2d1c2f292e8986fd23-CustomizeAPNTemplate-ezgif.com-crop.gif" alt="Customize your App Push Template" align="center" width="80% " caption="Customize your App Push Template" border={true} />


Toggle on **Enable APN Interactions** to include rich media elements, action buttons, sound, deep links, and more.


<Image src="https://files.readme.io/daf0d9b5832229e356e9b3b6703b4eb06c376eb38d2adaf8976b2cedfa88b4b2-EnableAPNInteractions.png" alt="Enable APN Interactions to include rich media, sound and so on" align="center" width="50% " caption="Enable APN Interactions to include rich media, sound, and so on" border={true} />


Refer to the table below to learn about all the options available to customize your app push template.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Options
      </th>

      <th>
        Descriptions
      </th>

      <th>
        Available for
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Title**
      </td>

      <td>
        Allows you to add the title of your push notification. You can also add formatting such as bold, italics, underline, text color, and background color here.<br />📘 Text formatting is supported only on Android SDK.
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar, Multi-icon, Quick reply, Product set
      </td>
    </tr>

    <tr>
      <td>
        **Description**
      </td>

      <td>
        Allows you to add the message content of your push notification.
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar, Multi-icon, Quick reply, Product set
      </td>
    </tr>

    <tr>
      <td>
        **Landing page**
      </td>

      <td>
        Allows you to redirect the user to your preferred location when the user clicks the notification. The options available here are: <ul><li>**Deeplink**: Opens directly within a specific app section.</li><li>**URL**: Opens in any app or browser location.</li><li>**App landing page**: The main entry or home page of the app.</li></ul>
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar, Multi-icon, Quick reply, Product set
      </td>
    </tr>

    <tr>
      <td>
        **Copy from iOS/Android**
      </td>

      <td>
        Copy common content between Android and iOS while configuring your push notification. Refer [here](https://cedocs.netcorecloud.com/docs/create-app-push-copy-1#copy-from-iosandroid) to know more.
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        **Add Image**
      </td>

      <td>
        Allows you to insert an image.<br />**Upload File**: Drag and drop the file or select it from your computer.<br />**Media URL**: Allows you to add an image URL.<br />📘 PNG and JPEG file formats are supported.<br />URL must include an HTTPS protocol ending with a supported file format. Example: [https://website.com/image.png](https://website.com/image.png)
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar
      </td>
    </tr>

    <tr>
      <td>
        **Overlay Color**
      </td>

      <td>
        Allows you to customize the color applied to the background overlay behind an app push.
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar
      </td>
    </tr>

    <tr>
      <td>
        **Background Color**
      </td>

      <td>
        Allows you to set the background color. Add a solid color or use a gradient option to define a two-colored gradient effect.
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar
      </td>
    </tr>

    <tr>
      <td>
        **Sticky Notification**
      </td>

      <td>
        A notification that stays visible until the user clicks \<image src="https\://files.readme.io/5343df9db6f0b2467c723c746a5a51bf90fe5e23ebef3dea6f9b997632f91a18-CloseButton.png" style="display:inline-block; margin:0; padding:0; width:20px; height:auto;">\<image> button. It cannot be removed by swiping or using the **Clear All** option in the notification tray.

        **Note**: The notification can be dismissed if the user's device has Android 14 or later installed. For more details, refer to the [official Android update](https://developer.android.com/about/versions/14/behavior-changes-all#non-dismissable-notifications).
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar
      </td>
    </tr>

    <tr>
      <td>
        **Sound**
      </td>

      <td>
        Define the tone played when a notification arrives on the device. You can choose between the default device sound or a custom sound.

        Here are the requirements for setting a custom sound: <ul><li>**Android Versions Below 8**: Enter the sound file name in your app bundle. Supported formats are .mp3, .ogg, and .wav.</li><li>**Android Versions 8 and Above**: Enter the name of the notification channel ID. For setup instructions, refer to the [notification channel documentation](https://developer.netcorecloud.com/docs/android-setup-notification-channel).</li><li>**iOS**: Enter the sound file name included in your app bundle. Supported formats are .aiff, .wav, and .caf.</li></ul>

        📘 The sound file name must be in your app bundle. If it is missing, the device will play the default sound.
      </td>

      <td>
        Overlay on image, Timer, Carousel (E2E), Edge to edge, Rating, Small image, Progress Bar
      </td>
    </tr>

    <tr>
      <td>
        **Carousel Type**
      </td>

      <td>
        This option allows you to select between **Manual** and **Automatic** carousel transitions. In **Automatic**, set the timer for image transitions between 2 and 10 seconds.<br />📘 Ensure the important part of the image is not in the lower portion. Users can add up to five images with a 2:1 aspect ratio and a maximum file size of 40KB.
      </td>

      <td>
        Carousel (E2E)
      </td>
    </tr>

    <tr>
      <td>
        **Text/Emoji**
      </td>

      <td>
        Allows you to add words or emojis as rating options.
      </td>

      <td>
        Rating
      </td>
    </tr>

    <tr>
      <td>
        **Rating Scale**
      </td>

      <td>
        Allows you to select the number of rating options to provide between two, three, or five.
      </td>

      <td>
        Rating
      </td>
    </tr>

    <tr>
      <td>
        **Timer Settings**
      </td>

      <td>
        <li><strong>Timer date and time</strong>: Set the exact date and time when the timer will end.</li><li><strong>Message after timer ends</strong>:Enter the message that will display after the timer has finished.</li><li><strong>Add URL</strong>: Provide a URL for an audio clip that will play with the timer.</li>
      </td>

      <td>
        Timer
      </td>
    </tr>

    <tr>
      <td>
        **Progress Bar Settings**
      </td>

      <td>
        <li><strong>End date & time</strong>: Select when the progress bar reaches completion.</li><li>Maximum and minimum time allowed: Set the timer duration between one hour and 24 hours.</li><li><strong>Message after the timer ends</strong>: Specify the message that will replace the timer text once the progress bar is completed.<strong>Local time display</strong>: Timer will automatically adjust to the user’s local time zone.</li>
      </td>

      <td>
        Progress Bar
      </td>
    </tr>
  </tbody>
</Table>

Toggle on **Add-on options** to enable custom key value and collapse notifications.


<Image src="https://files.readme.io/486042ea708fbab475603257f5ed717343575e034f12d99c03ee22861bbf1950-AddOnOptions.png" alt="Enable custom key value and collapse notifications" align="center" width="80% " caption="Enable custom key value and collapse notifications" border={true} />


- **Collapse Notification**

This feature is used by FCM (Firebase Cloud Messaging) and APNS (Apple Push Notification Service) to update older notifications that have already been delivered. When multiple notifications share the same collapse key, only the most recent one will appear in the user's notification tray.<br />For example, if you send a series of cricket match score updates, you can set **score_updates** as the collapse key. This ensures that only the latest score update is visible in the user's notification tray.

- **Custom Key-Value Pairs**

In this section, you can define custom key-value pairs specific to the operating system. These pairs trigger actions within the app when a user interacts with a notification, enabling personalized experiences.<br />For example, a shopping app can use a key-value pair like **Key**: category and **Value**: shoes to direct users to the shoes section when they click a notification about a shoe sale.

<Callout icon="📘" theme="info">
  ### Note

  - At least one operating system must be selected.
  - You can add up to 49 key-value pairs
</Callout>

# Copy From iOS/Android

To make App Push creation faster and more flexible, you have the option to copy common content between Android and iOS while configuring your push notification. This enhancement removes dependency to manually duplicate the same content across platforms.

<Callout icon="👍" theme="okay">
  ### Important Points to Remember

  - Choose both an Android and an iOS app while setting up campaign to enable **Copy from Android/iOS** option.
  - When copying content between platforms, only field values are copied. Field **enablement** or **disablement** is not synced. For exampIe, if a field is disabled on Android but enabled on iOS, it will remain enabled on iOS after using Copy from Android.
</Callout>

### Steps to enable copy to iOS/Android

1. Configure content on one platform (Android or iOS).
2. Switch to the other platform tab.
3. Click Copy from Android or Copy from iOS and confirm the action in the modal.

_Copying content overwrites common fields in the destination platform._ Refer to the table below to understand which set of content can be copied:

| Category                  | Fields                                                                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Common content fields** | <ul><li>Title</li><li>Subtitle</li><li>Body message</li><li>Image / GIF URL</li><li>Background color</li><li>CTA text</li><li>CTA URL / action link</li></ul> |
| **Carousel card fields**  | Card title<li>Card description<li>Card image URL<li>Card CTA                                                                                                  |

Refer to the table below to understand which set of content cannot be copied and has to be manually entered:

| Category                       | Fields                                                                                                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Platform-specific settings** | Android sound settings<li>Sticky notification (Android)<li>Collapsed state customization (Android)<li>Android add-on or advanced options<li>Any other platform-exclusive configurations |

### Send Test Notification

Select the **Send Test Notification** option to preview your app push before sending it to users. You can send a test push notification to users using either the push token ID or the primary key.


<Image src="https://files.readme.io/ce8e3e74b93077c88448efcc8dcf4dddd08b5f0a69864c2b2b06d4e6cd842547-TestCampaign.png" alt="Send Test Notification to your device" align="center" width="80% " caption="Send Test Notification to your device" border={true} />


Refer to the table below for details on the sections under **Send Test Notification**.

| Field Name                | Description                                                                                                                                                   |
| :------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Test with Primary Key** | Send the notification to a user identified by their primary key. This method helps test how the notification appears for that specific user.                  |
| **Test with Push Token**  | Obtain a push token from your development support team to test notifications on a specific device. This allows you to verify delivery directly on the device. |

<Callout icon="📘" theme="info">
  ### Note

  Test notifications are excluded from campaign statistics.
</Callout>

</Accordion>

## Schedule

<Accordion title="7. Define the campaign's delivery time and date under the Schedule section." icon="fa-calendar">

You can create and preview your App Push campaign and then schedule your campaign.


<Image src="https://files.readme.io/cc5587fc0f6b3f61ebe5c7df71e22f86c4ef40b42c4de5ee4f7944d43fe4e73c-ScheduleAPN.png" alt="Schedule your App Push" align="center" width="80% " caption="Schedule your App Push" border={true} />


Refer to the table below for details on the sections under **Schedule campaign**.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Frequency cap**
      </td>

      <td>
        Turn on the frequency cap to limit the app push notifications a specific user can receive. Refer to  [ frequency capping](https://cedocs.netcorecloud.com/docs/frequency-capping) to learn more about the setting.
      </td>
    </tr>

    <tr>
      <td>
        **When to send**
      </td>

      <td>
        Select the options for when you want your app push campaign to be sent.<ol><li>**Send now**: Immediately send the app push campaign to users.</li><li>**Send Later**: Schedule the app push campaign to be sent at a specified date and time.</li><li>**Optimise with Raman**: Use our AI engine Raman to optimize the send time based on user engagement metrics.</li></ol>
      </td>
    </tr>

    <tr>
      <td>
        **Time to Live (TTL)**
      </td>

      <td>
        TTL determines how long FCM will store and try to deliver your notification. <ol><li>**Specific Date and Time**: Set TTL with a specific date and time up to 28 days in the future.</li><li>**Immediate Delivery**: Set TTL to zero seconds for immediate delivery. FCM will not reattempt notifications. Provide a campaign cut-off time for this option.</li></ol>
      </td>
    </tr>

    <tr>
      <td>
        **Schedule and deliver notifications locally on mobile devices**
      </td>

      <td>
        Select this option to schedule push notifications directly on users' devices. When enabled, it ensures notifications are sent to almost 100% of your active users. Active users are those who come online from the time an app push campaign is scheduled until it is set to display on their device. Notifications can be delivered through **FCM** and **Push Amplification** if the user comes online during the scheduled period.

        **Points to remember**: <ol><li>This options is only avilable when you select **Send later** option..</li><li> Schedule your campaign 24 hours before using this feature.</li><li> When local notifications are stored on a user's device, they cannot be recalled if the campaign is suspended.</li></ol>
      </td>
    </tr>

    <tr>
      <td>
        **App Inbox**
      </td>

      <td>
        Send a copy of the push notification to the App Inbox. This ensures that users who miss a notification can access it later in the notification section of the app. <ol><li>**Message Category**: Choose a category for the notification to help users organize and find messages easily.</li><li>**Message Expiry Time**: Set an expiry time for the message in the App Inbox, after which it will no longer be accessible.</li></ol>
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  ### Important

  Running two consecutive campaigns within 30 minutes, the time frame could bypass the frequency cap check due to data synchronization delay.

  For example, if you schedule one app push at 12:00 pm and another at 12:30 pm with a frequency cap limiting users to one app push per day. In this case, the second push notification may not reach users due to the frequency cap settings.
</Callout>

</Accordion>

8. Click the **Preview** option to save your campaign and preview the app push. Once you have checked the details and appearance of your entire app push, click **Save & Publish** to publish it.

<br />