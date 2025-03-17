## TBO Air Search API

This search API allows you to search for flights for different journey types: One-Way, Round Trip or Multi-City

### Request Details

URL: {{base_url}}/api/servicegroup/search/tbo-air/

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