---
title: Examples and Detailed Description
deprecated: false
hidden: false
metadata:
  robots: index
---
## Endpoint

```http
POST /weapi/v1/doc/addinvoicequick
```

## Authentication

Requires a valid **Bearer Token**.

## Headers

| Header        | Value                   |
| ------------- | ----------------------- |
| Content-Type  | application/json        |
| Authorization | Bearer `<access_token>` |

## Request Body

| Field                 | Type    | Required         | Description                                                                                                                                                                                |
| --------------------- | ------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `recipient_name`      | string  | <mark>Yes</mark> | Customer name.                                                                                                                                                                             |
| `recipient_id_number` | string  | No               | Recipient identification number (Israeli ID, company registration number, authorized dealer number, or exempt dealer number). Optional, but required for transactions exceeding 5,000 ILS. |
| `product_name`        | string  | <mark>Yes</mark> | Product or service description.                                                                                                                                                            |
| `product_quantity`    | number  | No               | Product quantity. If omitted, the default quantity is used.                                                                                                                                |
| `sum_payed`           | number  | <mark>Yes</mark> | Total amount paid.                                                                                                                                                                         |
| `vat_exempt`          | boolean | No               | Indicates whether the product is VAT exempt.                                                                                                                                               |
| `pay_method`          | integer | No               | Payment method code. See the [Payment Methods](#payment-methods) section for the list of supported values. Leave empty if no payment information should be recorded.                       |
| `payment_desc`        | string  | No               | Additional payment details (for example, the last 4 digits of a credit card).                                                                                                              |
| `invoice_desc`        | string  | No               | Optional invoice note or description.                                                                                                                                                      |
| `currency`            | string  | No               | Currency code (for example, ILS, USD). If omitted, the system assumes ILS.                                                                                                                 |

### Payment Methods

The `pay_method` field is an **integer enum**. The API expects the **integer value** shown in the first column.

| Integer Value | Enum Value        | Description           |
| ------------: | ----------------- | --------------------- |
|           `1` | `מזומן`           | Cash payment.         |
|           `2` | `שיק`             | Check payment.        |
|           `3` | `כרטיס אשראי`     | Credit card payment.  |
|           `4` | `העברה בנקאית`    | Bank transfer.        |
|           `5` | `פייפאל`          | PayPal payment.       |
|           `6` | `פיימי`           | PayMe payment.        |
|           `7` | `פייבוקס`         | PayBox payment.       |
|           `8` | `ApplePay`        | Apple Pay payment.    |
|           `9` | `GooglePay`       | Google Pay payment.   |
|          `10` | `BIT`             | Bit payment.          |
|          `11` | `אחר`             | Other payment method. |
|          `12` | `אפליקציית תשלום` | Payment application.  |
|          `13` | `ניכוי במקור`     | Withholding tax.      |

### Payment Behavior

#### Without a payment method

If `pay_method` is omitted, a **Tax Invoice** is created.

#### With a payment method

If `pay_method` is provided, a **Tax Invoice Receipt** is created.

## Response

### On success

**HTTP 200 OK** with a JSON object containing the created invoice information.

#### Example:

```json
{
  "id": "ABC*****XYZ",
  "number": 1045,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/ABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/ABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/ABC*****XYZ/en"
}
```

## Response Fields

### Success (200 OK)

- Returned upon success

| Field           | Type    | Description                                              |
| --------------- | ------- | -------------------------------------------------------- |
| `id`            | string  | Unique identifier of the created invoice.                |
| `number`        | integer | The generated invoice number.                            |
| `confirmNumber` | string  | Israeli Tax Authority invoice allocation number          |
| `signed`        | boolean | Indicates whether the invoice has been digitally signed. |
| `lang`          | string  | The default language of the generated invoice.           |
| `url`           | string  | URL to view the generated invoice.                       |
| `urlHe`         | string  | URL to view the invoice in Hebrew.                       |
| `urlEn`         | string  | URL to view the invoice in English.                      |

***

### Error (400 Bad Request)

- Returned when the request is invalid or contains malformed data.

| Field        | Type           | Description                                            |
| ------------ | -------------- | ------------------------------------------------------ |
| errorCode    | string \| null | Optional machine-readable error code. May be `null`.   |
| errorMessage | string         | Human-readable description of the error.               |
| errorData    | object \| null | Additional error details, if available. May be `null`. |

### Failure

**400 Bad Request** Returned when the request is invalid or contains malformed data.

#### Example:

```json
{
  "errorCode": null,
  "errorMessage": "unique-id bad format",
  "errorData": null
}
```

## Notes

- This endpoint supports **only a single product**.
- Only **one payment method** can be supplied.
- Payment fields are optional if the invoice should be created without recording payment details.
- `sum_payed` should represent the total amount paid for the invoice.

## Examples

The following four examples demonstrate common real-world scenarios for using this endpoint:

1.Create a Tax Invoice for a Single Product

2.Create a Tax Invoice for a VAT-Exempt Product

3.Create a Tax Invoice Receipt for a Single Product Paid in Full

4.Create a Tax Invoice Receipt for a Transaction Above 5,000 ILS

5.Create a Tax Invoice Receipt in USD

### Example 1 – Create a Tax Invoice for a Single Product

you need to create a **Tax Invoice** for a single product sold to your customer.

Your customer, Israel Israeli, purchased **Consulting Services** for **1,170 ILS**, but has not paid yet. Since no payment information is provided, the API creates a **Tax Invoice** (not a Tax Invoice Receipt).

**Request**

#### JSON

```json
{
  "recipient_name": "Israel Israeli",
  "product_name": "Consulting Services",
  "sum_payed": 1170.0
}
```

#### JavaScript (Fetch)

```javascript
const url = "https://wbnftapi.azurewebsites.net/weapi/v1/doc/addinvoicequick";

const options = {
  method: "POST",
  headers: {
    accept: "application/json",
    Authorization: "Bearer <access_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    recipient_name: "Israel Israeli",
    product_name: "Consulting Services",
    sum_payed: 1170.0,
  }),
};

fetch(url, options)
  .then((res) => res.json())
  .then((json) => console.log(json))
  .catch((err) => console.error(err));
```

#### Response

```json
{
  "id": "ABC*****XYZ",
  "number": 1022,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/en"
}
```

### Example 2 – Create a Tax Invoice for a VAT-Exempt Product

**Scenario**

For example, you need to create a **Tax Invoice** for a single product that is **exempt from VAT**.

Israel Israeli purchased a professional training course for **950 ILS**. The service is VAT exempt, and no payment information is provided. Since `vat_exempt` is set to `true` and `pay_method` is omitted, the API creates a **Tax Invoice**.

**Request**

#### JSON

```json
{
  "recipient_name": "Israel Israeli",
  "product_name": "Professional Training Course",
  "sum_payed": 950.0,
  "vat_exempt": true,
  "currency": "ILS"
}
```

#### JavaScript (Fetch)

```javascript
const url = "https://wbnftapi.azurewebsites.net/weapi/v1/doc/addinvoicequick";

const options = {
  method: "POST",
  headers: {
    accept: "application/json",
    Authorization: "Bearer <access_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    recipient_name: "Israel Israeli",
    product_name: "Professional Training Course",
    sum_payed: 950.0,
    vat_exempt: true,
    currency: "ILS",
  }),
};

fetch(url, options)
  .then((res) => res.json())
  .then((json) => console.log(json))
  .catch((err) => console.error(err));
```

#### Response

```json
{
  "id": "ABC*****XYZ",
  "number": 1022,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/en"
}
```

### Example 3 – Create a Tax Invoice Receipt for a Single Product Paid in Full

**Scenario**

For example, you need to create a **Tax Invoice Receipt** for a single product that has been **paid in full using a single payment method**.

Israel Israeli purchased website development services for **2,500 ILS** and paid the full amount by credit card. Since payment information is provided using a single payment method (`pay_method`), the API creates a **Tax Invoice Receipt**.

**Request**

#### JSON

```json
{
  "recipient_name": "Israel Israeli",
  "product_name": "Website Development",
  "sum_payed": 2500.0,
  "pay_method": 2,
  "payment_desc": "Visa ****4587",
  "currency": "ILS"
}
```

#### JavaScript (Fetch)

```javascript
const url = "https://wbnftapi.azurewebsites.net/weapi/v1/doc/addinvoicequick";

const options = {
  method: "POST",
  headers: {
    accept: "application/json",
    Authorization: "Bearer <access_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    recipient_name: "Israel Israeli",
    product_name: "Website Development",
    sum_payed: 2500.0,
    pay_method: 2,
    payment_desc: "Visa ****4587",
    currency: "ILS",
  }),
};

fetch(url, options)
  .then((res) => res.json())
  .then((json) => console.log(json))
  .catch((err) => console.error(err));
```

#### Response

```json
{
  "id": "ABC*****XYZ",
  "number": 1022,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/en"
}
```

### Example 4 – Create a Tax Invoice Receipt for a Transaction Above 5,000 ILS

**Scenario**

For example, you need to create a **Tax Invoice Receipt** for a single product purchased for **more than 5,000 ILS** and paid in full using **Bit**.

Israel Israeli purchased a laptop for **6,200 ILS** and paid the full amount using Bit. Since the transaction amount exceeds **5,000 ILS**, `recipient_id_number` is required. Because payment information is included, the API creates a **Tax Invoice Receipt**.

**Request**

#### JSON

```json
{
  "recipient_name": "Israel Israeli",
  "recipient_id_number": "123456789",
  "product_name": "Laptop",
  "sum_payed": 6200.0,
  "pay_method": 4,
  "payment_desc": "Bit payment",
  "currency": "ILS"
}
```

#### JavaScript (Fetch)

```javascript
const url = "https://wbnftapi.azurewebsites.net/weapi/v1/doc/addinvoicequick";

const options = {
  method: "POST",
  headers: {
    accept: "application/json",
    Authorization: "Bearer <access_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    recipient_name: "Israel Israeli",
    recipient_id_number: "123456789",
    product_name: "Laptop",
    sum_payed: 6200.0,
    pay_method: 4,
    payment_desc: "Bit payment",
    currency: "ILS",
  }),
};

fetch(url, options)
  .then((res) => res.json())
  .then((json) => console.log(json))
  .catch((err) => console.error(err));
```

#### Response

```json
{
  "id": "ABC*****XYZ",
  "number": 1022,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/en"
}
```

### Example 5 – Create a Tax Invoice Receipt in USD

**Scenario**

For example, you need to create a **Tax Invoice Receipt** for a single product sold in **USD**.

Israel Israeli purchased consulting services for **1,170 USD** and paid the full amount by credit card. Since the payment is provided using a single payment method (`pay_method`) and the currency is set to `USD`, the API creates a **Tax Invoice Receipt** in USD.

**Request**

#### JSON

```json
{
  "recipient_name": "Israel Israeli",
  "product_name": "Consulting Services",
  "sum_payed": 1170.0,
  "pay_method": 2,
  "payment_desc": "Visa ****4587",
  "currency": "USD"
}
```

#### JavaScript (Fetch)

```javascript
const url = "https://wbnftapi.azurewebsites.net/weapi/v1/doc/addinvoicequick";

const options = {
  method: "POST",
  headers: {
    accept: "application/json",
    Authorization: "Bearer <access_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    recipient_name: "Israel Israeli",
    product_name: "Consulting Services",
    sum_payed: 1170.0,
    pay_method: 2,
    payment_desc: "Visa ****4587",
    currency: "USD",
  }),
};

fetch(url, options)
  .then((res) => res.json())
  .then((json) => console.log(json))
  .catch((err) => console.error(err));
```

#### Response

```json
{
  "id": "ABC*****XYZ",
  "number": 1022,
  "confirmNumber": "",
  "signed": true,
  "lang": "he",
  "url": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ",
  "urlHe": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/he",
  "urlEn": "https://metrocal.azurewebsites.net/p/doc/vncABC*****XYZ/en"
}
```

<br />