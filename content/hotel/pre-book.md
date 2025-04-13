## Hotel Pre-Book API

This search API allows you to pre-book hotels for further booking.

### Request Details

URL: `{{base_url}}/api/servicegroup/prebook/hotel/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

### **Example Payload**

```json
{
    "token": "{{token}}",
    "session_id": {{session_id}},
    "booking_code": "{{booking_code}}"
}
```

---


### Payload Description

| **Key**        | **Data Type** | **Description**                                                 |
| -------------- | ------------- | --------------------------------------------------------------- |
| `token`        | String        | The authentication token.                     |
| `session_id`   | Integer       | Session ID from search.                             |
| `booking_code` | String        | Booking code for the room. (From search response) |

---

### Responses

#### Error Response
```json
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": "",
    "error_data": {
        "session_id": "Value for the field is invalid."
    },
    "state": "Error"
}
```

#### Success Response
```json
{
    "status": true,
    "session_id": 61,
    "data": [
        {
            "hotel_code": "1492068",
            "currency": "USD",
            "rooms": [
                {
                    "name": [
                        "Standard Apartment, 1 Bedroom,1 Queen Bed,NonSmoking"
                    ],
                    "booking_code": "1492068!TB!1!TB!3100151a-2517-4160-9947-f12580777094",
                    "inclusion": "Room Only",
                    "day_rates": [
                        [
                            {
                                "base_price": 476.61
                            },
                            {
                                "base_price": 377.14
                            },
                            {
                                "base_price": 360.57
                            },
                            {
                                "base_price": 426.88
                            },
                            {
                                "base_price": 335.7
                            },
                            {
                                "base_price": 377.14
                            },
                            {
                                "base_price": 476.61
                            }
                        ]
                    ],
                    "total_fare": 3365.63,
                    "total_tax": 534.98,
                    "room_promotion": [
                        "Book now and save"
                    ],
                    "cancel_policies": [
                        {
                            "from_date": "18-03-2025 00:00:00",
                            "charge_type": "Percentage",
                            "cancellation_charge": 100
                        }
                    ],
                    "meal_type": "Room_Only",
                    "is_refundable": false,
                    "with_transfers": false,
                    "amenities": [
                        "Non-Smoking",
                        "Television",
                        "In-room climate control (heating)",
                        "Premium bedding",
                        "Electric kettle",
                        "Satellite TV service",
                        "Limited housekeeping",
                        "In-room climate control (air conditioning)",
                        "Separate dining area",
                        "Coffee/tea maker",
                        "Daily housekeeping",
                        "Free WiFi",
                        "Bidet",
                        "Hypo-allergenic bedding available",
                        "Phone",
                        "Desk",
                        "Designer toiletries",
                        "iPod docking station",
                        "Separate living room",
                        "Towels provided",
                        "Bedsheets provided",
                        "Connecting/adjoining rooms available",
                        "DVD player",
                        "TV size measurement: inch",
                        "Stovetop",
                        "Shower/tub combination",
                        "In-room massage available",
                        "Private bathroom",
                        "Washer/dryer",
                        "Free toiletries",
                        "Wheelchair accessible",
                        "Hair dryer",
                        "Iron/ironing board",
                        "Rollaway/extra beds (surcharge)",
                        "In-room safe",
                        "Full-sized refrigerator/freezer",
                        "Dishwasher",
                        "Kitchen",
                        "Cookware, dishware, and utensils",
                        "Separate sitting area",
                        "LCD TV",
                        "Microwave",
                        "Free bottled water",
                        "Free cribs/infant beds",
                        "Housekeeping - weekdays only",
                        "Separate bedroom",
                        "Oven"
                    ]
                }
            ],
            "rate_conditions": [
                "Early check out will attract full cancellation charge unless otherwise specified.",
                "Please note that this a special rate which should be sold only with an airline ticket as part of a package.",
                "Please refer to the following Terms of Use - http://mytravelagent.online/termsofuse.pdf",
                "CheckIn Time-Begin: 3:00 PM ",
                " CheckIn Time-End: midnight",
                "CheckOut Time: 11:00 AM",
                "CheckIn Instructions: &lt;ul&gt;  &lt;li&gt;Extra-person charges may apply and vary depending on property policy&lt;/li&gt;&lt;li&gt;Government-issued photo identification and a credit card, debit card, or cash deposit may be required at check-in for incidental charges&lt;/li&gt;&lt;li&gt;Special requests are subject to availability upon check-in and may incur additional charges; special requests cannot be guaranteed&lt;/li&gt;&lt;li&gt;The name on the credit card used at check-in to pay for incidentals must be the primary name on the guestroom reservation&lt;/li&gt;&lt;li&gt;This property accepts credit cards, debit cards, and cash&lt;/li&gt;&lt;li&gt;Host has not indicated whether there is a carbon monoxide detector on the property; consider bringing a portable detector with you on the trip&lt;/li&gt;&lt;li&gt;Host has indicated there is a smoke detector on the property&lt;/li&gt;&lt;li&gt;Safety features at this property include a fire extinguisher, a security system, a first aid kit, and window guards&lt;/li&gt;&lt;li&gt;This property is professionally cleaned&lt;/li&gt;  &lt;/ul&gt; ",
                " Special Instructions : Front desk staff will greet guests on arrival at the property.",
                "Minimum CheckIn Age : 18",
                "Mandatory Fees: &lt;p&gt;You'll be asked to pay the following charges at the property. Fees may include applicable taxes:&lt;/p&gt; &lt;ul&gt;&lt;li&gt;Breakage deposit: GBP 300.00 per stay&lt;/li&gt;&lt;/ul&gt; &lt;p&gt;We have included all charges provided to us by the property. &lt;/p&gt; ",
                " Optional Fees: &lt;ul&gt; &lt;li&gt;Covered self parking fee: GBP 65.00 per day&lt;/li&gt;&lt;li&gt;Late check-out is available for a fee (subject to availability)&lt;/li&gt;&lt;li&gt;Rollaway bed fee: GBP 65.0 per night&lt;/li&gt;&lt;/ul&gt; &lt;p&gt;The above list may not be comprehensive. Fees and deposits may not include tax and are subject to change. &lt;/p&gt;",
                "Cards Accepted: Visa,Debit cards,Cash,American Express,Mastercard",
                "&lt;ul&gt;  &lt;li&gt;The property has connecting/adjoining rooms, which are subject to availability and can be requested by contacting the property using the number on the booking confirmation. &lt;/li&gt;&lt;li&gt;The property is professionally cleaned.&lt;/li&gt;&lt;li&gt;Contactless check-in and contactless check-out are available.&lt;/li&gt; &lt;/ul&gt;,Pets not allowed,Professional property host/manager,Contactless check-out is available,Property uses a professional cleaning service,Contactless check-in is available,Essential workers only - NO"
            ]
        }
    ]
}
```