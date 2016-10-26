xBased API
==========
The xBased API is an internal API used to scale some technical endpoints.

**Version:** v1

### /about
---
##### ***GET***
**Description:** The 'about' endoint is basically the endpoint that will always work. If it doesn't,
then it means the whole xBased API is broken.
It defines the /about endpoint, returning a basic, simple object for debug purposes.


**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful response |

### /v1/locale
---
##### ***GET***
**Description:** Private endpoint resolving localisation information based on the given request parameters. The endpoint will return the country based on GeoIP resolution, the language based on on the Accept-Languages header as well as the associated LocaleV2 string.


**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful response |

### /v1/rules/
---
##### ***GET***
**Description:** Returns a set of rules depending on the given namespace (defaults to all rules). The returned data is a JSON object with the "data" key set to a mapping from rule ID to rule object.

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| user_id | formData | The xID of the user to consider when matching the rules users | No | string |
| ts | formData | Integer between 0 and 1,000,000, the traffic segment to consider when matching the rules traffic ranges | No | integer |
| country_code | formData | the ISO-3166-1 alpha-2 country code  to consider when matching the rules countries. If not set, the country code will be inferred from the GeoIP match of the client IP (or Forwarded/X-Forwarded-For headers) headers. | No | string |
| ns | formData | limit the result set to rules part of a namespace | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful response |

### /v1/rules/{id}
---
##### ***GET***
**Description:** Returns a JSON object representation of the rule with the given rule_id.

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | A rule ID (example mira.ads.provider.mopub) | Yes | string |
| user_id | formData | The xID of the user to consider when matching the rules users | No | string |
| ts | formData | Integer between 0 and 1,000,000, the traffic segment to consider when matching the rules traffic ranges | No | integer |
| country_code | formData | the ISO-3166-1 alpha-2 country code  to consider when matching the rules countries. If not set, the country code will be inferred from the GeoIP match of the client IP (or Forwarded/X-Forwarded-For headers) headers. | No | string |
| ns | formData | limit the result set to rules part of a namespace | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful response |
