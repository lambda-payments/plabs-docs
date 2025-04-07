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
    "delivery_language": "en"
}
```

### **Payload Description**

| **Field**           | **Type** | **Description**                                       |
| ------------------- | -------- | ----------------------------------------------------- |
| `token`             | String   | Secure token used for authentication.                 |
| `reference`         | String   | Unique identifier for the transaction.                |
| `notify`            | Integer  | Flag indicating whether notifications should be sent. |
| `brand_code`        | String   | The brand code                                        |
| `currency`          | String   | Preferred currency                                    |
| `amount`            | Integer  | Order amount.                                         |
| `country`           | String   | Country Code.                                         |
| `receiver_name`     | String   | Name of the recipient.                                |
| `receiver_email`    | String   | Email address of the recipient.                       |
| `receiver_phone`    | String   | Phone number of the recipient.                        |
| `message`           | String   | Personalized message included with the transaction.   |
| `extra_fields`      | Object   | Additional information to send.                       |
| `delivery_language` | String   | Preferred language for delivery communication.        |

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

```json
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "reference_id": "ccca4aa0-8743-475a-b9c9-20e1973616d7",
        "order_id": 1073029,
        "state": 1,
        "notify": 1,
        "is_generic": false,
        "ordered_amount": {
            "currency": "AED",
            "amount": 200
        },
        "extra_fields": "department: Information Technology\ncustuomer_id: A1232\nreceiver_name: My_Name\npi_12: 12Ag",
        "brand_accepted_amount": {
            "currency": "AED",
            "amount": 200
        },
        "exchange_rate": {
            "base_currency": "AED",
            "target_currency": "AED",
            "conversion_rate": 1.0
        },
        "barcode": "https://sandbox.yougotagift.com/barcode/generate/YGAG83649597798868855221/",
        "gift_voucher": [
            {
                "label": "code",
                "value": "YGAG83649597798868855221"
            }
        ],
        "expiry_date": "2025-11-05",
        "redemption_instructions": "Redeemable in UAE stores only\nThis eGift card is only valid for a one time purchase or single transaction to the full value unless otherwise specified.\r\nThe eGift card can be redeemed across all stores of Abdul Samad Al Qurashi in UAE.\r\neGift Cards once issued cannot be canceled, exchanged, extended or refunded and are subject to the terms & conditions of the merchant.\r\nItems purchased using this eGift Card are refundable as per the refund and exchange policy of the merchant. The merchant is solely responsible for the product & service provided to customers through the use of this eGift Card.\n\nTerms and conditions of the retailers are applicable.\nNo cashback, refunds or returns.",
        "brand_details": {
            "name": "Abdul Samad Al Qurashi",
            "code": "ABQUAE",
            "pin_redeemable": false,
            "logo": "https://scdn.yougotagift.com/media/images/cards/fb/tmp0iVW7p.jpg",
            "product_image": "https://scdn.yougotagift.com/media/images/cards/print/tmpcnQaga.jpg"
        },
        "receiver_name": "Manish",
        "receiver_email": "manish@lambdapayments.com",
        "receiver_phone": "+971512121212",
        "country": "AE",
        "message": "Well Done!,\nI thought you would like this gift!",
        "date_added": "2025-04-02T15:27:37.845Z",
        "egift_card": {
            "url": "https://s.gotagift.co/EaN3ad6",
            "gift_verification_pin": "BHtB2c"
        }
    },
    "detail": "Order successful",
    "credits_consumed": 200.0,
    "credits_available": 99935172.43756561,
    "id": 112
}
```