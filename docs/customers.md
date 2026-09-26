# Customers API

## List customers

`GET /customers`

Returns a paginated list of customers.

### Query parameters

| Parameter | Type | Required | Description |
|---|---|---:|---|
| `limit` | integer | No | Number of records to return. Maximum 100. |
| `cursor` | string | No | Cursor returned by the previous request. |
| `status` | string | No | Filter by `active` or `inactive`. |

### Example

```bash
curl "https://api.example.com/v1/customers?limit=20&status=active" \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

### Response

```json
{
  "data": [
    {
      "id": "cus_1001",
      "name": "Acme Manufacturing",
      "email": "orders@example.com",
      "status": "active"
    }
  ],
  "next_cursor": "eyJvZmZzZXQiOjIwfQ=="
}
```

## Get a customer

`GET /customers/{customer_id}`

Returns one customer.

### Path parameter

| Parameter | Type | Required | Description |
|---|---|---:|---|
| `customer_id` | string | Yes | Unique customer identifier. |

### Example

```bash
curl https://api.example.com/v1/customers/cus_1001 \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN"
```

## Create a customer

`POST /customers`

Creates a customer.

### Request body

```json
{
  "name": "Acme Manufacturing",
  "email": "orders@example.com"
}
```

### Successful response

Returns `201 Created` with the created customer.

## Update a customer

`PATCH /customers/{customer_id}`

Updates one or more customer fields.

## Delete a customer

`DELETE /customers/{customer_id}`

Deletes the customer if it has no active orders.
