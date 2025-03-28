## TBO Air Get Ticket Details API

This API allows you to get details for the ticket, which can be used in ticket generation.

### Request Details

URL: {{base_url}}/api/servicegroup/issue/tbo-air/

Method: POST

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "session_id": 0,
    "token": "top_secret_token",
    "pnr": "SOMEPNR"
}
```

---

### **Payload Description**

| **Field**    | **Type** | **Description**                       |
| ------------ | -------- | ------------------------------------- |
| `session_id` | Integer  | Unique identifier for the session.    |
| `token`      | String   | Secure token used for authentication. |
| `pnr`      | String   | Flight PNR obtained in issue response. |

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
        "session_id": "This field cannot be blank"
    },
    "state": "Error"
}
```

### Success Response

```json
{
    "status": true,
    "data": {
        "itinerary": {
            "segments": [
                {
                    "segment_id": 90178,
                    "seats_available": 0,
                    "alliance_info": null,
                    "flight_info_index": null,
                    "operating_carrier": "EY",
                    "segment_indicator": 1,
                    "airline": "EY",
                    "origin": {
                        "airport_code": "DOH",
                        "airport_name": "Doha",
                        "city_code": "DOH",
                        "city_name": "Doha",
                        "country_code": "QA",
                        "country_name": null,
                        "terminal": null
                    },
                    "destination": {
                        "airport_code": "AUH",
                        "airport_name": "Abu Dhabi Int'l",
                        "city_code": "AUH",
                        "city_name": "Abu Dhabi",
                        "country_code": "AE",
                        "country_name": null,
                        "terminal": "A"
                    },
                    "flight_number": "664",
                    "departure_time": "2025-07-10T04:10:00",
                    "arrival_time": "2025-07-10T06:10:00",
                    "booking_class": "Q",
                    "availability": null,
                    "flight_status": 0,
                    "status": "HK",
                    "meal_type": null,
                    "eticket_eligible": true,
                    "airline_pnr": "VORK8F",
                    "craft": "320",
                    "stopover": false,
                    "stops": 0,
                    "mile": 0,
                    "duration": "01:00:00",
                    "ground_time": "00:00:00",
                    "accumulated_duration": "00:00:00",
                    "stop_point": null,
                    "stop_point_arrival_time": "0001-01-01T00:00:00",
                    "stop_point_departure_time": "0001-01-01T00:00:00",
                    "included_baggage": "0 Kg",
                    "cabin_baggage": "Included",
                    "cabin_class": null,
                    "additional_baggage": null,
                    "airline_details": {
                        "airline_code": null,
                        "flight_number": null,
                        "craft": null,
                        "airline_name": null,
                        "operating_carrier": null,
                        "alliance_info": null
                    },
                    "airline_name": "Etihad Airways",
                    "departure_datetime": null,
                    "departure_date": null,
                    "arrival_datetime": null,
                    "arrival_date": null,
                    "layover_text": null,
                    "in_flight_services": null,
                    "fare_family_class": ""
                },
                {
                    "segment_id": 90179,
                    "seats_available": 0,
                    "alliance_info": null,
                    "flight_info_index": null,
                    "operating_carrier": "EY",
                    "segment_indicator": 1,
                    "airline": "EY",
                    "origin": {
                        "airport_code": "AUH",
                        "airport_name": "Abu Dhabi Int'l",
                        "city_code": "AUH",
                        "city_name": "Abu Dhabi",
                        "country_code": "AE",
                        "country_name": null,
                        "terminal": "A"
                    },
                    "destination": {
                        "airport_code": "COK",
                        "airport_name": "Kochi",
                        "city_code": "COK",
                        "city_name": "Cochin",
                        "country_code": "IN",
                        "country_name": null,
                        "terminal": "3"
                    },
                    "flight_number": "332",
                    "departure_time": "2025-07-10T09:30:00",
                    "arrival_time": "2025-07-10T15:05:00",
                    "booking_class": "Q",
                    "availability": null,
                    "flight_status": 0,
                    "status": "HK",
                    "meal_type": null,
                    "eticket_eligible": true,
                    "airline_pnr": "VORK8F",
                    "craft": "32A",
                    "stopover": false,
                    "stops": 0,
                    "mile": 0,
                    "duration": "04:05:00",
                    "ground_time": "00:00:00",
                    "accumulated_duration": "08:25:00",
                    "stop_point": null,
                    "stop_point_arrival_time": "0001-01-01T00:00:00",
                    "stop_point_departure_time": "0001-01-01T00:00:00",
                    "included_baggage": "0 Kg",
                    "cabin_baggage": "Included",
                    "cabin_class": null,
                    "additional_baggage": null,
                    "airline_details": {
                        "airline_code": null,
                        "flight_number": null,
                        "craft": null,
                        "airline_name": null,
                        "operating_carrier": null,
                        "alliance_info": null
                    },
                    "airline_name": "Etihad Airways",
                    "departure_datetime": null,
                    "departure_date": null,
                    "arrival_datetime": null,
                    "arrival_date": null,
                    "layover_text": null,
                    "in_flight_services": null,
                    "fare_family_class": ""
                },
                {
                    "segment_id": 90180,
                    "seats_available": 0,
                    "alliance_info": null,
                    "flight_info_index": null,
                    "operating_carrier": "EY",
                    "segment_indicator": 2,
                    "airline": "EY",
                    "origin": {
                        "airport_code": "COK",
                        "airport_name": "Kochi",
                        "city_code": "COK",
                        "city_name": "Cochin",
                        "country_code": "IN",
                        "country_name": null,
                        "terminal": "3"
                    },
                    "destination": {
                        "airport_code": "AUH",
                        "airport_name": "Abu Dhabi Int'l",
                        "city_code": "AUH",
                        "city_name": "Abu Dhabi",
                        "country_code": "AE",
                        "country_name": null,
                        "terminal": "A"
                    },
                    "flight_number": "337",
                    "departure_time": "2025-07-15T04:30:00",
                    "arrival_time": "2025-07-15T07:00:00",
                    "booking_class": "Q",
                    "availability": null,
                    "flight_status": 0,
                    "status": "HK",
                    "meal_type": null,
                    "eticket_eligible": true,
                    "airline_pnr": "VORK8F",
                    "craft": "32A",
                    "stopover": false,
                    "stops": 0,
                    "mile": 0,
                    "duration": "04:00:00",
                    "ground_time": "00:00:00",
                    "accumulated_duration": "00:00:00",
                    "stop_point": null,
                    "stop_point_arrival_time": "0001-01-01T00:00:00",
                    "stop_point_departure_time": "0001-01-01T00:00:00",
                    "included_baggage": "0 Kg",
                    "cabin_baggage": "Included",
                    "cabin_class": null,
                    "additional_baggage": null,
                    "airline_details": {
                        "airline_code": null,
                        "flight_number": null,
                        "craft": null,
                        "airline_name": null,
                        "operating_carrier": null,
                        "alliance_info": null
                    },
                    "airline_name": "Etihad Airways",
                    "departure_datetime": null,
                    "departure_date": null,
                    "arrival_datetime": null,
                    "arrival_date": null,
                    "layover_text": null,
                    "in_flight_services": null,
                    "fare_family_class": ""
                },
                {
                    "segment_id": 90181,
                    "seats_available": 0,
                    "alliance_info": null,
                    "flight_info_index": null,
                    "operating_carrier": "EY",
                    "segment_indicator": 2,
                    "airline": "EY",
                    "origin": {
                        "airport_code": "AUH",
                        "airport_name": "Abu Dhabi Int'l",
                        "city_code": "AUH",
                        "city_name": "Abu Dhabi",
                        "country_code": "AE",
                        "country_name": null,
                        "terminal": "A"
                    },
                    "destination": {
                        "airport_code": "DOH",
                        "airport_name": "Doha",
                        "city_code": "DOH",
                        "city_name": "Doha",
                        "country_code": "QA",
                        "country_name": null,
                        "terminal": null
                    },
                    "flight_number": "667",
                    "departure_time": "2025-07-15T16:40:00",
                    "arrival_time": "2025-07-15T16:45:00",
                    "booking_class": "Q",
                    "availability": null,
                    "flight_status": 0,
                    "status": "HK",
                    "meal_type": null,
                    "eticket_eligible": true,
                    "airline_pnr": "VORK8F",
                    "craft": "320",
                    "stopover": false,
                    "stops": 0,
                    "mile": 0,
                    "duration": "01:05:00",
                    "ground_time": "00:00:00",
                    "accumulated_duration": "14:45:00",
                    "stop_point": null,
                    "stop_point_arrival_time": "0001-01-01T00:00:00",
                    "stop_point_departure_time": "0001-01-01T00:00:00",
                    "included_baggage": "0 Kg",
                    "cabin_baggage": "Included",
                    "cabin_class": null,
                    "additional_baggage": null,
                    "airline_details": {
                        "airline_code": null,
                        "flight_number": null,
                        "craft": null,
                        "airline_name": null,
                        "operating_carrier": null,
                        "alliance_info": null
                    },
                    "airline_name": "Etihad Airways",
                    "departure_datetime": null,
                    "departure_date": null,
                    "arrival_datetime": null,
                    "arrival_date": null,
                    "layover_text": null,
                    "in_flight_services": null,
                    "fare_family_class": ""
                }
            ],
            "passengers": [
                {
                    "passport_issue_country_code": "AE",
                    "passport_issue_date": "2014-06-17T00:00:00",
                    "pax_id": 73776,
                    "title": "Mr",
                    "first_name": "Johnny",
                    "last_name": "Doe",
                    "mobile": "971-9876543212",
                    "mobile_country_code": "971",
                    "mobile_2": "",
                    "mobile_country_code_2": "",
                    "is_lead_pax": true,
                    "date_of_birth": "1995-05-31T00:00:00",
                    "passenger_type": "AD",
                    "passenger_id_type": 1,
                    "passenger_id_no": "J1234567",
                    "passenger_id_expiry": "2034-05-31T00:00:00",
                    "passenger_id_issue_date": "2014-06-17T00:00:00",
                    "passport_no": "J1234567",
                    "nationality": {
                        "country_code": "AE",
                        "country_name": null
                    },
                    "country": {
                        "country_code": "AE",
                        "country_name": "UAE"
                    },
                    "city": {
                        "country_code": "AE",
                        "city_code": "DXB",
                        "city_name": "Dubai"
                    },
                    "address_line": {},
                    "address_line_2": {},
                    "gender": "M",
                    "email": "info2@gotchya.ai",
                    "meal": {
                        "code": null,
                        "description": null
                    },
                    "seat": {
                        "code": null,
                        "description": null
                    },
                    "fare": {
                        "total_fare": 612.7079,
                        "fare_type": "RP",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 0.0,
                        "base_fare": 499.5717,
                        "tax": 113.1362,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_be": null,
                    "ff_airline": null,
                    "ff_number": null,
                    "passport_expiry": "2034-05-31T00:00:00",
                    "pax_baggage": [],
                    "pax_meal": [],
                    "zip_code": null,
                    "pax_seat": null,
                    "ticket": {
                        "ticket_number": "5904355558",
                        "remarks": "",
                        "validating_airline": "607",
                        "issue_date": "2025-03-10T17:28:48.583",
                        "status": "OK",
                        "title": null,
                        "ptc_detail": [],
                        "supplier_id": 0
                    },
                    "turkey_number": null,
                    "id_detail_code": "P",
                    "id_details": [
                        {}
                    ]
                },
                {
                    "passport_issue_country_code": "AE",
                    "passport_issue_date": "2025-01-09T00:00:00",
                    "pax_id": 73777,
                    "title": "Mstr",
                    "first_name": "JohnnyInfant",
                    "last_name": "Doe",
                    "mobile": "971-9876543212",
                    "mobile_country_code": "971",
                    "mobile_2": "",
                    "mobile_country_code_2": "",
                    "is_lead_pax": true,
                    "date_of_birth": "2024-12-31T00:00:00",
                    "passenger_type": "IN",
                    "passenger_id_type": 1,
                    "passenger_id_no": "J1234568",
                    "passenger_id_expiry": "2034-05-31T00:00:00",
                    "passenger_id_issue_date": "2025-01-09T00:00:00",
                    "passport_no": "J1234568",
                    "nationality": {
                        "country_code": "AE",
                        "country_name": null
                    },
                    "country": {
                        "country_code": "AE",
                        "country_name": "UAE"
                    },
                    "city": {
                        "country_code": "AE",
                        "city_code": "DXB",
                        "city_name": "Dubai"
                    },
                    "address_line": {},
                    "address_line_2": {},
                    "gender": "M",
                    "email": "info2@gotchya.ai",
                    "meal": {
                        "code": null,
                        "description": null
                    },
                    "seat": {
                        "code": null,
                        "description": null
                    },
                    "fare": {
                        "total_fare": 190.0326,
                        "fare_type": "RP",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 0.0,
                        "base_fare": 76.8964,
                        "tax": 113.1362,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_be": null,
                    "ff_airline": null,
                    "ff_number": null,
                    "passport_expiry": "2034-05-31T00:00:00",
                    "pax_baggage": [],
                    "pax_meal": [],
                    "zip_code": null,
                    "pax_seat": null,
                    "ticket": {
                        "ticket_number": "5904355560",
                        "remarks": "",
                        "validating_airline": "607",
                        "issue_date": "2025-03-10T17:28:48.583",
                        "status": "OK",
                        "title": null,
                        "ptc_detail": [],
                        "supplier_id": 0
                    },
                    "turkey_number": null,
                    "id_detail_code": "P",
                    "id_details": [
                        {}
                    ]
                },
                {
                    "passport_issue_country_code": "AE",
                    "passport_issue_date": "2021-06-17T00:00:00",
                    "pax_id": 73778,
                    "title": "Mstr",
                    "first_name": "JohnnyChild",
                    "last_name": "Doe",
                    "mobile": "971-9876543212",
                    "mobile_country_code": "971",
                    "mobile_2": "",
                    "mobile_country_code_2": "",
                    "is_lead_pax": true,
                    "date_of_birth": "2020-05-31T00:00:00",
                    "passenger_type": "CH",
                    "passenger_id_type": 1,
                    "passenger_id_no": "J1234569",
                    "passenger_id_expiry": "2034-05-31T00:00:00",
                    "passenger_id_issue_date": "2021-06-17T00:00:00",
                    "passport_no": "J1234569",
                    "nationality": {
                        "country_code": "AE",
                        "country_name": null
                    },
                    "country": {
                        "country_code": "AE",
                        "country_name": "UAE"
                    },
                    "city": {
                        "country_code": "AE",
                        "city_code": "DXB",
                        "city_name": "Dubai"
                    },
                    "address_line": {},
                    "address_line_2": {},
                    "gender": "M",
                    "email": "info2@gotchya.ai",
                    "meal": {
                        "code": null,
                        "description": null
                    },
                    "seat": {
                        "code": null,
                        "description": null
                    },
                    "fare": {
                        "total_fare": 377.3392,
                        "fare_type": "RP",
                        "agent_markup": 0.0,
                        "other_charges": 0.0,
                        "credit_card_charge": 0.0,
                        "agent_preferred_currency": "USD",
                        "service_fee": 0.0,
                        "base_fare": 377.3392,
                        "tax": 0.0,
                        "penalty_amount": 0.0,
                        "vat_amount": 0.0,
                        "vat_percentage": 0.0
                    },
                    "fare_be": null,
                    "ff_airline": null,
                    "ff_number": null,
                    "passport_expiry": "2034-05-31T00:00:00",
                    "pax_baggage": [],
                    "pax_meal": [],
                    "zip_code": null,
                    "pax_seat": null,
                    "ticket": {
                        "ticket_number": "5904355559",
                        "remarks": "",
                        "validating_airline": "607",
                        "issue_date": "2025-03-10T17:28:48.583",
                        "status": "OK",
                        "title": null,
                        "ptc_detail": [],
                        "supplier_id": 0
                    },
                    "turkey_number": null,
                    "id_detail_code": "P",
                    "id_details": [
                        {}
                    ]
                }
            ],
            "fare_rules": [
                {
                    "origin": "AUH",
                    "destination": "COK",
                    "airline": "EY",
                    "fare_restriction": "Y",
                    "fare_basis_code": "QNN05H7R",
                    "fare_family_code": null,
                    "fare_rule_detail": "Please refer above.",
                    "fare_rule_index": null,
                    "departure_date": "2025-07-10T04:10:00",
                    "flight_number": null,
                    "free_text_fare_rule_detail": null
                },
                {
                    "origin": "AUH",
                    "destination": "DOH",
                    "airline": "EY",
                    "fare_restriction": "Y",
                    "fare_basis_code": "QNN05H7R",
                    "fare_family_code": null,
                    "fare_rule_detail": "Please refer above.",
                    "fare_rule_index": null,
                    "departure_date": "2025-07-10T04:10:00",
                    "flight_number": null,
                    "free_text_fare_rule_detail": null
                },
                {
                    "origin": "COK",
                    "destination": "AUH",
                    "airline": "EY",
                    "fare_restriction": "N",
                    "fare_basis_code": "QNN05H7R",
                    "fare_family_code": null,
                    "fare_rule_detail": "Please refer above.",
                    "fare_rule_index": null,
                    "departure_date": "2025-07-10T04:10:00",
                    "flight_number": null,
                    "free_text_fare_rule_detail": null
                },
                {
                    "origin": "DOH",
                    "destination": "AUH",
                    "airline": "EY",
                    "fare_restriction": "N",
                    "fare_basis_code": "QNN05H7R",
                    "fare_family_code": null,
                    "fare_rule_detail": "<b>These Are Non Refundable Fares.</b></br><table border='1'><tr><th>Sector Details</th><th>Pax Type</th><th>Duration</th><th>Amount</th></tr><tr><th rowspan='3'>DOH-COK</th><th rowspan='1'>Adult</th><td>Rest of time period</td><td>Not Allowed</td></tr><tr><th rowspan='1'>Child</th><td>Rest of time period</td><td>Not Allowed</td></tr><tr><th rowspan='1'>Infant</th><td>Rest of time period</td><td>Not Allowed</td></tr></table><br /><br /><ul><li><b>There is no Minimum Stay requirement</b><br><li><b>Maximum Stay</b><br>Fare Component <b>QNN05H7R</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Travel must be completed before <b>No restriction</b></li><li>Travel must commence before <b>10JUL26  0000 from COK</b></li></ul></li><fieldset><legend><b><b>Adult</b><br></b></legend><ul><li><b>Revalidation/Reissue</b><br>Fare Component <b>QNN05H7R</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7R</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Revalidation before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li>Reissue before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><li><b>Refund</b><br>Fare Component <b>QNN05H7R</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7R</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Refund before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><br><b>* Revalidation is a modification of the original ticket without any reissue of a new ticket.</b><br><b>* For Reissue, Penalty fees are in addition to any difference in fare.</b><br><b>* For Refund, certain Taxes are non-refundable.</b></ul></fieldset></ul><ul><fieldset><legend><b><b>Child</b><br></b></legend><ul><li><b>Revalidation/Reissue</b><br>Fare Component <b>QNN05H7RCH</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7RCH</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Revalidation before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li>Reissue before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><li><b>Refund</b><br>Fare Component <b>QNN05H7RCH</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7RCH</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Refund before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><br><b>* Revalidation is a modification of the original ticket without any reissue of a new ticket.</b><br><b>* For Reissue, Penalty fees are in addition to any difference in fare.</b><br><b>* For Refund, certain Taxes are non-refundable.</b></ul></fieldset></ul><ul><fieldset><legend><b><b>Infant</b><br></b></legend><ul><li><b>Revalidation/Reissue</b><br>Fare Component <b>QNN05H7RIN</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7RIN</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Revalidation before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li>Reissue before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Revalidation/Reissue request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><li><b>Refund</b><br>Fare Component <b>QNN05H7RIN</b>&emsp; Sector <b>DOH-COK</b> &nbsp;Fare Component <b>QNN05H7RIN</b>&emsp; Sector <b>COK-DOH</b> &nbsp;<ul><li>Refund before/after departure, including failure to show at first/subsequent flight(s) : <b>Not Allowed</b></li><li><b>Prior to Departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at first flight</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>After departure of journey</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li><li><b>Failure to show at subsequent flight(s)</b><ul><li>Refund request must be made prior to : <b>No restriction</b></li></ul></li></ul></li><br><b>* Revalidation is a modification of the original ticket without any reissue of a new ticket.</b><br><b>* For Reissue, Penalty fees are in addition to any difference in fare.</b><br><b>* For Refund, certain Taxes are non-refundable.</b></ul></fieldset></ul><br /><b>These Are Non Refundable Fares.</b><br />",
                    "fare_rule_index": null,
                    "departure_date": "2025-07-10T04:10:00",
                    "flight_number": null,
                    "free_text_fare_rule_detail": null
                }
            ],
            "pnr": "VORK8F",
            "destination": "COK",
            "last_ticket_date": "2025-07-08T22:00:00",
            "last_void_date": "2025-03-11T00:00:00",
            "origin": "DOH",
            "created_on": "2025-03-10T17:28:32.57",
            "validating_airline_code": "EY",
            "ticketed": false,
            "airline_code": null,
            "travel_date": "2025-07-10T04:10:00",
            "non_refundable": true,
            "booking_id": 58129,
            "is_lcc": false,
            "airline_remark": "",
            "is_new_booking": false,
            "is_new_booking_flow": false,
            "upsell_options_list": {
                "FareFamily": null,
                "UpsellList": []
            },
            "payment_key": null,
            "hotel_confirmation_number": null,
            "mini_fare_rules": [],
            "is_vat_applicable": false
        },
        "void_appicable": false,
        "online_refund": true
    }
}
```
