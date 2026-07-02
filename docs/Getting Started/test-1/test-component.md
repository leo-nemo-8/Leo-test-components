---
title: test component
deprecated: false
hidden: false
metadata:
  robots: index
---
<CSPDomains domains={["mczbf.com", "sjwoe.com", "cj.dotomi.com", "emjcd.com", "idsync.rlcdn.com", ".cj.com"]} />

# Site Page Tag

This section covers the Site Page Tag implementation for all pages on your site, excluding transaction and purchase confirmation pages. It includes code examples and a reference for the available parameters.

<PreflightNote
  items={[
    "Place the cj.sitePage and cj.order object before the CJ script on the respective pages. Both scripts should be placed as high on the page as possible,",
    "Replace all placeholder values with your actual data. Brackets are for illustration only and should not appear in your final code.",
    "Code examples are provided for reference only and may not be compatible with all shopping carts or platforms. CJ does not guarantee their accuracy for your specific setup."
		
  ]}
/>

<DynamicCodeBlockTabs
  tabs={[
    {
      label: "Site Page Tag",
      language: "javascript",
      snippet: `<script type='text/javascript'>
if (!window.cj) window.cj = {};
cj.sitePage = {
    enterpriseId: {{enterpriseId}},
    pageType: '{pageType}',
    referringChannel: '{referringChannel}',
    cartSubtotal: {cartSubtotal}
};
</script>

<script type='text/javascript'>

(function(a,b,c,d){
    a='https://www.mczbf.com/tags/{{tagId}}/tag.js';
    b=document;c='script';d=b.createElement(c);d.src=a;
    d.type='text/java'+c;d.async=true;
    d.id='cjapitag';
    a=b.getElementsByTagName(c)[0];a.parentNode.insertBefore(d,a)
})();
</script>`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" },
        { key: "tagId",     fallback: "{tagId}" }
      ]
    },
    {
      label: "Homepage",
      language: "javascript",
      snippet: `cj.sitePage = {
    enterpriseId: {{enterpriseId}},
    pageType: 'homepage',
    referringChannel: 'Affiliate'
}`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" }
      ]
    },
    {
      label: "Product Page",
      language: "javascript",
      snippet: `cj.sitePage = {
    enterpriseId: {{enterpriseId}},
    pageType: 'productDetail',
    referringChannel: 'Affiliate'
}`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" }
      ]
    },
{
      label: "Cart Page",
      language: "javascript",
      snippet: `cj.sitePage = {
    enterpriseId: {{enterpriseId}},
    pageType: 'cart',
    referringChannel: 'Affiliate',
    cartSubtotal: 89.97,
    items: [
        {itemId: 'PROD-001',unitPrice: 29.99, quantity: 2},
        {itemId: 'PROD-002', unitPrice: 10.45, quantity: 1}
    ]
};`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" }
      ]
    },
  ]}
/>

## Site Page Tag Parameters

<ExpandableParamTable
  params={[
    {
      name: "enterpriseId",
      description: "Your CJ Enterprise ID. A static value provided by CJ and unique to your account.",
      required: "Required",
      expandable: false,
      details: {
        type: "ID",
        format: "Numeric string",
        examples: [
          { label: "Example", value: "1234567" },
        ],
        note: "This value never changes. Locate it under Account > Settings in your CJ Account Manager dashboard.",
      },
    },
    {
      name: "pageType",
      description: "The type of page where the tag is deployed. Drives page-level segmentation and cross-channel journey tracking.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "PageType",
        allowedValues: [
          { value: "homepage" },
          { value: "product" },
          { value: "category" },
          { value: "cart" },
          { value: "confirmation" },
          { value: "other" },
        ],
        note: "See the PageType reference table for the full list of accepted values. Mismatched values will skew funnel attribution reporting.",
      },
    },
    {
      name: "referringChannel",
      description: "The marketing channel that referred the user before they arrived at your site. Only populate this on the landing page of the session.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "String",
        allowedValues: [
          { value: "Affiliate" },
          { value: "Display" },
          { value: "Social" },
          { value: "Search" },
          { value: "Email" },
          { value: "Direct_Navigation" },
        ],
        note: "This field only needs to be populated on the page where the user first arrives. For Cross Channel Journey tracking, use the exact values shown above",
      },
    },
    {
      name: "cartSubtotal",
      description: "The subtotal of the shopping cart. Only populate this parameter on cart pages.",
      required: "Optional",
      expandable: false,
      details: {
        type: "Decimal",
        format: "Decimal number, max 2 decimal places",
        examples: [
          { label: "Example", value: "89.99" },
          { label: "Example", value: "124.50" },
        ],
        note: "Do not include taxes, shipping costs, or fees. Pass the pre-tax, pre-shipping subtotal only to ensure consistent cross-session data.",
      },
    },
  ]}
