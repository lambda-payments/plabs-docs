## YGAG Brands API

This API provides brands for YGAG, which can be cached on the client end.

### Request Details

URL: `{{base_url}}/api/servicegroup/options/ygag/brands`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "token": "top_secret_token"
}
```

---

### **Payload Description**

| **Field**    | **Type** | **Description**                       |
| ------------ | -------- | ------------------------------------- |
| `token`      | String   | Secure token used for authentication. |

### Example Response

> **Note**: The `amount` and `points` are account converted amounts, and the `price` and `price_currency` shall be used to send in the issue api.

```json
{
    "status": true,
    "data": [
        {
            "id": 499,
            "brand_id": null,
            "is_active": true,
            "is_generic": false,
            "brand_code": "ABQUAE",
            "pin_redeemable": false,
            "name": "Abdul Samad Al Qurashi",
            "logo": "https://scdn.yougotagift.com/media/images/cards/fb/tmp0iVW7p.jpg",
            "product_image": "https://scdn.yougotagift.com/media/images/cards/mail/tmpcnQaga.jpg",
            "country": {
                "code": "AE",
                "name": "UAE"
            },
            "validity_in_months": 12,
            "variable_amount": false,
            "denominations": [
                {
                    "price": 100.0,
                    "price_currency": "AED",
                    "amount": 45370.37037,
                    "amount_currency": "NPR",
                    "points": 604938271.6,
                    "points_currency": "PTS",
                    "is_active": true
                },
                {
                    "price": 200.0,
                    "price_currency": "AED",
                    "amount": 90740.740741,
                    "amount_currency": "NPR",
                    "points": 1209876543.213333,
                    "points_currency": "PTS",
                    "is_active": true
                },
                {
                    "price": 500.0,
                    "price_currency": "AED",
                    "amount": 226851.851852,
                    "amount_currency": "NPR",
                    "points": 3024691358.026667,
                    "points_currency": "PTS",
                    "is_active": true
                }
            ],
            "tagline": "Awaken Your Senses",
            "description": "Awaken Your Senses\r\n\nThe Abdul Samad Al Qurashi eGift Card is your gateway to Abdul Samad Al Qurashi is a leading company in the world of luxury perfumes, proud of its heritage and expertise for more than 150 years, guaranteeing outstanding and unique quality fragrances for an unforgettable experience.\r\n\n",
            "brand_accepted_currency": "AED",
            "image_gallery": [
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/1JK_H3_B97KVeWVaTfmkoB.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/2UFKfxYVF268J6UwMxdzpa.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/2nTIs5PXl2BX8_PZvMxUlu.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/2mdIOW4sNfZUGid3E9qzPI.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/p7WIybfV3Q8r4ML0K4o9l.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/2ImlQLTYJ6z8_LYemCo52D.jpg"
                }
            ],
            "redemption_type": "Redeem at Store",
            "redemption_instructions": "Redeemable in UAE stores only\nThis eGift card is only valid for a one time purchase or single transaction to the full value unless otherwise specified.\nThe eGift card can be redeemed across all stores of Abdul Samad Al Qurashi in UAE.\neGift Cards once issued cannot be canceled, exchanged, extended or refunded and are subject to the terms & conditions of the merchant.\nItems purchased using this eGift Card are refundable as per the refund and exchange policy of the merchant. The merchant is solely responsible for the product & service provided to customers through the use of this eGift Card.\n",
            "detail_url": "https://b2b-sandbox.yougotagift.com/corporate/api/v2-4/brands/ABQUAE/",
            "locations_url": "https://b2b-sandbox.yougotagift.com/corporate/api/v2-4/brands/ABQUAE/locations/",
            "categories": [
                {
                    "id": 32,
                    "name": "Most Popular"
                },
                {
                    "id": 154,
                    "name": "Single Brands"
                },
                {
                    "id": 21,
                    "name": "Fashion & Accessories"
                },
                {
                    "id": 114,
                    "name": "Beauty & Cosmetics"
                }
            ]
        }
    ]
}
```