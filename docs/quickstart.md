# Quickstart

This guide shows the basic flow for creating a customer and then creating an order.

## Prerequisites

You need:

- An OrderFlow account
- An API access token
- cURL or another HTTP client

## 1. Create a customer

```bash
curl -X POST https://api.example.com/v1/customers \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Acme Manufacturing",
    "email": "orders@example.com"
  }'
```

Example response:

```json
{
  "id": "cus_1001",
  "name": "Acme Manufacturing",
  "email": "orders@example.com",
  "status": "active"
}
```

## 2. Create an order

```bash
curl -X POST https://api.example.com/v1/orders \
  -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "customer_id": "cus_1001",
    "currency": "USD",
    "items": [
      {
        "product_id": "prod_2001",
        "quantity": 5
      }
    ]
  }'
```

The response contains the new order ID and current order status.

## What to learn

This example demonstrates a common API documentation pattern:

**Prerequisites → request → response → next step**
