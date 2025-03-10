## TBO Air Book API

This search API allows you to Select a flight to proceed further with ticket issue.

### Request Details

URL: {{base_url}}/api/servicegroup/book/tbo-air/

Method: POST

Headers: `'Content-Type': 'application/json'`


### **Example Payload**

```json
{
    "flight_id": "c5bf0227-3b98-44df-ac9d-e27d78747709",
    "session_id": 58,
    "token": "top_secret_token"
}
```

---

### **Payload Description**

| **Field**    | **Type** | **Description**                                     |
| ------------ | -------- | --------------------------------------------------- |
| `flight_id`  | String   | Unique identifier for the flight selection.         |
| `session_id` | Integer  | Session ID for tracking the flight booking session. |
| `token`      | String   | Secure token used for authentication.               |


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
        "session_id": "Invalid value for field."
    },
    "state": "Error"
}
```

### Success Response

```json
{
    "status": true,
    "data": {
        "farequote": {
            "is_price_changed": false,
            "result": [
                {
                    "flight_id": "3cec60ee-2d08-4e16-a9aa-a39ed0fb8c53",
                    "origin": "BAH",
                    "destination": "DXB",
                    "is_lcc": false,
                    "non_refundable": false,
                    "airline_remark": "",
                    "fare": {
                        "total_fare": 596.8968186836,
                        "fare_type": "RP",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 4.0,
                        "base_fare": 387.76210116,
                        "tax": 205.1347175236,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_breakdown": [
                        {
                            "currency": "USD",
                            "passenger_type": 1,
                            "passenger_count": 2,
                            "total_fare": 596.8968186836,
                            "other_charges": 0.0,
                            "agent_markup": 0.0,
                            "service_fee": 4.0,
                            "base_fare": 387.76210116,
                            "tax": 205.1347175236,
                            "penalty_amount": 0.0,
                            "credit_card_charge": 0.0,
                            "vat_amount": 0.0,
                            "vat_percentage": 0.0
                        }
                    ],
                    "last_ticket_date": "27JUN24",
                    "ticket_advisory": "TICKETS ARE NON REFUNDABLE AFTER DEPARTURE \nLAST TKT DTE 27JUN24  - DATE OF ORIGIN \n",
                    "segments": [
                        {
                            "segment_id": 0,
                            "seats_available": 9,
                            "alliance_info": "",
                            "flight_info_index": null,
                            "operating_carrier": "EK",
                            "segment_indicator": 1,
                            "airline": "EK",
                            "origin": {
                                "airport_code": "BAH",
                                "airport_name": "Bahrain Int'l",
                                "city_code": "BAH",
                                "city_name": "Bahrain",
                                "country_code": "BH",
                                "country_name": "Bahrain",
                                "terminal": ""
                            },
                            "destination": {
                                "airport_code": "DXB",
                                "airport_name": "Dubai",
                                "city_code": "DXB",
                                "city_name": "Dubai",
                                "country_code": "AE",
                                "country_name": "United Arab Emirates",
                                "terminal": "3"
                            },
                            "flight_number": "836",
                            "departure_time": "2024-06-27T03:40:00",
                            "arrival_time": "2024-06-27T06:05:00",
                            "booking_class": "Q",
                            "availability": null,
                            "flight_status": 0,
                            "status": null,
                            "meal_type": null,
                            "eticket_eligible": true,
                            "airline_pnr": null,
                            "craft": "77W",
                            "stopover": false,
                            "stops": 0,
                            "mile": 0,
                            "duration": "01:25:00",
                            "ground_time": "00:00:00",
                            "accumulated_duration": "01:25:00",
                            "stop_point": null,
                            "stop_point_arrival_time": "0001-01-01T00:00:00",
                            "stop_point_departure_time": "0001-01-01T00:00:00",
                            "included_baggage": "25 KG",
                            "cabin_baggage": "1 PC(s)",
                            "cabin_class": "Economy",
                            "additional_baggage": null,
                            "airline_details": {
                                "airline_code": "EK",
                                "flight_number": "836",
                                "craft": "77W",
                                "airline_name": "Emirates Airlines",
                                "operating_carrier": "EK",
                                "alliance_info": ""
                            },
                            "airline_name": "Emirates Airlines",
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
                            "origin": "BAH",
                            "destination": "DXB",
                            "airline": "EK",
                            "fare_restriction": "Y",
                            "fare_basis_code": "QEEOPBH1",
                            "fare_family_code": "ECOSAVER",
                            "fare_rule_detail": null,
                            "fare_rule_index": null,
                            "departure_date": "2024-06-27T03:40:00",
                            "flight_number": null,
                            "free_text_fare_rule_detail": null
                        }
                    ],
                    "provider_remarks": null,
                    "validating_airline": "EK",
                    "trip_indicator": 1,
                    "response_time": "2024-06-10T15:00:26.9954866Z",
                    "journey_type": "O",
                    "is_void_allowed": true,
                    "is_refund_allowed": false,
                    "is_reissue_allowed": false,
                    "corporate_code_detail": null,
                    "is_show_upsell_option": true,
                    "upsell_options_list": null,
                    "is_check_in_baggage_fare": false,
                    "required_field_validators": null,
                    "is_vat_applicable": false
                }
            ],
            "is_document_info_req_on_hold": false,
            "is_document_full_info_req": false,
            "is_document_full_detail_required_at_book": false,
            "is_document_info_req_on_ticket": true,
            "is_passport_info_req_on_hold": false,
            "is_passport_full_info_req": false,
            "is_baggage_changed": false,
            "is_passport_full_detail_required_at_book": false,
            "foid_details": {},
            "is_passport_info_req_on_ticket": true,
            "valid_document_types": [
                "Passport"
            ],
            "local_currency": "USD",
            "local_currency_roe": 1.0,
            "nationalities_for_optional_passport": []
        },
        "ssr_options": {}
    }
}
```
