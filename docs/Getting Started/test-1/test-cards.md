---
title: test Cards
deprecated: false
hidden: false
metadata:
  robots: index
---
<Callout icon="🚧" theme="warn">
  ## Coming soon

  We are introducing a new JSON-based styling tool for the Web SDK to simplify customization and reduce reliance on CSS.

  This will replace the current CSS-based approach over time. Documentation will be updated soon.

  In the meantime, please contact your customer success manager to request a JSON styling file.
</Callout>

This page sets out how to customize the Web SDK <Glossary>UI</Glossary> to match the look and feel of your brand.

<Cards kind="tile">
  <Card title="Setup" href="/docs/web-ui" />
  <Card title="Fonts" href="/docs/web-ui-fonts" />
  <Card title="Colors" href="/docs/web-ui-colors" />
  <Card title="Layout" href="/docs/web-ui-layout" />
</Cards>

<Card color="#ff0000" href="#" icon="fa-rocket" title="Getting Started">

## Setup

The SDK is built with [web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) and styles them using a styles file containing [CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) and `@font-face` definitions. The SDK automatically loads the file each time it is triggered.

Follow these steps:

1. Create the styles file following the guidance below, or ask Fourthline to create it for you.

2. Share the file with your Fourthline delivery manager along with your [logo](https://docs.fourthline.com/docs/web-ui-layout#logos) in SVG format.

<div class="call-out call-out__tip">
  <div class="call-out--icon">
    <img src="https://files.readme.io/8eb9022-Inline_Tip.svg" alt="Tip" />
  </div>

  <div>
    <div class="call-out--title">Tip</div>
    <div class="call-out--text">To update the file at any point, contact your Fourthline delivery manager.</div>
  </div>
</div>

***

### Flows

- `fl-flow-onboarding`: The [redirect flow](https://docs.fourthline.com/docs/web-sdk#redirect-flow) styles are hosted by you.
- `fl-flow-verify`: The [product flow](https://docs.fourthline.com/docs/web-sdk#flow) styles are hosted by Fourthline.

Usually, both flows share the **same** styles.

***

### Localization

For how to set the language and level of formality, see Web SDK Setup – Embedding manual > [Localize the UI](https://docs.fourthline.com/docs/web-embedding#3-localize-the-ui).

***

### Example

The following is an example of a complete styles file, using a [third-party font service](#third-party-service):

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@400;500&family=Roboto+Mono:wght@400;500&family=Roboto:wght@400;500&display=swap');

fl-flow-verify, fl-flow-onboarding {
  --fl-font-family: 'Roboto', system-ui, sans-serif;
  --fl-font-family-header: 'Roboto Slab', serif;
  --fl-font-family-monospace: 'Roboto Mono', monospace;

  --fl-color-light: snow; 
  --fl-color-info: dodgerblue; 
  --fl-color-primary: mediumvioletred; 
  --fl-color-accent: var(--fl-color-info);

  --fl-input-border-radius: 8px; 
  --fl-button-border-radius: 28px; 

  --fl-button-disabled-color: var(--fl-color-primary);
  --fl-button-disabled-background-color: var(--fl-background-color);
  --fl-button-disabled-border-color: var(--fl-color-primary);
  --fl-button-disabled-opacity: 1;

  --fl-input-selected-background-color: lavenderblush;
}
```

***

<div class="call-out call-out__success">
  <div class="call-out--icon">
    <img src="https://files.readme.io/a7f52d1-Inline_Success.svg" alt="Success" />
  </div>

  <div>
    <div class="call-out--title">Success</div>
    <div class="call-out--text">You have created a Web SDK styles file!</div>
  </div>
</div>

<br />
