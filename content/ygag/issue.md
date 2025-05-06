## YGAG Issue API

Order api for YGAG.

### Request Details

URL: `{{base_url}}/api/servicegroup/issue/ygag/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "notify": 1,
    "brand_code": "ABQUAE",
    "currency": "AED",
    "amount": 200,
    "country": "AE",
    "receiver_name": "Manish",
    "receiver_email": "manish@lambdapayments.com",
    "receiver_phone": "+971512121212",
    "message": "Well Done!,\nI thought you would like this gift!",
    "extra_fields": {
        "department": "Information Technology",
        "custuomer_id": "A1232",
        "pi_12": "12Ag",
        "receiver_name": "My_Name"
    },
    "delivery_language": "en",
    "customer_identifier": "customer@test.com",
    "remarks": "Test Txn"
}
```

### **Payload Description**

| **Field**             | **Type**         | **Description**                                       |
| --------------------- | ---------------- | ----------------------------------------------------- |
| `token`               | String           | Secure token used for authentication.                 |
| `reference`           | String           | Unique identifier for the transaction.                |
| `notify`              | Integer          | Flag indicating whether notifications should be sent. |
| `brand_code`          | String           | The brand code                                        |
| `currency`            | String           | Preferred currency                                    |
| `amount`              | Integer          | Order amount.                                         |
| `country`             | String           | Country Code.                                         |
| `receiver_name`       | String           | Name of the recipient.                                |
| `receiver_email`      | String           | Email address of the recipient.                       |
| `receiver_phone`      | String           | Phone number of the recipient.                        |
| `message`             | String           | Personalized message included with the transaction.   |
| `extra_fields`        | Object           | Additional information to send.                       |
| `delivery_language`   | String           | Preferred language for delivery communication.        |
| `remarks`             | Optional(String) | Transaction remarks for the order.                    |
| `customer_identifier` | Optional(String) | User Identifier at the client end.                    |

### Exampl Error Response

```json
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": "",
    "error_data": {
        "receiver_phone": "This field is required."
    },
    "state": "Error"
}
```

### Example Success Response

> Note: `amount` is the price converted to the client currency where the `price` is the original price for the order.

```json
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "reference_id": "a0ad1e7a-3ba2-456a-b786-3b5216964ac0",
        "order_id": 1108061,
        "state": 1,
        "notify": 1,
        "is_generic": false,
        "ordered_amount": {
            "price": 50,
            "price_currency": "AED",
            "amount": 22685.185185,
            "amount_currency": "NPR"
        },
        "extra_fields": "department: Information Technology\ncustuomer_id: A1232\nreceiver_name: My_Name\npi_12: 12Ag",
        "barcode": "https://sandbox.yougotagift.com/barcode/generate/4616574446974244/",
        "gift_voucher": [
            {
                "label": "code",
                "value": "4616574446974244"
            },
            {
                "label": "pin",
                "value": "2456"
            }
        ],
        "expiry_date": "2026-05-06",
        "redemption_instructions": "Redeemable in UAE stores only\nACE is a participating brand within the Blue Rewards program.\r\nBlue Rewards is an Al Futtaim company.\r\nThis card can be used across Al Futtaim brands and stores. For more detail, please visit <a href=\"https://mybluerewards.com/\" target=\"_blank\" class=\"new_plink plink\">https://mybluerewards.com/</a> \r\nThe card can be directly presented at the stores for redemption or the customer can download the Blue Rewards app or visit Blue Rewards at <a href=\"https://mybluerewards.com/\" target=\"_blank\" class=\"new_plink plink\">https://mybluerewards.com/</a> for more details. \r\nFor in app registration on Blue Rewards App - Follow the below steps for redeeming the Gift card:\r\n<ol>\r\nUpon registration, under Profile click Add Gift Card.\r\nEnter card number and PIN to add to Wallet.</ol>\r\nThe card cannot be exchanged for card or gift vouchers. The card cannot be returned or refunded.  \r\nThe card can only be loaded once and cannot be topped up. The card is valid for multiple purchases up to the full value loaded on the card.  \r\nAs the card is transferable, Merchant is not responsible for checking the ownership of the card before acceptance at the checkout. \r\nCustomers (users) are advised to read the terms and conditions carefully on the Blue Rewards website <a href=\"https://mybluerewards.com/\" target=\"_blank\" class=\"new_plink plink\">https://mybluerewards.com/</a>\r\nBalance enquiries and partial redemptions are the sole responsibility of the merchant..  \r\nMerchant reserves the right to change the terms and conditions governing the use of the card from time to time at its sole discretion.  \r\nMerchant's decisions on all matters relating to the card shall be final and binding on the Customer and all users and no correspondence will be entered into.\r\neGift Cards once issued cannot be canceled, exchanged, extended or refunded and are subject to the terms & conditions of the merchant.\r\nItems purchased using this eGift Card are refundable as per the refund and exchange policy of the merchant. The merchant is solely responsible for the product & service provided to customers through the use of this eGift Card.\n\nTerms and conditions of the retailers are applicable.\nNo cashback, refunds or returns.",
        "brand_details": {
            "name": "ACE",
            "code": "AECAE",
            "pin_redeemable": false,
            "logo": "https://scdn.yougotagift.com/media/images/cards/fb/tmpDvR67m.jpg",
            "product_image": "https://scdn.yougotagift.com/media/images/cards/print/tmp82_fvA.jpg"
        },
        "receiver_name": "Manish",
        "receiver_email": "manish@lambdapayments.com",
        "receiver_phone": "+971512121212",
        "country": "AE",
        "message": "Well Done!,\nI thought you would like this gift!",
        "date_added": "2025-05-06T02:15:01.784Z",
        "egift_card": {
            "url": "https://s.gotagift.co/1Mp5W0Y",
            "gift_verification_pin": "m9sqN1"
        }
    },
    "detail": "Order successful",
    "credits_consumed": 22685.185185,
    "credits_available": 99895434.29939592,
    "currency": "NPR",
    "id": 162
}
```