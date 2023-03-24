# Implementation considerations

## Data structures

### Date & time
A date and time MUST be represented in its ISO 8601 format.

- A date is represented by a string with the following format: `YYYY-MM-DD`.
- A date and time is represented by a string with the following format: `<date>T<time><timezone>`, where:
    - `<date>` follows the format described above: `YYYY-MM-DD`
    - `<time>` MUST be formatted as `HH:MM:SS`
    - `<timezone>` can be formatted in two ways: `Z` if the timezone is UTC, `+hh:mm` if another timezone

Examples:
```
"2006-01-03"
"2021-06-18T13:29:26+00:00"
"2021-06-18T13:29:26Z"
```

### Currency
Currencies MUST be represented in their ISO 4217 format, by an uppercase string.

Examples:
```
"CHF"
"USD"
```

## Response codes

Successful response status codes:

- `200` -> OK
- `201` -> Created
- `202` -> Accepted (The request has been accepted for processing, but the processing has not been completed. The request might or might not be eventually acted upon, and may be disallowed when processing occurs.)
- `204` -> No content

Error response status codes:

- `400` -> bad parameters provided by the user. Failed validation, or the resource doesn't exist
- `401` -> Unauthorized. Ex: not authenticated, invalid auth
- `403` -> Forbidden. Ex: you don't have access to this resource
- `404` -> Not found. The endpoint doesn't exist. The resource doesn't exist -> use 400
- `500` -> Internal error
- `503` -> Service Unavailable
- `504` -> Gateway timeout


## Error responses

The [RFC-7807](https://www.rfc-editor.org/rfc/rfc7807) specifies the HTTP header and the body of the error response.

When an API call returns a problem, it MUST return the proper status code, together with the right content type, and the expected attributes in the body.

```
HTTP/1.1 400 Bad Request
Content-Type: application/problem+json
Content-Language: en
{
    "status": 400,
    "type": "https://company.com/probs/portfolio-risk-measure",
    "title": "Cannot Process",
    "detail": "The content you have sent is not correct",
    "errors": [
        {
            "message": "Invalid ISIN format: CH00388633501"
        }
    ]
}
```

