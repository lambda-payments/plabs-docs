# Gift Card API Documentation

### Overview

The Gift Card Pack API provides two main functionalities:

1. **Get Packages API**: Retrieve available Gift Card options.

2. **Gift Card Payment API**: Process payment for a selected Gift Card.

## 1. Get Packages API

**Request URL:**  
`{{base_url}}/api/servicegroup/getpackages/gift-card/`

**Request Method:** POST

**Service Parameters:**

<pre><code class="json">
{
    "token": "<token>"
}

</code></pre>

### Success Response
<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "priority_no": 1,
                "product_type": "MPT Top-up Cards",
                "product_name": "MPT Top-up Cards - 1,000 Kyats",
                "currency": "MMK",
                "amount": 1000.0,
                "product_code": "200",
                "commission_percent": 0.1
            },
            {
                "priority_no": 2,
                "product_type": "App Store & iTunes (US)",
                "product_name": "App Store & iTunes (US) - 10 Credits",
                "currency": "MMK",
                "amount": 45000.0,
                "product_code": "320",
                "commission_percent": 0.1
            },
            {
                "priority_no": 3,
                "product_type": "Google Play Gift Cards (US)",
                "product_name": "Google Play Gift Cards (US) - 45 Credits",
                "currency": "MMK",
                "amount": 207000.0,
                "product_code": "2984",
                "commission_percent": 0.1
            }
        ]
    }
}
</code></pre>

### Success Response:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Your Pin number is '638761511308920854'",
    "serial": "638761511308920853",
    "pin": "638761511308920854",
    "credits_consumed": 1000.0,
    "credits_available": 56704.2,
    "id": 143
}
</code></pre>

### Error Response

<pre><code class="json">
{
    "status": false,
    "error_code": "001",
    "message": "The parameters sent are not correct.",
    "error": "invalid_parameters",
    "details": {
        "product_code": "Invalid Product Code"
    },
    "error_data": {
        "product_code": "Invalid Product Code"
    },
    "state": "Error"
}

</code></pre>