## TBO Air Search API

This search API allows you to search for flights for different journey types: One-Way, Round Trip or Multi-City

### Request Details

URL: `{{base_url}}/api/servicegroup/search/tbo-air/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

### **Example Payload**

```json
{
    "token": "{{token}}",
    "session_id": 100
}
```

---


### Payload Description


| **Key**      | **Data Type** | **Description**                                   |
| ------------ | ------------- | ------------------------------------------------- |
| `token`      | String        | The authentication token.                         |
| `session_id` | Integer       | A dynamically generated session ID (From Search). |

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
    "status": "S",
    "data": {
        "booking_status": "Confirmed",
        "voucher_status": true,
        "confirmation_number": "V3ES0M",
        "invoice_number": "MW283009",
        "check_in": "2025-10-01T00:00:00",
        "check_out": "2025-10-08T00:00:00",
        "booking_date": "2025-03-19T00:00:00",
        "no_of_rooms": 1,
        "hotel_details": {
            "hotel_name": "Mayfair House",
            "rating": "FiveStar",
            "address_line_1": "22-28 Shepherd Street Mayfair ",
            "map": "51.50607|-0.14797",
            "city": "London"
        },
        "rooms": [
            {
                "currency": "USD",
                "status": "Not Cancelled",
                "name": [
                    "Standard Apartment, 1 Bedroom,1 Queen Bed,NonSmoking"
                ],
                "inclusion": "Room Only",
                "total_fare": 3365.63,
                "total_tax": 534.98,
                "room_promotion": "Book now and save",
                "cancel_policies": [
                    {
                        "from_date": "18-03-2025 00:00:00",
                        "charge_type": "Percentage",
                        "cancellation_charge": 100
                    }
                ],
                "meal_type": "Room_Only",
                "is_refundable": false,
                "customer_details": [
                    {
                        "customer_names": [
                            {
                                "title": "Mr",
                                "first_name": "TestGuest",
                                "last_name": "One",
                                "type": "Adult"
                            }
                        ]
                    }
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
}
```