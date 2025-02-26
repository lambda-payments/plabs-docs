# GIG General Insurance API

The GIG General Insurance API allows users to perform transactions related to the GIG General Insurance service.

## Type: Single Step API

### Endpoint

- **URL:** `{{base_url}}/api/use/ggi-general-insurance`
- **Method:** `POST`

### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "token": "token",
    "policy_id": "<policy_id>",
    "mobile_number": "9791001370",
    "amount": 100, // Minimum Amount 100
    "reference": "pp123"
}
</code></pre>

### Response

Upon successful request, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "id": 123,
    "credits_available": 11000.0,
    "message": "Your operation is in queue.",
    "state": "Queued",
    "credits_consumed": 100.0
}
</code></pre>