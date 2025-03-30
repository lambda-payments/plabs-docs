## TBO Air Issue Ticket API

This API allows you to issue ticket, and this is responsible for the amount deduction.

### Request Details

URL: `{{base_url}}/api/servicegroup/issue/tbo-air/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "session_id": 0,
    "token": "top_secret_token"
}
```

---

### **Payload Description**

| **Field**    | **Type** | **Description**                       |
| ------------ | -------- | ------------------------------------- |
| `session_id` | Integer  | Unique identifier for the session.    |
| `token`      | String   | Secure token used for authentication. |

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
        "pnr": "JCRMP3",
        "change_in_itinerary": null,
        "is_baggage_changed_at_ticket": false
    },
    "credits_available": 99988060.99999988,
    "credits_consumed": 596.9,
    "commission": 0,
    "state": "Success",
    "message": "Issue flight success"
}
```
