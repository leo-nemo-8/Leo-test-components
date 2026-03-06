---
title: 'title: Split payments'
deprecated: false
hidden: false
metadata:
  robots: index
---
---
title: Split payments
excerpt: >-
Ideal for Marketplaces; purchasing goods from multiple sellers in a single
basket.
deprecated: false
hidden: true
metadata:
robots: index
---
Splitting payment is ideal for Marketplaces as it allows you to split payments between services/sales location (over different merchants). This make it possible for your customers to purchase goods from multiple sellers in a single basket.

A marketplace platform can split the payment between various parties, and even choose to retain a portion of the funds in their own balance as a fee.

You can spilt funds to a single party or to multiple parties. There is currently no limit on how many splits can be created for a single payment.

![](https://files.readme.io/1dc8c5720dc487e40467de3facdba5501b39765300c6b7a5aac1a3d86409276f-image.png)

<br />

# How to create a split payment

Use (at least) the following payload in the Order:Create API

```json
{
"serviceId": "SL-6515-0300",
"reference": "REF1234",
"description": "Split payment transations",
"amount": {
"value": 2500,
1000,
"currency": "EUR"
},
"optimize": {
"splitPayments": [
{
"serviceId": "SL-1390-9723",
"fee": "receiver",
"amount": {
"value": 1000,
250,
"currency": "EUR"
}
},
{
"serviceId": "SL-4567-1234",
"fee": "receiver",
"amount": {
"value": 1500,
250,
"currency": "EUR",

}
}
]
}
}
```

In the example above a 10 EUR single payment is created for SL-6515-0300 (from Merchant A) and a split payment request is added for:

* EUR 2,50 for SL-1390-9723 from Merchant B
* EUR 2,50 SL-4567-1234 from Merchant C

This results in a 10 EUR being added to the funds Merchant A (since Merchant A) is the owner of the transaction, but 2x EUR 2,50 is deducted and added to the funds of Merchant B and merchant C.

The reciple below, gives you a detailed instruction how to create a split payment.

<br />