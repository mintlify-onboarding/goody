---
stoplight-id: dd34d0dd0aba2
---

# Webhooks

Webhook | Description
---------|----
 **[order_batch.created](order_batch.created.md)** | When an order batch is newly created. The order batch could still be in process of sending, or scheduled for the future.
 **[order_batch.completed](order_batch.completed.md)** | When an order batch is fully processed and all orders have been created.
 **[order.created](order.created.md)** | When an order is created and is ready to be opened.
**[order.gift_opened](order.gift_opened.md)** | When a gift is opened by the recipient.
**[order.gift_accepted](order.gift_accepted.md)** | When a gift has been accepted by the recipient.
**[order.thank_you_note_added](order.thank_you_note_added.md)** | When a recipient adds a thank you note to a order after accepting it.
**[order.shipped](order.shipped.md)** | When an order starts shipping. If there are multiple shipments, this is called for the first.
**[order.delivered](order.delivered.md)** | When an order is fully delivered. If there are multiple shipments, this is called when all shipments are delivered.