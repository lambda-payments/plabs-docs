# Atom Data Pack API Documentation

### Overview

The Atom Data Pack API provides two main functionalities:

1. **Get Packages API**: Retrieve available Atom data pack options.

2. **Atom Data Pack Payment API**: Process payment for a selected Atom data pack.

## 1. Get Packages API

**Request URL:**  
`{{base_url}}/api/servicegroup/getpackages/atom-product/`

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
                "product_name": "ATOM Maximus 727 MB + TikTok 3D",
                "amount": 1994.0,
                "short_detail": "ATOM Maximus 727 MB + TikTok 3D",
                "product_code": "ATOM_Maximus_727_MB_TT",
                "description": "ATOM Maximus 727 MB + TikTok 3D",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 8
            },
            {
                "priority_no": 1,
                "product_name": "ATOM Maximus 727 MB + YouTube 3D",
                "amount": 1995.0,
                "short_detail": "ATOM Maximus 727 MB + YouTube 3D",
                "product_code": "ATOM_Maximus_727_MB_YT",
                "description": "ATOM Maximus 727 MB + YouTube 3D",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 7
            },
            {
                "priority_no": 1,
                "product_name": "ATOM Maximus 1818 MB + Telegram 7D",
                "amount": 4995.0,
                "short_detail": "ATOM Maximus 1818 MB + Telegram 7D",
                "product_code": "ATOM_Maximus_1818_MB_TG",
                "description": "ATOM Maximus 1818 MB + Telegram 7D",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 6
            },
            {
                "priority_no": 1,
                "product_name": "ATOM Maximus 1818 MB + TikTok 7D",
                "amount": 4996.0,
                "short_detail": "ATOM Maximus 1818 MB + TikTok 7D",
                "product_code": "ATOM_Maximus_1818_MB_TT",
                "description": "ATOM Maximus 1818 MB + TikTok 7D",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 5
            },
            {
                "priority_no": 1,
                "product_name": "ATOM Maximus 1818 MB + YouTube 7D",
                "amount": 4997.0,
                "short_detail": "ATOM Maximus 1818 MB + YouTube 7D",
                "product_code": "ATOM_Maximus_1818_MB_YT",
                "description": "ATOM Maximus 1818 MB + YouTube 7D",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 4
            },
            {
                "priority_no": 1,
                "product_name": "Shal Suboo 4,350 MB",
                "amount": 9999.0,
                "short_detail": "Shal Suboo 4,350 MB",
                "product_code": "Shal_Suboo_4350MB",
                "description": "Shal Suboo 4,350 MB",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 3
            },
            {
                "priority_no": 1,
                "product_name": "Shal Suboo 2,600MB",
                "amount": 5999.0,
                "short_detail": "Shal Suboo 2,600MB",
                "product_code": "Shal_Suboo_2600MB",
                "description": "Shal Suboo 2,600MB",
                "prodcut_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 2
            },
            {
                "priority_no": 2,
                "product_name": "ATOM Maximus 727 MB + Telegram 3D",
                "amount": 1993.0,
                "short_detail": "ATOM Maximus 727 MB + Telegram 3D",
                "product_code": "ATOM_Maximus_727_MB_TG",
                "description": "ATOM Maximus 727 MB + Telegram 3D",
                "prodcut_type": "Voice Pack",
                "validity": "3 Days",
                "package_priority": 9
            },
            {
                "priority_no": 2,
                "product_name": "Talkie Suboo 397 Mins",
                "amount": 4998.0,
                "short_detail": "Talkie Suboo 397 Mins",
                "product_code": "Talkie_Suboo_397_Mins",
                "description": "Talkie Suboo 397 Mins",
                "prodcut_type": "Voice Pack",
                "validity": "3 Days",
                "package_priority": 1
            }
        ]
    }
}
</code></pre>

## 2. Payment 

### Request URL:
  ```{{base_url}}/api/use/atom-product/```

***Request Method***: POST

### Service Parameters:
<pre><code class="json">
{
    "token": "<token>",
    "amount": 1994,
    "number": "9791001370",
    "reference": "PP123",
    "product_code": "ATOM_Maximus_727_MB_TT"
}
</code></pre>

### Success Response:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction successful",
    "id": 1234
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