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
```json
{
    "status": true,
    "data": [
        {
            "id": 2,
            "brand_id": null,
            "is_active": true,
            "is_generic": false,
            "brand_code": "3DWAE",
            "pin_redeemable": false,
            "name": "3D WORLD DUBAI : SELFIE MUSEUM",
            "logo": "https://scdn.yougotagift.com/media/images/cards/fb/tmp39VcDd.jpg",
            "product_image": "https://scdn.yougotagift.com/media/images/cards/mail/tmpcBFQxR.jpg",
            "country": {
                "code": "AE",
                "name": "UAE"
            },
            "validity_in_months": 3,
            "variable_amount": false,
            "denominations": {
                "AED": [
                    {
                        "amount": 59,
                        "is_active": false
                    },
                    {
                        "amount": 79,
                        "is_active": false
                    },
                    {
                        "amount": 65,
                        "is_active": true
                    },
                    {
                        "amount": 89,
                        "is_active": true
                    }
                ]
            },
            "tagline": "Pose, Click & Create Memories",
            "description": "Pose, Click & Create Memories\r\n\nThe first 3D Trick Art Museum in Dubai, with hand-painted 3D immersive artwork in 9 different themed zones, where visitors can pose with the paintings and become “part of the art”, creating memories for life!\r\n\n",
            "brand_accepted_currency": "AED",
            "image_gallery": [
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/19tRPsgkxaGF-aL1puDk6w.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/24jp55v2lbQFvq90ZHstW8.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/3qNNqtcLNdxqeGL87Fol_L.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/3WOhITqRxelXZVAFjj2efY.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/Fil4xX6JdiX2yuj375IDV.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/27Fdhz8Jt22oVEJNHLIWQW.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/3Vnc8JCQV5mV0nmX2Pl6vi.jpg"
                },
                {
                    "image": "https://scdn.yougotagift.com/media/images/cards/gallery/38vf599RN7ybKZ2Zs8VDou.jpg"
                }
            ],
            "redemption_type": "Redeem at Store",
            "redemption_instructions": "Redeemable in UAE stores only\nThis eGift card is only valid for a one-time purchase to the full value.\n3D World Dubai: Selfie Museum ticket prices as follows:\n<ol>\nChild Ticket (3 - 11 years) AED 65\nAdult Ticket (12 years and Above) AED 89\nBelow 3 years is free</ol>\nThe eGift card is valid at 3D World Dubai: Selfie Museum in The United Arab Emirates. To know the locations of 3D World Dubai: Selfie Museum, please visit the following link: <a href=\"https://dubai3dworld.com/visit.aspx\" target=\"_blank\" class=\"new_plink plink\"> https://dubai3dworld.com/visit.aspx</a>\nPlease arrive at the museum at least 1 hour before closing time to enjoy the experience at leisure.\nLate arrivals and people who miss their tour will be considered a no-show and will not be eligible for a refund.\nExpired eGift Cards cannot be extended, exchanged or refunded.\n",
            "detail_url": "https://b2b-sandbox.yougotagift.com/corporate/api/v2-4/brands/3DWAE/",
            "locations_url": null,
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
                    "id": 112,
                    "name": "Kids & Fun"
                },
                {
                    "id": 113,
                    "name": "Experiences & Entertainment"
                }
            ]
        }
    ]
}
```