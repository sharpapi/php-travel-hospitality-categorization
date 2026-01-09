![SharpAPI GitHub cover](https://sharpapi.com/sharpapi-github-laravel-bg.jpg "SharpAPI PHP Client")

# Travel Hospitality Categorization API for PHP

## ✈️ Categorize hospitality products using AI - hotels, resorts with relevance scores

[![Latest Version on Packagist](https://img.shields.io/packagist/v/sharpapi/php-travel-hospitality-categorization.svg?style=flat-square)](https://packagist.org/packages/sharpapi/php-travel-hospitality-categorization)
[![Total Downloads](https://img.shields.io/packagist/dt/sharpapi/php-travel-hospitality-categorization.svg?style=flat-square)](https://packagist.org/packages/sharpapi/php-travel-hospitality-categorization)

Check the full documentation on the [Travel Hospitality Categorization API for PHP API](https://sharpapi.com/en/catalog/ai/travel-tourism-hospitality/hospitality-product-categorization) page.

---

## Quick Links

| Resource | Link |
|----------|------|
| **Main API Documentation** | [Authorization, Webhooks, Polling & More](https://documenter.getpostman.com/view/31106842/2s9Ye8faUp) |
| **Postman Documentation** | [View Docs](https://documenter.getpostman.com/view/31106842/2sBXVeGsVg) |
| **Product Details** | [SharpAPI.com](https://sharpapi.com/en/catalog/ai/travel-tourism-hospitality/hospitality-product-categorization) |
| **SDK Libraries** | [GitHub - SharpAPI SDKs](https://github.com/sharpapi) |

---

## Requirements

- PHP >= 8.0

---

## Installation

### Step 1. Install the package via Composer:

```bash
composer require sharpapi/php-travel-hospitality-categorization
```

### Step 2. Visit [SharpAPI](https://sharpapi.com/) to get your API key.

---
## Laravel Integration

Building a Laravel application? Check the Laravel package version for better integration.

---

## What it does

Categorize hospitality products using AI - hotels, resorts with relevance scores

---

## Usage
```php
<?php

require __DIR__ . '/vendor/autoload.php';

use SharpAPI\TravelHospitality\HospitalityCategorizationClient;
use GuzzleHttp\Exception\GuzzleException;

$apiKey = 'your_api_key_here';
$client = new HospitalityCategorizationClient(apiKey: $apiKey);

try {
    $statusUrl = $client->categorizeHospitalityProduct(
        productName: 'Luxury Beach Resort',
        city: 'Miami',
        country: 'United States',
        language: 'English'
    );

    // Optional: Configure polling
    $client->setApiJobStatusPollingInterval(10);
    $client->setApiJobStatusPollingWait(180);

    // Fetch results (polls automatically)
    $result = $client->fetchResults($statusUrl);
    $resultData = $result->getResultJson();

    echo $resultData;
} catch (GuzzleException $e) {
    echo "API error: " . $e->getMessage();
}
```

---

## Example Response
```json
{
  "data": {
    "type": "api_job_result",
    "id": "job-id-here",
    "attributes": {
      "status": "success",
      "type": "content_processing",
      "result": {
        "content": "Processed result content here..."
      }
    }
  }
}
```
---

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

---

## Credits

- [A2Z WEB LTD](https://github.com/a2zwebltd)
- [Dawid Makowski](https://github.com/makowskid)
- Boost your [PHP AI](https://sharpapi.com/) capabilities!

---

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

---

## Social Media

🚀 For the latest news, tutorials, and case studies, don't forget to follow us on:
- [SharpAPI X (formerly Twitter)](https://x.com/SharpAPI)
- [SharpAPI YouTube](https://www.youtube.com/@SharpAPI)
- [SharpAPI Vimeo](https://vimeo.com/SharpAPI)
- [SharpAPI LinkedIn](https://www.linkedin.com/products/a2z-web-ltd-sharpapicom-automate-with-aipowered-api/)
- [SharpAPI Facebook](https://www.facebook.com/profile.php?id=61554115896974)
