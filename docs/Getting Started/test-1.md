---
title: 'test 1 '
deprecated: false
hidden: false
metadata:
  robots: index
---
---
title: RCS Text Template
deprecated: false
hidden: true
metadata:
  robots: index
---

To delete, click the <i class="fa-solid fa-trash" /> icon and then press save

You can send a simple, plain-text message to one or more recipients using the Text template. It is ideal for sending basic notifications, alerts, or transactional messages without any formatting or media.

You can send interactive suggestions, such as replies and actions. You can add chips such as:

* **URL Action** - Add a URL to the text template.
* **Reply** - Add a reply message to the RCS text template. This message helps the end user set the context for their reply. If they click the reply message provided while creating a template, the same message is received by the sender.
* **Dialer Action** - Add a phone number that end users can use to contact you.
* **View Location (Lat/Long)** - Add a location to the text template.
* **Create Calendar Event** - Create an event and share the date in a text template.

To create an RCS text template, perform the following steps:

1. Follow steps 1 through 3 in the [Add a New Agent](https://developers.kaleyra.io/docs/rcs-agents-add-a-new-agent) topic.  
   The **Agents** dashboard page appears.

<Image align="center" border={true} src="https://files.readme.io/70fa5cbca8bc92ff92e0cfc0f8f3397bce23acdfec5043893c6fdcfe3e4fe88e-add_template.png" className="border" />

2. Click the agent for which you want to add the template.

<Image align="center" border={true} src="https://files.readme.io/be83ae40d0184c55bf6c663712b133af6b918977b171bd1a8db0eb0cbdaed652-add_template_1.png" className="border" />

3. From the left menu bar, click **Templates**.  
   The **Template Details** step appears.

<Image align="center" border={true} src="https://files.readme.io/16897fcaa372fcb8da47c711d92b70237e46802068e67ffce775ec803a8bd095-add_template_3.png" className="border" />

4. In the **Template Details** section, perform the following:
   1. In the **Enter Template Name** field, enter the template name. Only alphanumeric characters are supported, up to a maximum of 20 characters.

test text /e

<Callout icon="❗️">

</Callout>

4. In the **Select Type** drop-down field, click the drop-down button, and then select the **Text** option.

<Image align="center" border={true} src="https://files.readme.io/1bc709e7b6ac4ecc78821cabe5d97eb8542c904ad742ad1eabbf1b259f6977bc-add_template_4.png" className="border" />

5. Click **Next**.  
   The **Add Content** step appears.

<Image align="center" border={true} src="https://files.readme.io/0ad40fd78501459e8bc6efcd89e177b3169eb8eb0c1496c2718f09ed59101211-add_template_5.png" className="border" />

<Callout icon="📘" theme="info">
  **Notes**:

  * From the right side of the page, in mobile view, you can preview the RCS template message to be delivered to end users.
  * From the right side of the page, in mobile view, click the Business Info tab to view the agent's business information.
</Callout>

6. The body component represents the core text of your RCS text message template and is a text-only template component; rich content is not supported. Templates are limited to one body component. In the **Message Content** field, enter the content for the text template. You can use dynamic variables to insert data into your template. Add dynamic variables by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. You can add emojis by clicking the emoji icon and selecting them from the pop-up. Enter the variable details. A maximum length of 3072 characters is supported for the message content.

<Image align="center" border={true} src="https://files.readme.io/8095776ebfe0a168c9dce17628eb203463dd6ad466396f24da5f26ca9a449187-add_template_6.png" className="border" />

7. Click **+ Add Chips**.  
   The **Button 1** section appears.

<Image align="center" border={true} src="https://files.readme.io/f9d07573dd3e8bd68733f6eea10e1e775d2fd1a0b946b1d909d0cc4050c1ba39-add_template_7.png" className="border" />

8. From the **Select Type** field, click the drop-down icon, and then select one of the following options:

<Accordion title="URL Action" icon="fa-link">
  <img src="https://files.readme.io/16dd92cf55916f89a8892c79ee2c526d84375d57614138fcce883c59f09f29de-add_template_8.png" />

  i. In the <b>Enter Text</b> field, enter the text for the URL that you want to display in the message. Use the dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. The maximum length of 25 characters is supported.<br />

  ii. In the **Enter Postback** field, enter the content you want to capture as a log event when the URL is clicked. Use the dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. The maximum length of 120 characters is supported. <br />

  iii. In the <b>Enter URL</b> field, enter the URL to which you want to redirect your end users. The maximum length of 2048 characters is supported. <br />

  <img src="https://files.readme.io/eaf84264c1743f02dc262f92326c9beadae9c133bfa82cb959d202f25d13645f-add_template_9.png" />

  <b>Notes</b>:

  <li> To add more than one chip to a template, click the <b>Add Chips</b> button.</li>
  <li> If you have multiple chips, click the up or down icon on the top-right of the <b>Button</b> section to change the chip order. </li>
  <li> To delete an added chip, click the <b>Delete</b> icon on the top-right of the <b>Button</b> section. </li>
</Accordion>

<Accordion title="Reply" icon="fa-comments">
  <img src="https://files.readme.io/925cdfc8437a7711503d464a579d169349e4ef0b1a4a8ed73e96cb3ed2bcbb1f-add_template_10.png" />

  i. In the <b>Enter Text</b> field, enter the reply text that you want to display in the message. This reply message helps the end user set the context for their reply. If they click the Reply message provided while creating a template, the same message is received, and the conversation starts. Use dynamic variables inside the template by clicking the <b>+</b> icon on the bottom-left of the Enter Content field. The new `{{custom_params}}` variable appears. <br />

  ii. In the **Enter Postback** field, enter the content you want to capture as a log event when the reply is clicked. Use dynamic variables inside the template by clicking the + icon on the bottom-left of the Enter Content field. The new `{{custom_params}}` variable appears. <br />

  <img src="https://files.readme.io/c8aee98f5b6da53d10770d4e1db573b0160281b0e0f9c4b081d6e52a2fb58fe1-add_template_11.png" />

  <b>Notes</b>:

  <li> To add more than one chip to a template, click the <b>Add Chips</b> button.</li>
  <li> If you have multiple chips, click the up or down icon on the top-right of the <b>Button</b> section to change the chip order. </li>
  <li> To delete an added chip, click the <b>Delete</b> icon on the top-right of the <b>Button</b> section. </li>
</Accordion>

<Accordion title="Dialer Action" icon="fa-phone">
  <img src="https://files.readme.io/3a0e68eb17a1cd2c753f1dce4f5030ab9689c7b462c81798111b1a886318c2d8-add_template_12.png" />

  i. In the <b>Enter Text</b> field, enter the text for the <b>Dialer Action</b> that you want to display in the message. Use dynamic variables inside the template by clicking the <b>+</b> icon on the bottom-left of the <b>Enter Content</b> field. The new `{{custom_params}}` variable appears. <br />

  ii. In the <b>Enter Postback</b> field, enter the content you want to capture as a log event when the <b>Dialer Action</b> is clicked. Use dynamic variables inside the template by clicking the <b>+</b> icon on the bottom-left of the <b>Enter Content</b> field. The new `{{custom_params}}` variable appears. <br />

  iii. In the <b>Country Code</b> drop-down field, click the drop-down icon and then select the country code for your phone number.

  iv. In the <b>Enter Phone Number</b> field, enter the phone number by which the end-user can contact you.

  <img src="https://files.readme.io/26838d8e5b50656d1741ec72e0d731e88358cfd9e1a513652a4023c9726a45b2-add_template_13.png" />

  <b>Notes</b>:

  <li> To add more than one chip to a template, click the <b>Add Chips</b> button.</li>
  <li> If you have multiple chips, click the up or down icon on the top-right of the <b>Button</b> section to change the chip order. </li>
  <li> To delete an added chip, click the <b>Delete</b> icon on the top-right of the <b>Button</b> section. </li>
</Accordion>

<Accordion title="View Location (Lat/Long)" icon="fa-location-crosshairs">
  <img src="https://files.readme.io/1f2b9450d65243e247ca591f47e214247459c56d2981cabb66fd4cf927652b3a-add_template_14.png" />

  i. In the <b>Enter Text</b> field, enter the text for <b>View Location (Latitude/Longitude)</b> that you want to display in the message. Use dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. <br />

  ii. In the **Enter Postback** field, enter the content you want to capture as a log event when View Location (Latitude/Longitude) is clicked. Use dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. <br />

  iii. In the **Enter Latitude** field, enter the latitude for your location.

  iv. In the **Enter Longitude** field, enter the longitude for your location.

  <img src="https://files.readme.io/2b510772ce5f3c54a4feba4663d2897928cda8bc89015e8279350cd5436c723b-add_template_15.png" />

  <b>Notes</b>:

  <li> To add more than one chip to a template, click the <b>Add Chips</b> button.</li>
  <li> If you have multiple chips, click the up or down icon on the top-right of the <b>Button</b> section to change the chip order. </li>
  <li> To delete an added chip, click the <b>Delete</b> icon on the top-right of the <b>Button</b> section. </li>
</Accordion>

<Accordion title="Create Calendar Event" icon="fa-calendar">
  <img src="https://files.readme.io/919dcd457a255e6b7680020e297347df3a4a337093a8c34360387420a4418a23-add_template_16.png" />

  i. In the <b>Enter Text</b> field, enter the text for the <b>Create Calendar Event</b> that you want to display in the message. Use dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. <br />

  ii. In the **Enter Postback** field, enter the content you want to capture as a log event when the <b>Create Calendar Event</b> is clicked. Use dynamic variables inside the template by clicking the **+** icon on the bottom-left of the **Enter Content** field. The new `{{custom_params}}` variable appears. <br />

  iii. In the **Enter Event Title** field, enter the title for your event.

  iv. In the **Enter Description** field, enter the description for your event.

  v. In the **Enter Event Start Date & Time** field, enter the event's start date and time.

  vi. In the **Enter Event End Date & Time** field, enter the event's end date and time.

  <img src="https://files.readme.io/0b7f4ff3a0a959d7248043a4dd5bfcf4a60dad034cf2152bc2aab0189179fb84-add_template_17.png" />

  <b>Notes</b>:

  <li> To add more than one chip to a template, click the <b>Add Chips</b> button.</li>
  <li> If you have multiple chips, click the up or down icon on the top-right of the <b>Button</b> section to change the chip order. </li>
  <li> To delete an added chip, click the <b>Delete</b> icon on the top-right of the <b>Button</b> section. </li>
</Accordion>

<Image align="center" border={true} src="https://files.readme.io/ddfa9869cfff2892c25cf69a9b4e7542ff12ef7eaa6dcb9291c1b75379685e16-add_template_19.png" className="border" />

9. Click **Next**.  
   The **Preview** step appears with template details.

<Image align="center" border={true} src="https://files.readme.io/bef778874ee9194552e024f1579de216a87d40a4196af4d78f14e4f4d96fc1df-add_template_20.png" className="border" />

10. Click **Save**.  
    The **Activate template** pop-up appears.

<Image align="center" border={true} src="https://files.readme.io/0f3381f78830710d28faf6b5185c757a0923ed011d9eec767639dee43b3d65e1-add_template_21.png" className="border" />

11. Select one of the following options:

* **Activate Now** - Activate the template immediately. After successful template approval, the **Status** of the template will be **Approved**.

  <Image align="center" border={true} src="https://files.readme.io/3cd6c2b839363203c829f5814cf8e4954e47bfd680e969e9d027d4a03487c6e7-add_template_22.png" className="border" />
* **Activate Later** - Create the template. After selecting the **Activate Later** option, the status of the template will be **Created**. You can send the template for approval later. For more information, see [Send Template for Approval](https://developers.kaleyra.io/docs/rcs-send-template-for-approval).

  <Image align="center" border={true} src="https://files.readme.io/5a0ca87fe37a7d44082e81c0ab9cf3d0bcb792993083faa270708251511c77bd-add_template_23.png" className="border" />
