# Authentication

OrderFlow uses bearer tokens to authenticate API requests.

## Authorization header

Include the access token in every authenticated request:

```http
Authorization: Bearer YOUR_ACCESS_TOKEN
```

### Example

```bash
curl https://api.example.com/v1/customers \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

## Security guidance

Never:

- Put access tokens in source control.
- Include tokens in screenshots.
- Send tokens through email or chat.
- Store production credentials in client-side code.

Use environment variables or a secure secrets manager.

## Authentication errors

| Status | Meaning |
|---|---|
| 401 | Missing or invalid authentication |
| 403 | Authentication succeeded, but the caller lacks permission |
