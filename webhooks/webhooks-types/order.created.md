---
stoplight-id: himk4itg3dvn1
---

# Event: order.created

Emitted when an order has been created and is ready to be opened and accepted (if it's a gift). An individual gift link is available (`individual_gift_link`).

## Example

```json
{
  "event_type": "order.created",
  "id": "ad097c47-bf12-45c9-8feb-0536a0012c09",
  "data": {
    "id": "10c588dd-d566-45bf-86e9-c23bd1f1587b",
    "status": "created",
    "individual_gift_link": "https://gifts.ongoody.com/gift/vWtUe8lQRJuoyYzKlYeHMkbV",
    "recipient_first_name": "Alena",
    "recipient_last_name": "Kenter",
    "recipient_email": "alena@ongoody.com",
    "card_id": "ae4cb4ce-75fc-4782-a9ab-2f30d9b7b41d",
    "message": "Thank you!",
    "thank_you_note": null,
    "view_count_recipient": 0,
    "is_swapped": false,
    "order_batch_id": "4133078a-c35f-441e-8e92-57645342b299",
    "expires_at": null,
    "cart": {
      "id": "39b04e91-6a40-468d-8ed4-f59e9059afae",
      "items": [
        {
          "id": "d59dead0-a44c-44df-885f-030612038a48",
          "quantity": 1,
          "product": {
            "id": "c399bafb-3fbc-40c5-bef3-9158b7a19abc",
            "name": "Cookies",
            "brand": {
              "id": "db631527-c59c-409c-823f-42a24c972283",
              "name": "Cookie Company"
            }
          }
        }
      ]
    },
    "shipments": [],
    "amounts": {
      "amount_product": 1000,
      "amount_shipping": 1000,
      "amount_processing_fee": 100,
      "amount_pre_tax_total": 2100,
      "amount_tax": null,
      "amount_total": null,
      "amount_global_relay_cost": null
    },
    "sender": {
      "first_name": "Test",
      "last_name": "User",
      "email": "15556038009@test.ongoody.com"
    },
    "workspace_id": "8779bb01-ca47-4e9e-a845-d05f509c4be3",
    "workspace_name": "Test Team",
    "original_cart": null,
    "original_amounts": null,
    "reference_id": "PCI7GLZ3KFIEN8MWWSD5LDCF"
  }
}
```

## Schema

```json json_schema
{
  "$id": "http://json-schema.org/draft-07/schema#",
  "$schema": "http://json-schema.org/draft-07/schema#",
  "additionalProperties": false,
  "description": "",
  "properties": {
    "event_type": {
      "description": "The type of event that occurred",
      "properties": {},
      "type": "string"
    },
    "event_id": {
      "description": "The unique ID for this event",
      "properties": {},
      "type": "string"
    },
    "data": {
      "type": "object",
      "description": "An individual order contains the gift link to be sent to the recipient (if applicable) and other information about the order.",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid"
        },
        "recipient_first_name": {
          "type": "string"
        },
        "recipient_last_name": {
          "type": "string",
          "nullable": true
        },
        "recipient_email": {
          "type": "string",
          "nullable": true
        },
        "status": {
          "type": "string",
          "enum": [
            "created",
            "notified",
            "opened",
            "accepted",
            "pending_payment",
            "paid",
            "ordered",
            "shipped",
            "delivered",
            "failed",
            "canceled"
          ]
        },
        "individual_gift_link": {
          "type": "string",
          "description": "This gift link can be sent to the recipient or shared with the sender. For privacy reasons, this gift link does not display tracking information. A separate link, the recipient link, is sent directly to the recipient after they accept their gift, which does contain tracking information."
        },
        "cart": {
          "description": "The cart currently on this order. If the order is a gift that was swapped, `cart` displays the most recent products selected (i.e. post-swap).",
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid"
            },
            "items": {
              "type": "array",
              "items": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid"
                  },
                  "product": {
                    "type": "object",
                    "properties": {
                      "id": {
                        "type": "string",
                        "format": "uuid"
                      },
                      "name": {
                        "type": "string"
                      },
                      "brand": {
                        "type": "object",
                        "description": "The brand that this product is from.",
                        "properties": {
                          "id": {
                            "type": "string",
                            "format": "uuid"
                          },
                          "name": {
                            "type": "string"
                          }
                        },
                        "required": [
                          "id",
                          "name"
                        ]
                      }
                    },
                    "required": [
                      "id",
                      "name",
                      "brand"
                    ]
                  },
                  "quantity": {
                    "type": "integer"
                  }
                },
                "required": [
                  "id",
                  "product",
                  "quantity"
                ]
              }
            }
          }
        },
        "shipments": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "string",
                "format": "uuid"
              },
              "status": {
                "type": "string",
                "enum": [
                  "pending",
                  "tracking",
                  "shipped",
                  "delivered",
                  "delivered_override",
                  "failed",
                  "failed_unset_tracking",
                  "failed_with_reship"
                ]
              },
              "brand_name": {
                "type": "string",
                "description": "The name of the brand that this shipment is from."
              },
              "tracking_carrier": {
                "type": "string",
                "nullable": true,
                "description": "The carrier for this shipment, e.g. UPS."
              },
              "tracking_number": {
                "type": "string",
                "nullable": true,
                "description": "Only for approved distribution partners."
              },
              "shipped_at": {
                "type": "string",
                "format": "date-time",
                "description": "ISO 8601",
                "nullable": true
              },
              "delivered_at": {
                "type": "string",
                "format": "date-time",
                "description": "ISO 8601",
                "nullable": true
              },
              "delivery_eta": {
                "type": "string",
                "format": "date-time",
                "description": "The estimated delivery time of this shipment.",
                "nullable": true
              }
            },
            "required": [
              "id",
              "status",
              "brand_name"
            ]
          },
          "description": "A list of the shipments for the order."
        },
        "workspace_id": {
          "type": "string",
          "format": "uuid",
          "description": "Organizations are sub-divided into workspaces. Orders are contained in workspaces, identified by this ID."
        },
        "workspace_name": {
          "type": "string",
          "nullable": true
        },
        "expires_at": {
          "type": "string",
          "format": "date-time",
          "description": "For gifts, the date and time the gift is set to expire.",
          "nullable": true
        },
        "card_id": {
          "type": "string",
          "format": "uuid",
          "nullable": true,
          "description": "The digital greeting card on this gift."
        },
        "message": {
          "type": "string",
          "nullable": true,
          "description": "The message in this gift, provided by the sender."
        },
        "thank_you_note": {
          "type": "string",
          "nullable": true,
          "description": "A thank you note sent by the recipient."
        },
        "view_count_recipient": {
          "type": "integer",
          "description": "The number of times the recipient viewed the gift."
        },
        "is_swapped": {
          "type": "boolean",
          "description": "If this gift was swapped by the recipient. Swapping allows a recipient to select another product or products, which replaces the `cart`. The original products are saved to `original_cart`."
        },
        "order_batch_id": {
          "type": "string",
          "format": "uuid",
          "description": "On Goody for Business, all orders are attached to a order batch, which is a collection of one or more orders."
        },
        "amounts": {
          "type": "object",
          "description": "Costs in USD cents (i.e. $1.00 = 100). If the order was swapped, `amounts` displays the most recent amounts (i.e. post-swap).",
          "properties": {
            "amount_product": {
              "type": "integer",
              "description": "Total cost of the products in this order."
            },
            "amount_shipping": {
              "type": "integer",
              "description": "Total cost of shipping for this order."
            },
            "amount_processing_fee": {
              "type": "integer",
              "nullable": true,
              "description": "Total cost of processing fees for this order."
            },
            "amount_credit_applied": {
              "type": "integer",
              "nullable": true,
              "description": "Total amount of credit applied to this order."
            },
            "amount_pre_tax_total": {
              "type": "integer",
              "description": "Total cost of the products, shipping, and processing fees in this order."
            },
            "amount_tax": {
              "type": "integer",
              "nullable": true,
              "description": "Total tax for this order."
            },
            "amount_total": {
              "type": "integer",
              "nullable": true,
              "description": "Total cost of the products, shipping, processing fees, tax, and global shipping costs in this order."
            },
            "amount_global_relay_cost": {
              "type": "integer",
              "nullable": true,
              "description": "Total cost of global shipping for this order through the Global Relay service."
            }
          },
          "required": [
            "amount_product",
            "amount_shipping",
            "amount_pre_tax_total"
          ]
        },
        "event_times": {
          "type": "object",
          "description": "Only provided when calling the /orders/:id endpoint.",
          "properties": {
            "created_at": {
              "type": "string",
              "format": "date-time",
              "description": "ISO 8601"
            },
            "notified_at": {
              "type": "string",
              "format": "date-time",
              "description": "When the recipient was notified of the order.",
              "nullable": true
            },
            "opened_at": {
              "type": "string",
              "format": "date-time",
              "description": "For gifts, when the recipient opened the order.",
              "nullable": true
            },
            "accepted_at": {
              "type": "string",
              "format": "date-time",
              "description": "For gifts, when the recipient accepted the order.",
              "nullable": true
            },
            "pending_payment_at": {
              "type": "string",
              "format": "date-time",
              "description": "When the order entered pending payment status.",
              "nullable": true
            },
            "paid_at": {
              "type": "string",
              "format": "date-time",
              "description": "When the order was paid for.",
              "nullable": true
            },
            "shipped_at": {
              "type": "string",
              "format": "date-time",
              "description": "When the order was first shipped. If there are multiple shipments, this is when the first shipment shipped.",
              "nullable": true
            },
            "delivered_at": {
              "type": "string",
              "format": "date-time",
              "description": "When the order was delivered. If there are multiple shipments, this is when all shipments were delivered.",
              "nullable": true
            }
          },
          "required": [
            "created_at"
          ],
          "nullable": true
        },
        "original_cart": {
          "description": "If this order is a gift that was swapped, this displays the original cart that was sent to the recipient.",
          "nullable": true,
          "type": "object",
          "properties": {
            "id": {
              "type": "string",
              "format": "uuid"
            },
            "items": {
              "type": "array",
              "items": {
                "type": "object",
                "properties": {
                  "id": {
                    "type": "string",
                    "format": "uuid"
                  },
                  "product": {
                    "type": "object",
                    "properties": {
                      "id": {
                        "type": "string",
                        "format": "uuid"
                      },
                      "name": {
                        "type": "string"
                      },
                      "brand": {
                        "type": "object",
                        "description": "The brand that this product is from.",
                        "properties": {
                          "id": {
                            "type": "string",
                            "format": "uuid"
                          },
                          "name": {
                            "type": "string"
                          }
                        },
                        "required": [
                          "id",
                          "name"
                        ]
                      }
                    },
                    "required": [
                      "id",
                      "name",
                      "brand"
                    ]
                  },
                  "quantity": {
                    "type": "integer"
                  }
                },
                "required": [
                  "id",
                  "product",
                  "quantity"
                ]
              }
            }
          }
        },
        "original_amounts": {
          "type": "object",
          "description": "If this order is a gift that was swapped, this displays the original amounts of the cart that was sent to the recipient.",
          "properties": {
            "original_amount_product": {
              "type": "integer",
              "nullable": true
            },
            "original_amount_shipping": {
              "type": "integer",
              "nullable": true
            },
            "original_amount_credit_applied": {
              "type": "integer",
              "nullable": true
            },
            "original_amount_pre_tax_total": {
              "type": "integer",
              "nullable": true
            }
          },
          "nullable": true
        },
        "sender": {
          "description": "The Goody user who sent this order.",
          "type": "object",
          "properties": {
            "first_name": {
              "type": "string"
            },
            "last_name": {
              "type": "string"
            },
            "email": {
              "type": "string"
            }
          },
          "required": [
            "first_name",
            "last_name",
            "email"
          ]
        },
        "reference_id": {
          "type": "string",
          "description": "The reference ID displayed on receipts and other locations as the ID for this order."
        }
      },
      "required": [
        "id",
        "recipient_first_name",
        "status",
        "individual_gift_link",
        "cart",
        "shipments",
        "amounts",
        "sender",
        "reference_id"
      ]
    }
  },
  "required": [
    "data",
    "event_type",
    "event_id"
  ],
  "type": "object"
}
```