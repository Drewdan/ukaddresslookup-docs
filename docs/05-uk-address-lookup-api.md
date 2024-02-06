# API Usage

## Authentication with the API

The API supports two methods of authentication. Below are examples demonstrating how to use each method with the Guzzle
HTTP client in PHP.

### 1. Using the `Authorization` Header

To authenticate using the `Authorization` header, you can set the header in your Guzzle request like this:

```php
<?php

require 'vendor/autoload.php';

use GuzzleHttp\Client;

$client = new Client();

$response = $client->request('GET', 'https://ukaddresslookup.co.uk/api/v1/postcode/AA011AA', [
    'headers' => [
        'Authorization' => 'Bearer YOUR_API_KEY_HERE',
    ]
]);

echo $response->getBody();
```

### 2. Using the `token` query parameter

```php
<?php

require 'vendor/autoload.php';

use GuzzleHttp\Client;

$client = new Client();

$response = $client->request('GET', 'https://ukaddresslookup.co.uk/api/v1/postcode/AA011AA', [
    'query' => [
        'token' => 'YOUR_API_KEY_HERE',
    ]
]);

echo $response->getBody();
```

Generally, it is better to use the `Authorization` header method as it is more secure. You should make sure your API key
is kept secure and not stored in any source code that is publicly accessible.

## Postcode Lookup

The postcode lookup will list all the available addresses for a given postcode. It can be accessed by making a `GET`
request to:

```http
https://ukaddresslookup.co.uk/api/v1/postcode/NP10 0AS
```

replace `AA011AA` with the postcode you want to look up.

A sample response from this endpoint would look like this:

```json
{
  "data": [
    {
      "id": "52fd3ca2-7e7a-4061-bce4-59f199804d81",
      "organisation_name": null,
      "property_name": "",
      "property_number": "1",
      "address_line_1": " Barry Walk",
      "address_line_2": null,
      "city": "Newport",
      "county": "Newport",
      "country": "United Kingdom",
      "postcode": "NP10 0AS"
    },
    {
      "id": "37e0b669-a282-4f4b-8fd8-df36874d61c7",
      "organisation_name": null,
      "property_name": "",
      "property_number": "2",
      "address_line_1": " Barry Walk",
      "address_line_2": null,
      "city": "Newport",
      "county": "Newport",
      "country": "United Kingdom",
      "postcode": "NP10 0AS"
    }
  ],
  "count": 2,
  "status": "success"
}
```

> Please note, this system is still in beta so these responses are likely to change. Please do not use these
> in a production environment.

If no results could be found for the given postcode, the response will be as follows:

```json
{
  "data": [],
  "count": 0,
  "status": "no results"
}
```

## Address Autocomplete

The address autocomplete endpoint can be used to provide a list of addresses as a user types into a form. This can be
accessed by making a `GET` request to:

```http
https://ukaddresslookup.co.uk/api/v1/autocomplete/Barry Walk, Newport
```

A sample response from this endpoint would look like:

```json
{
  "data": [
    {
      "address": "1, Barry Walk, Rogerstone, Newport, United Kingdom",
      "id": "52fd3ca2-7e7a-4061-bce4-59f199804d81",
      "link": "https://ukaddresslookup.co.uk/api/v1/address/52fd3ca2-7e7a-4061-bce4-59f199804d81"
    },
    {
      "address": "2, Barry Walk, Rogerstone, Newport, United Kingdom",
      "id": "37e0b669-a282-4f4b-8fd8-df36874d61c7",
      "link": "https://ukaddresslookup.co.uk/api/v1/address/37e0b669-a282-4f4b-8fd8-df36874d61c7"
    }
  ],
  "count": 2,
  "status": "success"
}
```

This endpoint alone will not provide you with the full address details. It will only provide you with the address
and a link to the full address details. You can use the `id` field to make a request to the address details endpoint.

If no results are found, you will receive a payload as follows:

```json
{
    "data": [],
    "count": 0,
    "status": "no results"
}
```

## Address Lookup

Each address in our database has a unique identifier. You can use this identifier to look up the full details of an
address. This can be accessed by making a `GET` request to:

```http
https://ukaddresslookup.co.uk/api/v1/address/52fd3ca2-7e7a-4061-bce4-59f199804d81
```

A sample response from this endpoint would look like:

```json
{
    "id": "52fd3ca2-7e7a-4061-bce4-59f199804d81",
    "organisation_name": null,
    "property_name": "",
    "property_number": "1",
    "address_line_1": " Barry Walk",
    "address_line_2": null,
    "city": "Newport",
    "county": "Newport",
    "country": "United Kingdom",
    "postcode": "NP10 0AS"
}
```

If the UUID does not match an address, you will receive a 404 response.
