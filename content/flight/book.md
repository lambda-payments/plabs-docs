## Flight Book API

This API allows you to Select a flight to proceed further with ticket issue.

### Request Details

URL: `{{base_url}}/api/servicegroup/book/flight/`

Method: `POST`

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

### Success Responses

#### Non LCC Airlines

```json
{
    "status": true,
    "data": {
        "farequote": {
            "is_price_changed": false,
            "result": [
                {
                    "flight_id": "73dbce73-089d-4e99-b572-39a95c648592",
                    "origin": "DXB",
                    "destination": "BAH",
                    "is_lcc": false,
                    "non_refundable": false,
                    "airline_remark": "",
                    "fare": {
                        "total_fare": 520.5341770008,
                        "fare_type": "RP",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 0.0,
                        "base_fare": 345.633060846,
                        "tax": 174.9011161548,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_breakdown": [
                        {
                            "currency": "USD",
                            "passenger_type": 1,
                            "passenger_count": 2,
                            "total_fare": 520.5341770008,
                            "other_charges": 0.0,
                            "agent_markup": 0.0,
                            "service_fee": 0.0,
                            "base_fare": 345.633060846,
                            "tax": 174.9011161548,
                            "penalty_amount": 0.0,
                            "credit_card_charge": 0.0,
                            "vat_amount": 0.0,
                            "vat_percentage": 0.0
                        }
                    ],
                    "last_ticket_date": "10JUL25",
                    "ticket_advisory": "PENALTY APPLIES \nLAST TKT DTE 10JUL25  - DATE OF ORIGIN \n",
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
                            "flight_number": "23",
                            "departure_time": "2025-07-10T07:15:00",
                            "arrival_time": "2025-07-10T07:30:00",
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
                                "flight_number": "23",
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
                            "departure_date": "2025-07-10T07:15:00",
                            "flight_number": null,
                            "free_text_fare_rule_detail": null
                        }
                    ],
                    "provider_remarks": null,
                    "validating_airline": "FZ",
                    "trip_indicator": 1,
                    "response_time": "2025-03-23T15:29:42.538187Z",
                    "journey_type": "O",
                    "is_void_allowed": false,
                    "is_refund_allowed": false,
                    "is_reissue_allowed": false,
                    "corporate_code_detail": null,
                    "is_show_upsell_option": false,
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
        "ssr_options": {
            "baggage_list": {},
            "meal_dynamic_list": {},
            "seat_dynamic_list": {
                "outward": [
                    {
                        "row_seats": [
                            {
                                "seat_info": [
                                    {
                                        "airline_code": "FZ",
                                        "flight_number": "23",
                                        "craft_type": "",
                                        "origin": "DXB",
                                        "destination": "BAH",
                                        "availability_type": 0,
                                        "description": 2,
                                        "code": "NoSeat",
                                        "seat_type": 0,
                                        "seat_no": null,
                                        "row_no": "0",
                                        "seat_way_type": 2,
                                        "compartment": 1,
                                        "deck": 1,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T07:15:00",
                                        "serial_no": 0,
                                        "seat_key": null
                                    }
                                ]
                            }
                        ],
                        "max_seats_in_each_row": 0
                    }
                ]
            },
            "meal_list": {
                "outward": [
                    {
                        "code": "LCML",
                        "description": "Low Calorie"
                    },
                    {
                        "code": "LFML",
                        "description": "Low Cholesterol/Fat"
                    },
                    {
                        "code": "LPML",
                        "description": "Low Protein"
                    },
                    {
                        "code": "LSML",
                        "description": "Low Sodium/No Salt"
                    },
                    {
                        "code": "MOML",
                        "description": "Moslem"
                    },
                    {
                        "code": "NLML",
                        "description": "Non Lactose"
                    },
                    {
                        "code": "ORML",
                        "description": "Oriental"
                    },
                    {
                        "code": "PRML",
                        "description": "Low Purin"
                    },
                    {
                        "code": "RVML",
                        "description": "Raw Vegetarian"
                    },
                    {
                        "code": "SFML",
                        "description": "Seafood"
                    },
                    {
                        "code": "SPML",
                        "description": "Special Meal"
                    },
                    {
                        "code": "VGML",
                        "description": "Veg/Non Dairy"
                    },
                    {
                        "code": "VJML",
                        "description": "Vegetarian Jain"
                    },
                    {
                        "code": "VLML",
                        "description": "Veg/Milk/Eggs"
                    },
                    {
                        "code": "VOML",
                        "description": "Vegetarian Oriental"
                    }
                ]
            },
            "seat_list": {}
        }
    }
}
```