/>

## Accepted values for `pageType`

<FilterableParamTable
  description="All values are supported across verticals. The list below reflects the most common usage per vertical."
  columns={[
    { key: "value", label: "Page Type", isCode: true },
    { key: "verticals", label: "Advertiser Vertical" },
    { key: "notes", label: "Notes" },
  ]}
  filters={[
    {
      key: "verticals",
      label: "Vertical",
      options: ["Retail", "Finance", "Travel", "Network Services"],
    },
  ]}
  searchKeys={["value", "notes"]}
  rows={[
    { value: "homepage", verticals: "Retail, Network Services, Finance, Travel", notes: "The main landing page and homepage of your site." },
    { value: "department", verticals: "Retail, Network Services, Finance", notes: "Department-level pages sitting above category pages in the site hierarchy." },
    { value: "category", verticals: "Retail, Network Services, Finance", notes: "Category listing pages showing a group of products or services." },
    { value: "subCategory", verticals: "Retail, Network Services, Finance", notes: "" },
    { value: "productDetail", verticals: "Retail, Network Services, Finance", notes: "Individual product detail pages." },
    { value: "cart", verticals: "Retail, Network Services, Finance, Travel", notes: "Pass all items in the cart, if possible. Follow the format outlined in the Site Tag code example" },
    { value: "searchResults", verticals: "Retail, Network Services, Finance, Travel", notes: "Search results pages." },
    { value: "storeLocator", verticals: "Retail, Network Services", notes: "" },
    { value: "accountSignup", verticals: "Retail, Network Services, Finance, Travel", notes: "Account registration and signup pages." },
    { value: "accountCenter", verticals: "Retail, Network Services, Finance, Travel", notes: "Any pages within the account center after the user has logged in" },
    { value: "conversionConfirmation", verticals: "Retail, Network Services, Finance, Travel", notes: "The conversion confirmation page." },
    { value: "information", verticals: "Travel", notes: "" },
    { value: "propertyResults", verticals: "Travel", notes: "" },
    { value: "propertyDetail", verticals: "Travel", notes: "" },
    { value: "applicationStart", verticals: "Finance", notes: "The beginning of an application flow." },
    { value: "branchLocator", verticals: "Finance", notes: "Pages that help users find a physical branch location." },
  ]}
/>

# Conversion Page Tag

Place this code **only** on order confirmation, thank you, or conversion complete pages:

