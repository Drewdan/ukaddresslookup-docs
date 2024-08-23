# Rest API Documentation

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
https://ukaddresslookup.co.uk/api/v1/postcode/NP19 8GJ
```

replace `AA011AA` with the postcode you want to look up.

A sample response from this endpoint would look like this:

```json
{
    "data": [
        {
            "id": "aecff900-7f76-4f84-9646-db2644ef97ac",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "1"
            },
            "full_address": "1, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "1742d02a-f3ac-43ea-ae59-1841e1aa9e2b",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "2"
            },
            "full_address": "2, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "e06d3ee2-dbef-4416-82c5-adf7f834615f",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "3"
            },
            "full_address": "3, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "115c5236-64c4-4c28-af90-555860ed1434",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "4"
            },
            "full_address": "4, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "a0eea707-f3ce-4b2b-8571-4d6e78a045a5",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "5"
            },
            "full_address": "5, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "23af759b-0d10-4401-a6ef-97171d58f692",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "7"
            },
            "full_address": "7, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "c021171f-5f3a-4c4f-8e9f-a9526383268d",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "8"
            },
            "full_address": "8, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "1921bfe1-1f8a-4b67-b621-b5254310e109",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "9"
            },
            "full_address": "9, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "cb8bd2d5-0719-4eef-8c48-41f86a3c5daf",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "10"
            },
            "full_address": "10, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        },
        {
            "id": "c3010bed-affe-40d7-be30-d5a208f58e44",
            "property": {
                "organisation_name": null,
                "sub_property_name": "",
                "sub_property_number": null,
                "property_name": null,
                "property_number": "12"
            },
            "full_address": "12, Kensington Grove, Beechwood, Newport, Wales, NP19 8GJ",
            "address_line_1": "Kensington Grove",
            "address_line_2": "",
            "locality": "Beechwood",
            "district": null,
            "city": "Newport",
            "county": null,
            "country": "Wales",
            "postcode": "NP19 8GJ",
            "language_code": "EN"
        }
    ],
    "count": 10,
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
https://ukaddresslookup.co.uk/api/v1/autocomplete/Flat 4, Bedwellty House
```

A sample response from this endpoint would look like:

```json
{
    "data": {
        "3": {
            "address": "Flat 4, Bedwellty House, Golden Mile View, Casnewydd, Wales",
            "id": "dbe5b9f7-1413-4d3a-b5d4-11016b07bf6d",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/dbe5b9f7-1413-4d3a-b5d4-11016b07bf6d",
            "relevance": 10.76
        },
        "4": {
            "address": "Flat 3, Bedwellty House, Golden Mile View, Newport, Wales",
            "id": "c92286d6-6aad-44d2-b554-0ad7bbcca33a",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/c92286d6-6aad-44d2-b554-0ad7bbcca33a",
            "relevance": 10.76
        },
        "23": {
            "address": "Flat, 4, Bedwellty Road, Coed-Duon, Wales",
            "id": "55d5394d-22b3-4683-9d45-35ad52df10f6",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/55d5394d-22b3-4683-9d45-35ad52df10f6",
            "relevance": 7.47
        },
        "5": {
            "address": "Corner House, Casnewydd, Wales",
            "id": "830a863c-902a-419d-b0b5-7b1bf570c523",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/830a863c-902a-419d-b0b5-7b1bf570c523",
            "relevance": 3.27
        },
        "6": {
            "address": "Holly House, Pentrepoeth Road, The Hollies, Casnewydd, Wales",
            "id": "cf5faf79-35d4-4420-94c2-c51bb6d6c983",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/cf5faf79-35d4-4420-94c2-c51bb6d6c983",
            "relevance": 3.27
        },
        "7": {
            "address": "Gwent Constabulary, Rogerstone Police Station, Ebenezer Drive, Casnewydd, Wales",
            "id": "c1103888-95eb-4f38-96c0-2d09455aaba1",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/c1103888-95eb-4f38-96c0-2d09455aaba1",
            "relevance": 0.03
        },
        "0": {
            "address": "154A, Cefn Road, Casnewydd, Wales",
            "id": "9a19fa9b-0f4d-4e73-9075-06ca80e0f71b",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/9a19fa9b-0f4d-4e73-9075-06ca80e0f71b",
            "relevance": 0.02
        },
        "1": {
            "address": "2 Shopping Centre, Thornbury Park, Casnewydd, Wales",
            "id": "b4508fca-7f78-4d0b-942c-e7bc94fddf83",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/b4508fca-7f78-4d0b-942c-e7bc94fddf83",
            "relevance": 0.02
        },
        "2": {
            "address": "Greenfields Stores, 3-4 Greenfield Stores, Greenfield Road, Casnewydd, Wales",
            "id": "d670429f-4f73-477f-a2dc-cc4a3ca92060",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/d670429f-4f73-477f-a2dc-cc4a3ca92060",
            "relevance": 0.02
        },
        "8": {
            "address": "1, Oak Road, Casnewydd, Wales",
            "id": "12a4a686-789f-4838-8a99-bfc1b6a30c3b",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/12a4a686-789f-4838-8a99-bfc1b6a30c3b",
            "relevance": 0.02
        },
        "9": {
            "address": "1, Primrose Way, Casnewydd, Wales",
            "id": "1bbe3848-2e13-4f81-8c9c-a286318039bd",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/1bbe3848-2e13-4f81-8c9c-a286318039bd",
            "relevance": 0.02
        },
        "10": {
            "address": "1, Lyndon Way, Casnewydd, Wales",
            "id": "35707b0f-acc2-4f18-9015-a20b7c91f492",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/35707b0f-acc2-4f18-9015-a20b7c91f492",
            "relevance": 0.02
        },
        "11": {
            "address": "1, Tudor Crescent, Newport, Wales",
            "id": "63e74c1b-a7a5-4c8c-b65a-456c4d60b766",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/63e74c1b-a7a5-4c8c-b65a-456c4d60b766",
            "relevance": 0.02
        },
        "12": {
            "address": "2, Ebenezer Drive, Casnewydd, Wales",
            "id": "53b45f8f-09a2-477d-b37c-fa59ec55a04e",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/53b45f8f-09a2-477d-b37c-fa59ec55a04e",
            "relevance": 0.02
        },
        "13": {
            "address": "2, Marlow Close, Casnewydd, Wales",
            "id": "cdbd089a-6179-4c33-90a8-291b6f5b2911",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/cdbd089a-6179-4c33-90a8-291b6f5b2911",
            "relevance": 0.02
        },
        "14": {
            "address": "2, Tudor Crescent, Newport, Wales",
            "id": "218e59fe-1c74-4ad7-8835-982c54eafa17",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/218e59fe-1c74-4ad7-8835-982c54eafa17",
            "relevance": 0.02
        },
        "15": {
            "address": "2, Primrose Way, Casnewydd, Wales",
            "id": "9d1928c9-fde5-4b80-b0dd-b8e1d417da07",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/9d1928c9-fde5-4b80-b0dd-b8e1d417da07",
            "relevance": 0.02
        },
        "16": {
            "address": "2, Roberts Close, Casnewydd, Wales",
            "id": "0f41a2d0-64a1-4207-ba1c-70f7b10df152",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/0f41a2d0-64a1-4207-ba1c-70f7b10df152",
            "relevance": 0.02
        },
        "17": {
            "address": "2, Hollyhock Close, Casnewydd, Wales",
            "id": "37efa398-a526-4c77-ac78-8b988fe8db7a",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/37efa398-a526-4c77-ac78-8b988fe8db7a",
            "relevance": 0.02
        },
        "18": {
            "address": "2, Poppy Place, Casnewydd, Wales",
            "id": "3f62bc87-d84d-4549-a0aa-99858ef1476d",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/3f62bc87-d84d-4549-a0aa-99858ef1476d",
            "relevance": 0.02
        },
        "19": {
            "address": "3, Tudor Crescent, Casnewydd, Wales",
            "id": "c1ac1ae4-60b7-458b-9908-725bde563bcb",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/c1ac1ae4-60b7-458b-9908-725bde563bcb",
            "relevance": 0.02
        },
        "20": {
            "address": "3, Poppy Place, Casnewydd, Wales",
            "id": "c02734e1-9b13-4014-a9ca-704c3e501417",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/c02734e1-9b13-4014-a9ca-704c3e501417",
            "relevance": 0.02
        },
        "21": {
            "address": "3, Watkins Walk, Casnewydd, Wales",
            "id": "c9ae213d-b3ba-4d03-923b-85e3bfe16e2b",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/c9ae213d-b3ba-4d03-923b-85e3bfe16e2b",
            "relevance": 0.02
        },
        "22": {
            "address": "3, Primrose Way, Casnewydd, Wales",
            "id": "fbf3161e-ec88-4681-aae6-2b05f135be31",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/fbf3161e-ec88-4681-aae6-2b05f135be31",
            "relevance": 0.02
        },
        "24": {
            "address": "4, Tudor Crescent, Newport, Wales",
            "id": "530cafa0-129b-4fd5-a8a2-fce2cc5195f8",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/530cafa0-129b-4fd5-a8a2-fce2cc5195f8",
            "relevance": 0.02
        },
        "25": {
            "address": "4, St. Annes Close, Casnewydd, Wales",
            "id": "97712ae6-3e1c-4eb2-b485-76b2335cd5b0",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/97712ae6-3e1c-4eb2-b485-76b2335cd5b0",
            "relevance": 0.02
        },
        "26": {
            "address": "4, Hillside Crescent, Casnewydd, Wales",
            "id": "32e2ecf2-55c8-4f41-a76b-5c39224fe7e1",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/32e2ecf2-55c8-4f41-a76b-5c39224fe7e1",
            "relevance": 0.02
        },
        "27": {
            "address": "4, Royce Walk, Casnewydd, Wales",
            "id": "6636abd0-3ce5-4929-b8a9-5dadcd123930",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/6636abd0-3ce5-4929-b8a9-5dadcd123930",
            "relevance": 0.02
        },
        "28": {
            "address": "5, Poppy Place, Casnewydd, Wales",
            "id": "1879b6df-77b1-4d66-a7d9-ce2987f94ebc",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/1879b6df-77b1-4d66-a7d9-ce2987f94ebc",
            "relevance": 0.02
        },
        "29": {
            "address": "5, Mountford Close, Casnewydd, Wales",
            "id": "07158a6b-e664-4147-9e6d-de03808d03a7",
            "link": "https://ukaddresslookup.drewdan.dev/api/v1/address/07158a6b-e664-4147-9e6d-de03808d03a7",
            "relevance": 0.02
        }
    },
    "count": 30,
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
https://ukaddresslookup.co.uk/api/v1/address/dbe5b9f7-1413-4d3a-b5d4-11016b07bf6d
```

A sample response from this endpoint would look like:

```json
{
    "id": "dbe5b9f7-1413-4d3a-b5d4-11016b07bf6d",
    "property": {
        "organisation_name": null,
        "sub_property_name": "Flat 4",
        "sub_property_number": null,
        "property_name": "Bedwellty House",
        "property_number": null
    },
    "full_address": "Flat 4, Bedwellty House, Golden Mile View, Rogerstone, Casnewydd, Wales, NP20 3PA",
    "address_line_1": "Golden Mile View",
    "address_line_2": "",
    "locality": "Rogerstone",
    "district": null,
    "city": "Casnewydd",
    "county": null,
    "country": "Wales",
    "postcode": "NP20 3PA",
    "language_code": "CY"
}
```

If the UUID does not match an address, you will receive a 404 response.
