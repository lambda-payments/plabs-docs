# **BULK SERVICE STATUS LOOKUP API**

**URL:** `{{base_url}}/api/service/bulk/status/`  

**METHOD:** GET  

**Service Params:**
<pre><code class="json">
{
    "token": "<provided token>",
    "references": "PP123,PP234",  # Comma separated references
    "reference_length": 2  # Number of references sent
}
</code></pre>

**Response:**
<pre><code class="json">
{
    "status": true,
    "message": "Success",
    "detail": [
        {
            "status": true,
            "state": "Success",
            "details": "Payment made successfully. Account will be activated in few minutes",
            "reference": "PP123",
            "response_id": 101,
            "amount": 10000
        },
        {
            "status": true,
            "state": "Error",
            "details": "Invalid reference obtained for account",
            "reference": "PP234",
            "response_id": 0,
            "amount": 0
        }
    ]
}
</code></pre>

**NOTE:** Always check the `state` to make success/failure decisions. The list of possible states is listed Previous Page.
