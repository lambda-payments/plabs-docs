# Atom API

## Overview

The Atom API endpoint allows you to perform a single-step transaction. This API requires a POST request and provides information about the success or failure of the transaction.

**URL:** [{{base_url}}/api/use/atom/]
**Type:** Single Step API  
**Method:** POST

## Request Parameters

The following parameters are required in the POST request:

- **number:** mobile number
- **token:** Authentication token
- **reference:** Unique reference for the transaction
- **amount:** Amount in Kyats

### Valid Amounts

- From 100 to 10000

## Request Example



<pre><code class="json">
{
    "token": "Token Provided",
    "reference": "unique-reference",
    "amount": "amount",
    "number": "number(eg:9791001370)"
}
</code></pre>