<DynamicCodeBlockTabs
  tabs={[
    {
      label: "cj.order",
      language: "javascript",
      snippet: `<script type="text/javascript">
if (!window.cj) window.cj = {};
cj.order = {
    enterpriseId: {{enterpriseId}},
    actionTrackerId: {{actionTrackerId}},
    orderId: {oid},
    cjeventOrder: {cjeCookie},
    pageType: 'conversionConfirmation',
    currency: {currency},
    amount: {amount},
    discount: {cartDiscount},
    coupon: {coupon},
    items: [
        { unitPrice: 29.99, itemId: 'sku1', quantity: 2, discount: 5.00},
        { unitPrice: 15.50, itemId: 'sku2', quantity: 1, discount: 0}
    ]
};
</script>

<script type='text/javascript'>
(function(a,b,c,d){
    a='https://www.mczbf.com/tags/{{tagId}}/tag.js';
    b=document;c='script';d=b.createElement(c);d.src=a;
    d.type='text/java'+c;d.async=true;
    d.id='cjapitag';
    a=b.getElementsByTagName(c)[0];a.parentNode.insertBefore(d,a)
})();
</script>`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" },
        { key: "tagId",     fallback: "{tagId}" }
      ]
    },
    {
      label: "cj.orders",
      language: "javascript",
      snippet: `<script type="text/javascript">
if (!window.cj) window.cj = {};
cj.orders = [{
    enterpriseId: {{enterpriseId}},
    pageType: 'conversionConfirmation',
    orderId: {orderId},
    actionTrackerId: {{actionTrackerId}},
    currency: {currency},
    amount: {amount},
    discount: {cartDiscount},
    coupon: {coupon},
    cjeventOrder: {cjeCookie},
    customerStatus: {customerStatus},
    items: [
       { 'unitPrice': 9.99, 'itemId': 'M223-02', 'quantity': 20, 'discount': 0 }, 
       { 'unitPrice': 24.99, 'itemId': 'B00138C', 'quantity': 4, 'discount': 1.00 }, 
       { 'unitPrice': 1449.00, 'itemId': 'MWHA', 'quantity': 1, 'discount': 50.00 }
       ]
},
{
    enterpriseId: {{enterpriseId}},
    pageType: 'conversionConfirmation',
    orderId: {orderId},
    actionTrackerId: {{actionTrackerId}},
    currency: {currency},
    amount: {amount},
    discount: {cartDiscount},
    coupon: {coupon},
    cjeventOrder: {cjeCookie},
    customerStatus: {customerStatus},
    items: [
       { 'unitPrice': 0, 'itemId': 'lead-submission', 'quantity': 1, 'discount': 0 },
       ]
}];
</script>

<script type='text/javascript'>
(function(a,b,c,d){
    a='https://www.mczbf.com/tags/{{tagId}}/tag.js';
    b=document;c='script';d=b.createElement(c);d.src=a;
    d.type='text/java'+c;d.async=true;
    d.id='cjapitag';
    a=b.getElementsByTagName(c)[0];a.parentNode.insertBefore(d,a)
})();
</script>
`,
      params: [
        { key: "enterpriseId", fallback: "{enterpriseId}" },
        { key: "tagId", fallback: "{tagId}" } 
      ]
    }
  ]}
/>

> The **cj.orders** data object should be used for any advertiser that needs to fire multiple actions for the same transaction.
>
> The **cj.orders** accepts an array of orders than can include different enterpriseId and actionTrackerId.

## Conversion Tag Parameters

