---
title: 'test '
deprecated: false
hidden: false
metadata:
  robots: index
---
Fourthline's App Drop-in lets you smoothly integrate workflows into your mobile app. It takes care of all interaction with the client, collects the relevant data (e.g. ID document, selfie, geolocation), and uploads it to Fourthline for <Glossary>case processing</Glossary>. You never handle sensitive <Glossary>personal data</Glossary> .

The SDK takes care of the user journey and orchestrates modules with a streamlined API flow. You can also easily level up from single products to multi-product solutions with **no** additional API requests.

All required images and data are captured in our best-practice <Glossary>UI</Glossary>  and automatically uploaded to Fourthline for processing. You never handle sensitive <Glossary>personal data</Glossary>.

## How it works

The App Drop-in supports the following:

| SDKs                                                                                   | Solutions & modules                                                                                                   |
| :------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------- |
| [Android SDK](https://docs.fourthline.com/docs/app-drop-in-setup-android)              | [Identity Verification](https://docs.fourthline.com/docs/idv-solutions)                                               |
| [iOS SDK](https://docs.fourthline.com/docs/app-drop-in-setup-ios)                      | [Qualified Electronic Signature](https://docs.fourthline.com/docs/qes-overview)                                       |
| [Cordova plugin](https://docs.fourthline.com/docs/app-drop-in-setup-cordova)           | [Bank Account Verification](https://docs.fourthline.com/docs/bav-overview)                                            |
| [Flutter plugin](https://docs.fourthline.com/docs/app-drop-in-setup-flutter)           | [Client Authentication](https://docs.fourthline.com/docs/authentication-solutions#biometric-authentication-solution)  |
| [React Native plugin](https://docs.fourthline.com/docs/app-drop-in-setup-react-native) | [Document Authentication](https://docs.fourthline.com/docs/authentication-solutions#document-authentication-solution) |

***

## Flow

The flow is as follows:

<img src="https://files.readme.io/a35d0c1-AppDrop-in_HowItWorks.png"
alt="App Drop-in flow"
style={{width: '100%', border: "1px solid #e4e7ec", borderRadius: "8px"}} />

<p align="center"><em>App Drop-in flow</em></p>

***

## User interface

Fourthline provides the mobile-responsive <Glossary>UI</Glossary> , which is built in line with industry-standard best practices for user experience (UX):

- The UI includes guidance and animations to help clients understand the journey.
- Clients may not know how to take photos with appropriate lighting, background, and framing, which can lead to processing delays or unnecessary rejections. The UI provides clients clear instructions and real-time feedback to optimize image quality and maximize conversion.
- The UI validates data entered by clients in real time to reduce input errors.
- You can localize the UI text in a range of languages, and customize fonts and colors to match the look-and-feel of your brand.
- Fourthline collects analytics data and continually updates the UI to improve conversion, meet evolving regulatory requirements, and keep pace with market trends in UIs and UX.

<div class="call-out call-out__note">
  <div class="call-out--icon">
    <img src="https://files.readme.io/ad2486a-Inline_Note.svg" alt="Note" />
  </div>

  <div>
    <div class="call-out--title">Note</div>
    <div class="call-out--text">Fourthline ensures photos are taken <strong>during</strong> the workflow, in compliance with art. 41b of the European Banking Authority – <a href="https://www.eba.europa.eu/sites/default/files/document_library/Publications/Guidelines/2022/EBA-GL-2022-15%20GL%20on%20remote%20customer%20onboarding/1043884/Guidelines%20on%20the%20use%20of%20Remote%20Customer%20Onboarding%20Solutions.pdf">Guidelines on the use of Remote Customer Onboarding Solutions under Article 13(1) of Directive (EU) 2015/849</a>.</div>
  </div>
</div>

***

## How to integrate

See below for integration and configuration guidance.

### Configuration

For configuration and setup instructions, see the relevant manual:

- [Android SDK](https://docs.fourthline.com/docs/app-drop-in-setup-android)
- [iOS SDK](https://docs.fourthline.com/docs/app-drop-in-setup-ios)
- [Cordova Plugin](https://docs.fourthline.com/docs/app-drop-in-setup-cordova)
- [Flutter Plugin](https://docs.fourthline.com/docs/app-drop-in-setup-flutter)
- [React Native Plugin](https://docs.fourthline.com/docs/app-drop-in-setup-react-native)

### Integration manuals

For step-by-step integration manuals per solution, see the relevant integration guide:

- [Identity Verification](https://docs.fourthline.com/docs/idv-integration-app)
- [Qualified Electronic Signature](https://docs.fourthline.com/docs/qes-integration-app)
- [Bank Account Verification](https://docs.fourthline.com/docs/bav-integration-app)

### UI customization

For how to customize the <Glossary>UI</Glossary> , see [App UI Customization](https://docs.fourthline.com/docs/app-ui).<br />

### Duplicate submissions prevention

To prevent duplicate submissions, after a client completes the App drop-in flow, **always verify the workflow status** before allowing a new workflow to be launched. This prevents duplicate submissions and inconsistent workflow states.

<div class="call-out call-out__note">
  <div class="call-out--icon">
    <img src="https://files.readme.io/ad2486a-Inline_Note.svg" alt="Note" />
  </div>

  <div>
    <div class="call-out--title">Note</div>
    <div class="call-out--text">Store the `workflowId` returned when the workflow is first created and reuse it to check the status.</div>
  </div>
</div>

#### How it works

1. Make a [GET case status](https://docs.fourthline.com/reference/get-case-status) request.
2. Read the `verificationStatus` value from the response.
3. **Do not allow a new workflow launch** if the status is one of the following:

| Status      | Description                       |
| ----------- | --------------------------------- |
| `completed` | Workflow finished successfully    |
| `pending`   | Workflow is still being processed |
| `rejected`  | Workflow was rejected             |

Only allow a new workflow to be launched when the status is `new` or another non-terminal state.

#### UI guidance

From a UI perspective:

- Disable the launch button when the workflow status is `completed`, `pending`, or `rejected`.

- Clearly explain why the client cannot continue (for example, _Your verification is still being processed_).

- Re-enable the launch option only when the workflow is eligible to be restarted.

<div class="call-out call-out__support">
  <div class="call-out--icon">
    <img src="https://files.readme.io/372d218-Inline_Support.svg" alt="Support" />
  </div>

  <div>
    <div class="call-out--title">Support</div>
    <div class="call-out--text">For any questions, contact your Fourthline delivery manager.</div>
  </div>
</div>

<br />

<HTMLBlock>{`
<!doctype html>
<html>
<head>
<meta charset="utf-8">
</head>
<body style="width: 100%; background-color:white;">
<title>Accordion in HTML5</title>
<style>

details {   
  padding:1.2em 1.2em 0;
  margin-bottom: 2em;
  background-color: #F5F5F5;
}

summary {	
  font-weight: 500;
  margin: -1.6em -1.2em 0;
  font-size: 1em;
  padding: 1.2em;
  background-color: #F5F5F5;
  color: #4F5065;
  border-bottom: 1px solid #00000022;
}

details[open] {
	border-bottom: 2px solid #4D55EB;
  padding-bottom: 2em;
}

details[open] summary {
  border-bottom: hidden;
  color:#4D55EB;
}

</style>
</body>
</html>
`}</HTMLBlock>

<br />
