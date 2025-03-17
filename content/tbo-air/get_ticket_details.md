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

```
