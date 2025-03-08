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

### Success Response

```json
{
    "status": true,
    "session_id": 48,
    "data": [
        {
            "flight_id": "51636620-9313-42df-8ee9-8290cf4661ad",
            "origin": "DXB",
            "destination": "BAH",
            "is_lcc": false,
            "non_refundable": false,
            "airline_remark": "",
            "fare": {
                "total_fare": 535.6364904144,
                "fare_type": "RP",
                "agent_markup": 0.0,
                "other_charges": 0.0,
                "credit_card_charge": 0.0,
                "agent_preferred_currency": "USD",
                "service_fee": 0.0,
                "base_fare": 360.356358672,
                "tax": 175.2801317424,
                "penalty_amount": 0.0,
                "vat_amount": 0.0,
                "vat_percentage": 0.0
            },
            "fare_breakdown": [
                {
                    "currency": "USD",
                    "passenger_type": 1,
                    "passenger_count": 2,
                    "total_fare": 535.6364904144,
                    "other_charges": 0.0,
                    "agent_markup": 0.0,
                    "service_fee": 0.0,
                    "base_fare": 360.356358672,
                    "tax": 175.2801317424,
                    "penalty_amount": 0.0,
                    "credit_card_charge": 0.0,
                    "tax_breakup_list": [
                        {
                            "type": "Taxes & Fees",
                            "amount": 175.2801317424
                        }
                    ],
                    "vat_amount": 0.0,
                    "vat_percentage": 0.0
                }
            ],
            "last_ticket_date": "29APR25",
            "ticket_advisory": "PENALTY APPLIES \nLAST TKT DTE 29APR25  - DATE OF ORIGIN \n",
            "segments": [
                {
                    "segment_id": 0,
                    "seats_available": 9,
                    "alliance_info": "",
                    "flight_info_index": null,
                    "operating_carrier": "FZ",
                    "segment_indicator": 1,
                    "airline": "FZ",
                    "origin": {
                        "airport_code": "DXB",
                        "airport_name": "Dubai",
                        "city_code": "DXB",
                        "city_name": "Dubai",
                        "country_code": "AE",
                        "country_name": "United Arab Emirates",
                        "terminal": "2"
                    },
                    "destination": {
                        "airport_code": "BAH",
                        "airport_name": "Bahrain Int'l",
                        "city_code": "BAH",
                        "city_name": "Bahrain",
                        "country_code": "BH",
                        "country_name": "Bahrain",
                        "terminal": ""
                    },
                    "flight_number": "29",
                    "departure_time": "2025-04-29T00:25:00",
                    "arrival_time": "2025-04-29T00:40:00",
                    "booking_class": "K",
                    "availability": null,
                    "flight_status": 0,
                    "status": null,
                    "meal_type": null,
                    "eticket_eligible": true,
                    "airline_pnr": null,
                    "craft": "7M8",
                    "stopover": false,
                    "stops": 0,
                    "mile": 0,
                    "duration": "01:15:00",
                    "ground_time": "00:00:00",
                    "accumulated_duration": "01:15:00",
                    "stop_point": null,
                    "stop_point_arrival_time": "0001-01-01T00:00:00",
                    "stop_point_departure_time": "0001-01-01T00:00:00",
                    "included_baggage": "20 KG",
                    "cabin_baggage": "Included",
                    "cabin_class": "Economy",
                    "additional_baggage": null,
                    "airline_details": {
                        "airline_code": "FZ",
                        "flight_number": "29",
                        "craft": "7M8",
                        "airline_name": "Fly Dubai",
                        "operating_carrier": "FZ",
                        "alliance_info": ""
                    },
                    "airline_name": "Fly Dubai",
                    "departure_datetime": null,
                    "departure_date": null,
                    "arrival_datetime": null,
                    "arrival_date": null,
                    "layover_text": null,
                    "in_flight_services": null,
                    "fare_family_class": ""
                }
            ],
            "fare_rules": [
                {
                    "origin": "DXB",
                    "destination": "BAH",
                    "airline": "FZ",
                    "fare_restriction": "Y",
                    "fare_basis_code": "KOB7AE1",
                    "fare_family_code": null,
                    "fare_rule_detail": null,
                    "fare_rule_index": null,
                    "departure_date": "0001-01-01T00:00:00",
                    "flight_number": null,
                    "free_text_fare_rule_detail": null
                }
            ],
            "provider_remarks": "",
            "validating_airline": "FZ",
            "trip_indicator": "outbound",
            "response_time": "2025-03-08T05:25:14",
            "journey_type": "O",
            "is_void_allowed": false,
            "is_refund_allowed": false,
            "is_reissue_allowed": false,
            "corporate_code_detail": null,
            "is_show_upsell_option": false,
            "upsell_options_list": null,
            "is_check_in_baggage_fare": true,
            "required_field_validators": null,
            "mini_fare_rules": null,
            "is_vat_applicable": false,
            "fare_classification": null
        }
    ]
}
```