<ExpandableParamTable
  params={[
    {
      name: "enterpriseId",
      description: "Your CJ Enterprise ID. A static value provided by CJ and unique to your account.",
      required: "Required",
      expandable: false,
      details: {
        type: "ID",
        format: "Numeric string",
      },
    },
		{
      name: "actionTrackerId",
      description: "A static value provided by CJ. Each account may have multiple actions, each referenced by a different actionTrackerId.",
      required: "Required",
      expandable: false,
      details: {
        type: "ID",
      },
    },
    {
      name: "orderId",
      description: "A unique identifier for the order, such as an order number or invoice ID. Used to reconcile orders between your system and CJ.",
      required: "Required",
      expandable: true,
      details: {
        type: "ID",
        format: "Alphanumeric, dashes, and underscores only",
        examples: [
          { value: "ORDER-00123" },
          { value: "INV_987654" },
        ],
        note: "Truncated after 96 characters. Do not include PII such as email addresses. Spaces and special characters are not permitted.",
      },
    },
		{
      name: "cjeventOrder",
      description: "The CJ Event ID from the cje cookie stored on the advertiser's site. Used to attribute the order to the correct CJ event.",
      required: "Required",
      expandable: true,
      details: {
        type: "String",
        note: "Read this value directly from the cje cookie. If the cookie is not present, do not pass an empty string — omit the parameter entirely.",
      },
    },
    {
      name: "amount",
      description: "The order total in the currency specified by the currency parameter. Do not include shipping or tax.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "Decimal",
        format: "Numeric, max 2 decimal places",
        examples: [
          { value: "89.99" },
          { value: "124.50" },
        ],
        note: "Do not include shipping or tax. If a currency other than your functional currency is specified, CJ converts the amount automatically using current exchange rates.",
      },
    },
    {
      name: "currency",
      description: "Three-letter currency code identifying the currency of the order amount. Defaults to the advertiser's functional currency if omitted.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "String",
        format: "ISO 4217 three-letter currency code",
        examples: [
          { value: "USD" },
          { value: "GBP" },
          { value: "EUR" },
        ],
        note: "If a currency value is not returned, the transaction will default to your account's functional currency.",
      },
    },
    {
      name: "discount",
      description: "Discount amount applied to the whole order.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "Decimal",
        format: "Numeric, max 2 decimal places",
        examples: [
          { value: 10.00 },
          { value: 5.50 },
        ],
        note: "Total discount applied to the order as a whole. Use this for cart-level promotions such as a percentage off the entire order or a flat order discount. For item-level discounts, use the discount field within each item in the items array.",
      },
    },
    {
      name: "coupon",
      description: "The coupon or voucher code used in the transaction.",
      required: "Recommended",
      expandable: true,
      details: {
        type: "String",
        examples: [
          { value: "SAVE20" },
          { value: "WELCOME10" },
        ],
        note: "Leave empty or omit if no coupon was used.",
      },
    },
  ]}
/>

## Item-Level Parameters

<ExpandableParamTable
  params={[
    {
      name: "itemId",
      description: "The identifier for the individual item purchased, such as a SKU or product ID.",
      required: "Required",
      expandable: true,
      details: {
        type: "String",
        format: "Alphanumeric, dashes, and underscores only",
        examples: [
          { value: "SKU-001" },
          { value: "PROD_4521" },
        ],
        note: "Maximum 100 items per order. SKU values must be 100 characters or fewer. Spaces and special characters are not permitted.",
      },
    },
    {
      name: "unitPrice",
      description: "The price of a single unit of the item. Do not multiply by quantity.",
      required: "Required",
      expandable: true,
      details: {
        type: "Decimal",
        format: "Numeric only, no currency symbols or commas",
        examples: [
          { value: "13.49" },
          { value: "3.00" },
        ],
        note: "Pass the price of one item regardless of quantity. For example, pass 3.00 for two items at 3.00 each — not 6.00. Maximum 100 items per order.",
      },
    },
    {
      name: "quantity",
      description: "The number of units purchased for this item. Multiplied by unitPrice to calculate the item total.",
      required: "Required",
      expandable: true,
      details: {
        type: "Integer",
        format: "Whole numbers only",
        examples: [
          { value: "1" },
          { value: "3" },
        ],
        note: "Decimal quantities are not supported. For example, quantity=1.0 is read as quantity=10. Maximum 100 items per order.",
      },
    },
 {
  name: "discount",
  description: "Discount applied to this specific item in the transaction. Use this for product-level promotions such as a sale price on an individual SKU. For order-wide discounts, use the top-level discount parameter.",
  required: "Optional",
  expandable: true,
  details: {
    type: "Decimal",
    format: "Numeric, max 2 decimal places",
    examples: [
      { value: "5.00" },
    ],
    note: "The discount is divided evenly across all units. For example, a 5.00 discount on 2 units at 10.00 each reduces each unit to 7.50, giving a subtotal of 15.00.",
  },
},
  ]}
/>