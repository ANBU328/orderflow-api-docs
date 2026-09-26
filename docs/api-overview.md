# OrderFlow API

The OrderFlow API enables business applications to manage customers, products and orders through a REST interface.

## Base URL

`https://api.example.com/v1`

The URL is illustrative only. This portfolio project does not expose a production API.

## API style

OrderFlow uses:

- HTTPS
- REST-style resources
- JSON request and response bodies
- Bearer-token authentication
- HTTP status codes
- Cursor-based pagination for collection endpoints

## Common headers

```http
Authorization: Bearer <access-token>
Content-Type: application/json
Accept: application/json
```

## Resources

| Resource | Purpose |
|---|---|
| Customers | Manage customer records |
| Products | Manage products |
| Orders | Create and manage sales orders |
| Webhooks | Receive event notifications |

## Versioning

The API version is included in the URL:

```text
/v1/customers
/v1/orders
```

Breaking changes are introduced only in a new major API version.

## Documentation conventions

Each endpoint documents:

1. HTTP method and path
2. Purpose
3. Authentication
4. Parameters
5. Request body
6. Response
7. Errors
8. Example request
9. Example response
