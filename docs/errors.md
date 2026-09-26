# Errors

OrderFlow uses standard HTTP status codes and a consistent JSON error object.

## Error format

```json
{
  "error": {
    "code": "invalid_request",
    "message": "The quantity must be greater than zero.",
    "request_id": "req_123456"
  }
}
```

## Common status codes

| Status | Meaning | Typical cause |
|---|---|---|
| 400 | Bad Request | Invalid request data |
| 401 | Unauthorized | Missing or invalid token |
| 403 | Forbidden | Insufficient permission |
| 404 | Not Found | Resource does not exist |
| 409 | Conflict | Request conflicts with current state |
| 422 | Unprocessable Entity | Valid JSON but invalid business data |
| 429 | Too Many Requests | Rate limit exceeded |
| 500 | Internal Server Error | Unexpected server error |

## Troubleshooting

When contacting support, provide the `request_id` returned by the API. Do not send access tokens or other secrets.
