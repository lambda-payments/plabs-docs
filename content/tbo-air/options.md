## TBO Air Master Data API

This API provides master data for TBO Air.

### Request Details

URL: `{{base_url}}/api/servicegroup/options/tbo-air/<option_type>`

Option Types: One of `['airlines', 'cities', 'countries', 'sectors']`

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
    "details": "Invalid choice for option `error`. Must be one of ['airlines', 'cities', 'countries', 'sectors']",
    "error_data": {},
    "state": "Error"
}
```

### Example Response

```json
{
    "status": true,
    "data": [
        {
            "name": "Alaska Airlines Inc.",
            "code": "AS",
            "logo_path": "https://cdnimage.blob.core.windows.net/airline-logos/AS.png",
            "is_lcc": false
        },
        {
            "name": "Wanair",
            "code": "3W",
            "logo_path": "https://cdnimage.blob.core.windows.net/airline-logos/3W.gif",
            "is_lcc": false
        }
    ]
}
```