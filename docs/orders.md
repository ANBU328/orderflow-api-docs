# Orders API

## Create an order

`POST /orders`

Creates a new sales order.

### Request

```json
{
  "customer_id": "cus_1001",
  "currency": "USD",
  "items": [
    {
      "product_id": "prod_2001",
      "quantity": 5
    }
  ]
}
```

### Response

```json
{
  "id": "ord_5001",
  "customer_id": "cus_1001",
  "status": "pending",
  "currency": "USD",
  "total": 1250.00
}
```

## Get an order

`GET /orders/{order_id}`

Returns the current state of an order.

## Update an order

`PATCH /orders/{order_id}`

Use this operation to update fields that are allowed by the order lifecycle.

## Cancel an order

`POST /orders/{order_id}/cancel`

Cancels an order that has not entered fulfillment.

### Important

An order that has already entered fulfillment cannot be cancelled through this endpoint.

## Order lifecycle

```text
pending → confirmed → fulfilled
             ↓
          cancelled
```
