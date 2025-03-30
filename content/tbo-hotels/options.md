## TBO Hotels Master Data API

This API provides master data for TBO Hotels.

### Request Details

URL: `{{base_url}}/api/servicegroup/options/tbo-hotels/<option_type>`

Option Types: One of `['hotel-code-list', 'hotel-codes', 'hotel-city', 'hotel-country']`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

---

### **Example Payload**

```json
{
    "token": "top_secret_token"
}
```

---

### **Payload Description**

| **Field**    | **Type** | **Description**                       |
| ------------ | -------- | ------------------------------------- |
| `token`      | String   | Secure token used for authentication. |

---

### Error Response:
```json
// When hit request with `/api/servicegroup/options/tbo-air/error`
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Invalid choice for option `error`. Must be one of ['hotel-code-list', 'hotel-codes', 'hotel-city', 'hotel-country']",
    "error_data": {},
    "state": "Error"
}
```

### Example Response

```json
// hotel-country
{
    "status": true,
    "data": [
        {
            "name": "Albania",
            "iso_code": "AL"
        },
        {
            "name": "Andorra",
            "iso_code": "AD"
        },
    ]
}
```