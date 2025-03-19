## TBO Air Search API

This search API allows you to search for flights for different journey types: One-Way, Round Trip or Multi-City

### Request Details

URL: {{base_url}}/api/servicegroup/search/tbo-hotels/

Method: POST

Headers: `'Content-Type': 'application/json'`

### **Example Payload**

```json
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "checkin_date": "2025-10-01",
    "checkout_date": "2025-10-08",
    "city_code": "143851",
    "nationality": "AE",
    "pax_rooms": [
         {
            "adults": 1,
            "children": 0,
            "children_ages": []
        }
    ]
}
```

---


### Payload Description

| **Key**           | **Data Type**     | **Description**                                           |
|-------------------|-------------------|-----------------------------------------------------------|
| `token`           | String            | A placeholder for the authentication token.               |
| `reference`       | String            | A unique identifier for the booking request, generated dynamically. |
| `checkin_date`    | Date (String)     | The date when the customer is expected to check in.       |
| `checkout_date`   | Date (String)     | The date when the customer is expected to check out.      |
| `city_code`       | String            | A numeric code representing the city associated with the booking. |
| `nationality`     | String            | The nationality code of the customer (e.g., "AE" for UAE).|
| `pax_rooms`       | List (Array)      | A list of rooms with the number of adults and children, as well as their ages. ([below](#pax-rooms-description))|


### Pax Rooms Description

| **Key**           | **Data Type**     | **Description**                                           |
|-------------------|-------------------|-----------------------------------------------------------|
| `adults`          | Integer           | The number of adults in the room.                         |
| `children`        | Integer           | The number of children in the room.                       |
| `children_ages`   | List (Array)      | A list of ages of the children in the room (if any).      |

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
        "country": "Nationality Not found"
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
                    "total_fare": 12351.86,
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
                    "commission": 0
                }
            ],
            "name": "",
            "city": "",
            "rating": "",
            "address": "",
            "attractions": [],
            "country_name": "",
            "description": "",
            "trip_advisor_rating": "",
            "trip_advisor_review_url": "",
            "fax_number": "",
            "facilities": [],
            "map_lat_long": "",
            "phone_number": "",
            "pin_code": "",
            "website_url": ""
        }
    ]
}
```