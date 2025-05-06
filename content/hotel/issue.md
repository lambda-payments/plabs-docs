## Hotel Issue API

This API allows you to create a booking for a hotel.

### Request Details

URL: `{{base_url}}/api/servicegroup/issue/hotel/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

### **Example Payload**

```json
{
    "token": "{{token}}",
    "session_id": {{session_id}},
    "email": "test@gmail.com",
    "phone": "9800101122",
    "customer_identifier": "customer@test.com",
    "remarks": "Test Txn",
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
```

---


### Payload Description


| **Key**               | **Data Type**    | **Description**                                                        |
| --------------------- | ---------------- | ---------------------------------------------------------------------- |
| `token`               | String           | The authentication token.                                              |
| `session_id`          | Integer          | A dynamically generated session ID (From Search).                      |
| `email`               | String           | The email address of the customer.                                     |
| `phone`               | String           | The phone number of the customer.                                      |
| `remarks`             | Optional(String) | Transaction remarks for the booking.                                   |
| `customer_identifier` | Optional(String) | User Identifier at the client end.                                     |
| `customer_details`    | List (Array)     | A list of customer details, which contains the customer name and type. |

### Customer Details Description

| **Key**          | **Data Type** | **Description**                                                             |
| ---------------- | ------------- | --------------------------------------------------------------------------- |
| `customer_names` | List (Array)  | A list of customer names with their title, first name, last name, and type. |

---

#### Customer Names Description

| **Key**      | **Data Type** | **Description**                                  |
| ------------ | ------------- | ------------------------------------------------ |
| `title`      | String        | The title of the customer (e.g., Mr, Mrs, etc.). |
| `first_name` | String        | The first name of the customer.                  |
| `last_name`  | String        | The last name of the customer.                   |
| `type`       | String        | The type of the customer (e.g., Adult, Child).   |

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
        "session_id": "This field cannot be blank."
    },
    "state": "Error"
}
```

#### Success Response
```json
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "total_fare": 3365.63,
        "pax_rooms": [
            {
                "adults": 1,
                "children": 0,
                "children_ages": []
            }
        ],
        "checkin_date": "2025-10-01",
        "checkout_date": "2025-10-08"
    },
    "detail": {
        "client_reference_id": "61",
        "confirmation_number": "V3ES0M"
    },
    "credits_consumed": 3365.63,
    "credits_available": 99944586.39197989,
    "id": 63
}
```