---
title: countries query | Commerce Web APIs
---

# countries query

The `countries` query returns all countries in which the entity can do business.

Use the [country](country.md) query if you want to retrieve information about a specific country.

## Syntax

`{countries {Countries}}`

## Example usage

The following query returns all countries listed for the current instance of Magento:

**Request:**

```graphql
query {
    countries {
        id
        two_letter_abbreviation
        three_letter_abbreviation
        full_name_locale
        full_name_english
        available_regions {
            id
            code
            name
        }
    }
}
```

**Response:**

In this example, the response is intentionally truncated. The `available_regions` attribute value will be null if the country does not have any regions available. Otherwise, it contains an array of the country's regions.

```json
{
  "data": {
    "countries": [
      {
        "id": "AD",
        "two_letter_abbreviation": "AD",
        "three_letter_abbreviation": "AND",
        "full_name_locale": "Andorra",
        "full_name_english": "Andorra",
        "available_regions": null
      },
      {
        "id": "AE",
        "two_letter_abbreviation": "AE",
        "three_letter_abbreviation": "ARE",
        "full_name_locale": "United Arab Emirates",
        "full_name_english": "United Arab Emirates",
        "available_regions": null
      },
      {
        "id": "AF",
        "two_letter_abbreviation": "AF",
        "three_letter_abbreviation": "AFG",
        "full_name_locale": "Afghanistan",
        "full_name_english": "Afghanistan",
        "available_regions": null
      },
      {
        "id": "AG",
        "two_letter_abbreviation": "AG",
        "three_letter_abbreviation": "ATG",
        "full_name_locale": "Antigua and Barbuda",
        "full_name_english": "Antigua and Barbuda",
        "available_regions": null
      },
      {
        "id": "AT",
        "two_letter_abbreviation": "AT",
        "three_letter_abbreviation": "AUT",
        "full_name_locale": "Austria",
        "full_name_english": "Austria",
        "available_regions": [
          {
            "id": 102,
            "code": "BL",
            "name": "Burgenland"
          },
          {
            "id": 99,
            "code": "KN",
            "name": "Kärnten"
          },
          {
            "id": 96,
            "code": "NO",
            "name": "Niederösterreich"
          },
          {
            "id": 97,
            "code": "OO",
            "name": "Oberösterreich"
          },
          {
            "id": 98,
            "code": "SB",
            "name": "Salzburg"
          },
          {
            "id": 100,
            "code": "ST",
            "name": "Steiermark"
          },
          {
            "id": 101,
            "code": "TI",
            "name": "Tirol"
          },
          {
            "id": 103,
            "code": "VB",
            "name": "Vorarlberg"
          },
          {
            "id": 95,
            "code": "WI",
            "name": "Wien"
          }
        ]
      }
    ]
  }
}
```

## Output attributes

The query returns an array of `Country` objects.

import CountryOutput from '/src/pages/_includes/graphql/country-output.md'

<CountryOutput />

## Related topics

*  [country query](country.md)
*  [currency query](currency.md)
