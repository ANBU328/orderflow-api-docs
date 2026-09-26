# ERP Integration Guide

This guide demonstrates how an ERP system could exchange order information with OrderFlow.

## Integration architecture

```text
ERP
 │
 │ HTTPS / JSON
 ▼
OrderFlow API
 │
 ├── Customers
 ├── Products
 └── Orders
      │
      ▼
   Webhooks
      │
      ▼
     ERP
```

## Recommended flow

1. Synchronize customer master data.
2. Synchronize products.
3. Create orders in OrderFlow.
4. Store the OrderFlow order ID in the ERP.
5. Subscribe to order webhooks.
6. Update ERP order status when events arrive.
7. Retry failed requests using exponential backoff.

## Idempotency

Integrations should use an idempotency key when creating resources where supported.

Example:

```http
Idempotency-Key: erp-order-12345
```

This prevents accidental duplicate transactions when an ERP retries a request after a network timeout.

## Operational considerations

Document:

- Authentication and secret management
- Field mappings
- Error handling
- Retry behavior
- Rate limits
- Logging
- Monitoring
- Data ownership
- Reconciliation procedures
