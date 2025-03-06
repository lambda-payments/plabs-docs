## TBO Air Search API

This search API allows you to search for flights for different journey types: One-Way, Round Trip or Multi-City

### Request Details

URL: {{base_url}}/api/servicegroup/search/tbo-air/

Method: POST

Headers: `'Content-Type': 'application/json'`


### **Example Payload**

```json
{
  "reference": "unique_ref_123",
  "point_of_sale": "IN",
  "request_origin": "India",
  "adult_count": 1,
  "child_count": 1,
  "infant_count": 0,
  "journey_type": "O",
  "segments": [
    {
      "origin": "DEL",
      "destination": "BOM",
      "preferred_departure_date": "2025-03-10",
      "preferred_arrival_date": "2025-03-11",
      "preferred_airlines": ["AI"]
    }
  ],
  "flight_cabin_class": "AC"
}
```

---

### **Payload Description**

| **Field**                     | **Validation**                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `reference`                   | Must be unique.                                                                                                           |
| `point_of_sale`               | Defaults to `"IN"` if not provided.                                                                                       |
| `request_origin`              | Defaults to `"India"` if not provided.                                                                                    |
| `adult_count`                 | Must be an integer.                                                                                                       |
| `child_count`                 | Must be an integer.                                                                                                       |
| `infant_count`                | Must be an integer.                                                                                                       |
| `adult_count` & `child_count` | At least one must be greater than zero.                                                                                   |
| `journey_type`                | Required and must match one of the valid choices (Reference [table below](#valid-journey_type-values)).                   |
| `segments[]`                  | Must be a **non-empty array** of flight segments (Reference [table below](#structure-of-each-segment-in-segments-array)). |
| `flight_cabin_class`          | Defaults to `AC` (All class). (Reference [table below](#flight-cabin-class-choices))                                      |

#### **Valid `journey_type` Values**

| **Value** | **Description** |
| --------- | --------------- |
| `"O"`     | One Way         |
| `"R"`     | Return          |
| `"M"`     | Multi City      |

#### **Structure of Each Segment in `segments` Array**

| **Segment Field**          | **Validation**                                              |
| -------------------------- | ----------------------------------------------------------- |
| `origin`                   | Required, must be a valid sector code.                      |
| `destination`              | Required, must be a valid sector code.                      |
| `preferred_departure_date` | Required, must be in a valid date format (`YYYY-MM-DD`).    |
| `preferred_arrival_date`   | Optional, must be in a valid date format (`YYYY-MM-DD`).    |
| `preferred_airlines`       | Optional list of airline codes (no validation implemented). |

#### **Flight Cabin Class Choices**

| **Value** | **Description**  |
| --------- | ---------------- |
| `"AC"`    | All Class        |
| `"EC"`    | Economy          |
| `"PE"`    | Premium Economy  |
| `"BC"`    | Business         |
| `"PB"`    | Premium Business |
| `"FC"`    | First            |


---

### Example Error Responses

#### Validation Error
```json
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": "",
    "error_data": {
        "journey_type": "Invalid choice for journey_type. Options: ['O', 'R', 'M']",
        "segments": [
            {
                "destination": "Sector Not found",
                "preferred_arrival_date": "Invalid date format for: 08-22-10. Accepted formats: [YYYY-MM-DD, YYYY-MM-DDTHH:MM:SS]"
            }
        ],
        "flight_cabin_class": "Invalid choice for flight_cabin_class. Options: ['AC', 'EC', 'PE', 'BC', 'PB', 'FC']",
        "non_field_errors": [
            "At least one adult or child is required."
        ]
    },
    "state": "Error"
}
```

#### Duplicate Referemce

```json
{
    "status": false,
    "error_code": "1013",
    "message": "Request with duplicate reference id obtained",
    "error": "duplicate_request",
    "details": "",
    "error_data": {},
    "state": "Error"
}
```
