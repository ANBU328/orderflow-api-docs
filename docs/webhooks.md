# Webhooks

Webhooks allow an integration to receive notifications when events occur in OrderFlow.

## Supported events

| Event | Trigger |
|---|---|
| `order.created` | An order is created |
| `order.updated` | An order changes |
| `order.cancelled` | An order is cancelled |

## Example payload

```json
{
  "id": "evt_9001",
  "type": "order.created",
  "created_at": "2026-09-26T08:00:00Z",
  "data": {
    "order_id": "ord_5001"
  }
}
```

## Integration recommendations

Your webhook endpoint should:

1. Validate the signature.
2. Return a 2xx response quickly.
3. Process the event asynchronously.
4. Make processing idempotent.
5. Log failures for troubleshooting.

## Retry behavior

For this portfolio specification, failed webhook deliveries are retried using an exponential backoff strategy.
