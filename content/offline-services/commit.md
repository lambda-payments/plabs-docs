# Offline Services Commit

This file documents the commit process for offline services.

- Add details about the commit workflow, requirements, and any relevant notes here.

## Offline Services Commit API

This API allows you to commit an offline service transaction.

### Request Details

URL: `{{base_url}}/api/servicegroup/commit/offline-services/`

Method: `POST`

Headers: `'Content-Type': 'application/json'`

### **Example Payload**

```json
{
    "reference_identifier": "{{$guid}}",
    "token": "{{token}}",
    "service_slug": "test-offline-service",
    "amount": 1200,
    "email": "test_email@offline.com",
    "username": "test.username",
    "voucher_number": "VHR001"
}
```

> **NOTE**: The fields except for `token`, `service_slug`, `reference_identifier` are configurable, and can be modified as per need. The provided fields are dummy fields and may change for every offline service.

---

### Payload Description

| **Key**                | **Data Type** | **Description**                                                                              |
| ---------------------- | ------------- | -------------------------------------------------------------------------------------------- |
| `reference_identifier` | String        | Unique identifier for the offline service transaction (e.g., GUID).                          |
| `token`                | String        | The authentication token for API access.                                                     |
| `service_slug`         | String        | Slug or code representing the offline service type.                                          |
| `amount`               | Number        | The transaction amount for the offline service. (Should be in same currency as the account.) |
| `email`                | String        | The email address of the user/customer.                                                      |
| `username`             | String        | The username of the user/customer.                                                           |
| `voucher_number`       | String        | Voucher number associated with the offline service transaction.                              |

---

### Responses

#### Error Response
```json
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": {
        "service_slug": "Service slug is missing."
    },
    "error_data": {},
    "state": "Error"
}
```

#### Success Response
```json
{
    "status": true,
    "state": "Processing",
    "detail": "Transaction is being processed.",
    "message": "Transaction is processing",
    "credits_consumed": 1200.0,
    "credits_available": 99580797.54338321,
    "currency": "NPR",
    "extra_data": {},
    "id": 279
}
```
