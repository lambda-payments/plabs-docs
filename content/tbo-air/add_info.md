## TBO Air Search API

This search API allows you to search for flights for different journey types: One-Way, Round Trip or Multi-City

### Request Details

URL: {{base_url}}/api/servicegroup/addinfo/tbo-air/

Method: POST

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "session_id": 61,
    "token": "top_secret_token",
    "contact_name": "John Doe",
    "contact_email": "johndoe@plabs.com",
    "contact_phone": "971-9876543210",
    "passengers": [
        {
            "title": "Mr",
            "is_lead_pax": true,
            "first_name": "John",
            "last_name": "Doe",
            "mobile": "971-9876543210",
            "mobile_country_code": "971",
            "date_of_birth": "1995-06-01T00:00:00",
            "type": "AD",
            "nationality": "AE",
            "city": "DXB",
            "address_line": "JLT",
            "gender": "M",
            "email": "info@gotchya.ai",
            "passport_no": "J1234567",
            "passport_issue_country_code": "AE",
            "passport_issue_date": "2014-06-18T00:00:00",
            "passport_expiry": "2034-06-01T00:00:00"
        }
    ]
}
```

---

### **Payload Description**

| **Field**       | **Type** | **Description**                                                                    |
| --------------- | -------- | ---------------------------------------------------------------------------------- |
| `session_id`    | Integer  | Unique identifier for the session.                                                 |
| `token`         | String   | Secure token used for authentication.                                              |
| `contact_name`  | String   | Name of the contact person.                                                        |
| `contact_email` | String   | Email address of the contact person.                                               |
| `contact_phone` | String   | Phone number of the contact person.                                                |
| `passengers`    | Array    | List of passengers associated with the session. ([Details Below](#passenger-data)) |

### **Passenger Data**

| **Field**                     | **Type** | **Description**                                                |
| ----------------------------- | -------- | -------------------------------------------------------------- |
| `title`                       | String   | Title of the passenger (e.g., Mr, Mrs).                        |
| `is_lead_pax`                 | Boolean  | Indicates if this passenger is the lead (main) passenger.      |
| `first_name`                  | String   | First name of the passenger.                                   |
| `last_name`                   | String   | Last name of the passenger.                                    |
| `mobile`                      | String   | Mobile phone number of the passenger.                          |
| `mobile_country_code`         | String   | Country code of the mobile number.                             |
| `date_of_birth`               | String   | Date of birth of the passenger (in ISO 8601 format).           |
| `type`                        | String   | Type of passenger (e.g., AD for Adult, CHD for Child).         |
| `nationality`                 | String   | Nationality code of the passenger (e.g., AE for UAE).          |
| `city`                        | String   | City of residence of the passenger (e.g., DXB for Dubai).      |
| `address_line`                | String   | Address line of the passenger.                                 |
| `gender`                      | String   | Gender of the passenger (e.g., M for Male, F for Female).      |
| `email`                       | String   | Email address of the passenger.                                |
| `passport_no`                 | String   | Passport number of the passenger.                              |
| `passport_issue_country_code` | String   | Country code where the passport was issued (e.g., AE for UAE). |
| `passport_issue_date`         | String   | Passport issue date (in ISO 8601 format).                      |
| `passport_expiry`             | String   | Passport expiry date (in ISO 8601 format).                     |


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
        "contact_name": "Invalid value for field.",
        "contact_phone": "This field cannot be blank",
        "contact_email": "This field cannot be blank",
        "non_field_errors": [
            "Mutiple passengers have same passport_no."
        ]
    },
    "state": "Error"
}
```

### Success Response

```json
{
    "status": true,
    "data": {
        "detail": "Info Added Successfully."
    }
}
```