#### LCC Airlines
```json
{
    "status": true,
    "data": {
        "farequote": {
            "is_price_changed": false,
            "result": [
                {
                    "flight_id": "e7107966-0777-4e11-b639-61c73a4e5438",
                    "origin": "DEL",
                    "destination": "BOM",
                    "is_lcc": true,
                    "non_refundable": false,
                    "airline_remark": "This is a Xpress Value fare",
                    "fare": {
                        "total_fare": 44.1990485232,
                        "fare_type": "PUB",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 0.0,
                        "base_fare": 26.2103856348,
                        "tax": 17.9886628884,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_breakdown": [
                        {
                            "currency": "USD",
                            "passenger_type": 1,
                            "passenger_count": 2,
                            "total_fare": 44.1990485232,
                            "other_charges": 0.0,
                            "agent_markup": 0.0,
                            "service_fee": 0.0,
                            "base_fare": 26.2103856348,
                            "tax": 17.9886628884,
                            "penalty_amount": 0.0,
                            "credit_card_charge": 0.0,
                            "vat_amount": 0.0,
                            "vat_percentage": 0.0
                        }
                    ],
                    "last_ticket_date": "2025-07-07T21:10:00",
                    "ticket_advisory": null,
                    "segments": [
                        {
                            "segment_id": 0,
                            "seats_available": 9,
                            "alliance_info": null,
                            "flight_info_index": null,
                            "operating_carrier": null,
                            "segment_indicator": 1,
                            "airline": "IX",
                            "origin": {
                                "airport_code": "DEL",
                                "airport_name": "Indira Gandhi Airport",
                                "city_code": "DEL",
                                "city_name": "Delhi",
                                "country_code": "IN",
                                "country_name": "India",
                                "terminal": "3"
                            },
                            "destination": {
                                "airport_code": "BOM",
                                "airport_name": "Chhatrapati Shivaji Maharaj International Airport",
                                "city_code": "BOM",
                                "city_name": "Mumbai",
                                "country_code": "IN",
                                "country_name": "India",
                                "terminal": "2"
                            },
                            "flight_number": "1163",
                            "departure_time": "2025-07-10T21:10:00",
                            "arrival_time": "2025-07-10T23:35:00",
                            "booking_class": "XC",
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
                            "duration": "02:25:00",
                            "ground_time": "00:00:00",
                            "accumulated_duration": "02:25:00",
                            "stop_point": "",
                            "stop_point_arrival_time": "0001-01-01T00:00:00",
                            "stop_point_departure_time": "0001-01-01T00:00:00",
                            "included_baggage": "15Kg",
                            "cabin_baggage": "7Kg",
                            "cabin_class": "Economy",
                            "additional_baggage": null,
                            "airline_details": {
                                "airline_code": "IX",
                                "flight_number": "1163",
                                "craft": "7M8",
                                "airline_name": "Air India Express",
                                "operating_carrier": null,
                                "alliance_info": null
                            },
                            "airline_name": "Air India Express",
                            "departure_datetime": null,
                            "departure_date": null,
                            "arrival_datetime": null,
                            "arrival_date": null,
                            "layover_text": null,
                            "in_flight_services": [],
                            "fare_family_class": "Xpress Value"
                        }
                    ],
                    "fare_rules": [
                        {
                            "origin": "DEL",
                            "destination": "BOM",
                            "airline": "IX",
                            "fare_restriction": null,
                            "fare_basis_code": "XNRA015",
                            "fare_family_code": null,
                            "fare_rule_detail": "",
                            "fare_rule_index": null,
                            "departure_date": "0001-01-01T00:00:00",
                            "flight_number": null,
                            "free_text_fare_rule_detail": null
                        }
                    ],
                    "provider_remarks": null,
                    "validating_airline": "IX",
                    "trip_indicator": 1,
                    "response_time": "2025-03-23T15:33:32.9764998Z",
                    "journey_type": "O",
                    "is_void_allowed": false,
                    "is_refund_allowed": false,
                    "is_reissue_allowed": false,
                    "corporate_code_detail": null,
                    "is_show_upsell_option": false,
                    "upsell_options_list": null,
                    "is_check_in_baggage_fare": false,
                    "required_field_validators": null,
                    "is_vat_applicable": false
                }
            ],
            "is_document_info_req_on_hold": false,
            "is_document_full_info_req": true,
            "is_document_full_detail_required_at_book": true,
            "is_document_info_req_on_ticket": true,
            "is_passport_info_req_on_hold": false,
            "is_passport_full_info_req": true,
            "is_baggage_changed": false,
            "is_passport_full_detail_required_at_book": true,
            "foid_details": {},
            "is_passport_info_req_on_ticket": true,
            "valid_document_types": [
                "Passport"
            ],
            "local_currency": "USD",
            "local_currency_roe": 1.0,
            "nationalities_for_optional_passport": []
        },
        "ssr_options": {
            "baggage_list": {
                "outward": [
                    {
                        "code": "NONE",
                        "description": 2,
                        "price": 0.0,
                        "weight": 0,
                        "text": "0 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": null
                    },
                    {
                        "code": "SBHA",
                        "description": 2,
                        "price": 21.8662839,
                        "weight": 1,
                        "text": "1 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": "MSFNQ0ZCUkZRLSFTQkhBISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MSFNU0ZCUkZRLSFTQkhBISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    },
                    {
                        "code": "SBHC",
                        "description": 2,
                        "price": 65.5988517,
                        "weight": 3,
                        "text": "3 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": "MSFNQ0ZCUkZRLSFTQkhDISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MSFNU0ZCUkZRLSFTQkhDISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    },
                    {
                        "code": "PBCA",
                        "description": 2,
                        "price": 13.11977034,
                        "weight": 3,
                        "text": "3 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": "MSFNQ0ZCUkZRLSFQQkNBISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MSFNU0ZCUkZRLSFQQkNBISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    },
                    {
                        "code": "PBCB",
                        "description": 2,
                        "price": 21.8662839,
                        "weight": 5,
                        "text": "5 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": "MSFNQ0ZCUkZRLSFQQkNCISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MSFNU0ZCUkZRLSFQQkNCISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    },
                    {
                        "code": "PBAF",
                        "description": 2,
                        "price": 200.44093575,
                        "weight": 25,
                        "text": "25 KG",
                        "way_type_field": 2,
                        "origin": "DEL",
                        "destination": "BOM",
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "airline_code": "IX",
                        "baggage_key": "MSFNQ0ZCUkZRLSFQQkFGISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MSFNU0ZCUkZRLSFQQkFGISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    }
                ]
            },
            "meal_dynamic_list": {
                "outward": [
                    {
                        "code": "NONE",
                        "description": 2,
                        "airline_description": null,
                        "price": 0.0,
                        "quantity": 0,
                        "text": "Add",
                        "destination": "BOM",
                        "origin": "DEL",
                        "way_type_field": 2,
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "meal_key": null
                    },
                    {
                        "code": "VMFB",
                        "description": 2,
                        "airline_description": "Vegetable Manchurian with Fried Rice",
                        "price": 8.74651356,
                        "quantity": 1,
                        "text": "Add",
                        "destination": "BOM",
                        "origin": "DEL",
                        "way_type_field": 2,
                        "currency": "USD",
                        "flight_number": "1163",
                        "departure_time": "2025-07-10T21:10:00",
                        "meal_key": "MiFNQ0ZCUkZRLSFWTUZCISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-#TBO#MiFNU0ZCUkZRLSFWTUZCISFCT00hSVghNjM4ODc3MDI0MDAwMDAwMDAwIURFTCExMTYzISA-"
                    }
                ]
            },
            "seat_dynamic_list": {
                "outward": [
                    {
                        "row_seats": [
                            {
                                "seat_info": [
                                    {
                                        "airline_code": "IX",
                                        "flight_number": "1163",
                                        "craft_type": "7M8",
                                        "origin": "DEL",
                                        "destination": "BOM",
                                        "availability_type": 0,
                                        "description": 2,
                                        "code": "NoSeat",
                                        "seat_type": 0,
                                        "seat_no": null,
                                        "row_no": "0",
                                        "seat_way_type": 2,
                                        "compartment": 0,
                                        "deck": 0,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T21:10:00",
                                        "serial_no": 0,
                                        "seat_key": null
                                    }
                                ]
                            },
                            {
                                "seat_info": [
                                    {
                                        "airline_code": "IX",
                                        "flight_number": "1163",
                                        "craft_type": "7M8",
                                        "origin": "DEL",
                                        "destination": "BOM",
                                        "availability_type": 3,
                                        "description": 2,
                                        "code": "1A",
                                        "seat_type": 1,
                                        "seat_no": "A",
                                        "row_no": "1",
                                        "seat_way_type": 2,
                                        "compartment": 1,
                                        "deck": 1,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T21:10:00",
                                        "serial_no": 1,
                                        "seat_key": "SVghMTE2MyEgITYzODg3Nzc4NjAwMDAwMDAwMCFERUwhQk9NITFBIUM-"
                                    },
                                    {
                                        "airline_code": "IX",
                                        "flight_number": "1163",
                                        "craft_type": "7M8",
                                        "origin": "DEL",
                                        "destination": "BOM",
                                        "availability_type": 3,
                                        "description": 2,
                                        "code": "1C",
                                        "seat_type": 2,
                                        "seat_no": "C",
                                        "row_no": "1",
                                        "seat_way_type": 2,
                                        "compartment": 1,
                                        "deck": 1,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T21:10:00",
                                        "serial_no": 2,
                                        "seat_key": "SVghMTE2MyEgITYzODg3Nzc4NjAwMDAwMDAwMCFERUwhQk9NITFDIUM-"
                                    },
                                    {
                                        "airline_code": "IX",
                                        "flight_number": "1163",
                                        "craft_type": "7M8",
                                        "origin": "DEL",
                                        "destination": "BOM",
                                        "availability_type": 3,
                                        "description": 2,
                                        "code": "1D",
                                        "seat_type": 2,
                                        "seat_no": "D",
                                        "row_no": "1",
                                        "seat_way_type": 2,
                                        "compartment": 1,
                                        "deck": 1,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T21:10:00",
                                        "serial_no": 3,
                                        "seat_key": "SVghMTE2MyEgITYzODg3Nzc4NjAwMDAwMDAwMCFERUwhQk9NITFEIUM-"
                                    },
                                    {
                                        "airline_code": "IX",
                                        "flight_number": "1163",
                                        "craft_type": "7M8",
                                        "origin": "DEL",
                                        "destination": "BOM",
                                        "availability_type": 3,
                                        "description": 2,
                                        "code": "1F",
                                        "seat_type": 1,
                                        "seat_no": "F",
                                        "row_no": "1",
                                        "seat_way_type": 2,
                                        "compartment": 1,
                                        "deck": 1,
                                        "currency": "USD",
                                        "price": 0.0,
                                        "remarks": null,
                                        "departure_time": "2025-07-10T21:10:00",
                                        "serial_no": 4,
                                        "seat_key": "SVghMTE2MyEgITYzODg3Nzc4NjAwMDAwMDAwMCFERUwhQk9NITFGIUM-"
                                    }
                                ]
                            }
                        ],
                        "max_seats_in_each_row": 0
                    }
                ]
            },
            "meal_list": {},
            "seat_list": {}
        }
    }
}
```
