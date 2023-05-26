---
stoplight-id: d0ikb6tbavu24
---

# Event: order_batch.completed

Emitted when an order batch is fully processed, which is when all orders are created for each recipient in the order batch.

**For non-scheduled order batches,** the `order_batch.completed` event is emitted immediately after the order batch is finished processing and all orders have been created. *(This is instantly after the `order_batch.created` webhook event for order batches with 10 or fewer recipients, and shortly after the `order_batch.created` event for order batches with more than 10 recipients.)*

**For scheduled order batches,** the `order_batch.completed` event is emitted when the order batch scheduled time is reached, and orders are created for the order batch.

## Example

```json
{
  "event_type": "gift_batch.completed",
  "id": "ad097c47-bf12-45c9-8feb-0536a0012c09",
  "data": {
    "id": "bd1fd5b5-6339-4331-a404-66200143ff0f",
    "send_status": "complete",
    "from_name": "John",
    "message": "Thank you!",
    "gifts_count": 2,
    "gifts_preview": [
      {
        "id": "1f6e253e-4d03-4a85-a349-0659384ac894",
        "status": "created",
        "recipient_first_name": "Alena",
        "recipient_last_name": "Kenter",
        "recipient_email": "alena@ongoody.com",
        "individual_gift_link_shared": "https://gifts.ongoody.com/gift/Anc0HT0ZhyKAJguP75jt2Rar",
        "card_id": "60c4a674-4f0e-4031-9eca-645d34bb6cec",
        "message": "Thank you!",
        "thank_you_note": null,
        "view_count_recipient": 0,
        "is_swapped": false,
        "gift_batch_id": "bd1fd5b5-6339-4331-a404-66200143ff0f",
        "cart": {
          "id": "e0597695-5e19-4bbc-9a99-0fd540a9e68f",
          "items": [
            {
              "id": "5f4e70e9-5cc7-406e-8058-c513af667511",
              "quantity": 1,
              "product": {
                "id": "e69ea31a-320f-48f5-8fd7-0692df22328e",
                "name": "Cookies",
                "brand": {
                  "id": "393d847d-874b-4338-b834-fe3e0cf27644",
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
          "email": "15550197216@test.ongoody.com"
        },
        "workspace_id": "ae6e2795-8667-4d21-a1b0-fe7f642d7893",
        "workspace_name": "Test Team",
        "original_cart": null,
        "original_amounts": null,
        "reference_id": "LLRMPDGSSD7GXISGMACUKUIS"
      },
      {
        "id": "981c4abd-1f0c-4287-8c35-c7cea8f6f5da",
        "status": "created",
        "recipient_first_name": "Michael",
        "recipient_last_name": "Franci",
        "recipient_email": "michael@ongoody.com",
        "individual_gift_link_shared": "https://gifts.ongoody.com/gift/6p5k63B9ym4ksusHG6hr6xtA",
        "card_id": "60c4a674-4f0e-4031-9eca-645d34bb6cec",
        "message": "Thank you!",
        "thank_you_note": null,
        "view_count_recipient": 0,
        "is_swapped": false,
        "gift_batch_id": "bd1fd5b5-6339-4331-a404-66200143ff0f",
        "cart": {
          "id": "e0597695-5e19-4bbc-9a99-0fd540a9e68f",
          "items": [
            {
              "id": "5f4e70e9-5cc7-406e-8058-c513af667511",
              "quantity": 1,
              "product": {
                "id": "e69ea31a-320f-48f5-8fd7-0692df22328e",
                "name": "Cookies",
                "brand": {
                  "id": "393d847d-874b-4338-b834-fe3e0cf27644",
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
          "email": "15550197216@test.ongoody.com"
        },
        "workspace_id": "ae6e2795-8667-4d21-a1b0-fe7f642d7893",
        "workspace_name": "Test Team",
        "original_cart": null,
        "original_amounts": null,
        "reference_id": "U23DXZIHYSI4U9M8SBQ7XMVH"
      }
    ],
    "recipients_count": 2,
    "recipients_preview": [
      {
        "first_name": "Alena",
        "last_name": "Kenter",
        "email": "alena@ongoody.com"
      },
      {
        "first_name": "Michael",
        "last_name": "Franci",
        "email": "michael@ongoody.com"
      }
    ],
    "cart": {
      "id": "e0597695-5e19-4bbc-9a99-0fd540a9e68f",
      "items": [
        {
          "id": "5f4e70e9-5cc7-406e-8058-c513af667511",
          "quantity": 1,
          "product": {
            "id": "e69ea31a-320f-48f5-8fd7-0692df22328e",
            "name": "Cookies",
            "brand": {
              "id": "393d847d-874b-4338-b834-fe3e0cf27644",
              "name": "Cookie Company"
            }
          }
        }
      ]
    },
    "is_scheduled_send": false,
    "scheduled_send_on": null,
    "expires_at": null,
    "send_method": "link_multiple_custom_list",
    "batch_name": "Alena Kenter and Michael Franci",
    "card_id": "60c4a674-4f0e-4031-9eca-645d34bb6cec",
    "sender": {
      "first_name": "Test",
      "last_name": "User",
      "email": "15550197216@test.ongoody.com"
    },
    "workspace_id": "ae6e2795-8667-4d21-a1b0-fe7f642d7893",
    "workspace_name": "Test Team",
    "reference_id": "61Q2FSAHYYISJRZDHQXGYTBU"
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
      "description": "An order batch is the primary resource created by the API. Order batches contain an array of orders.",
      "properties": {
        "id": {
          "type": "string",
          "format": "uuid"
        },
        "send_status": {
          "description": "The `pending` status indicates that an order batch is being prepared to be sent out. If it is not scheduled, it is being sent asynchronously. If it is scheduled, it will stay in `pending` state until the scheduled time is reached, at which point it will be processed and moved to `complete`. When it is in `pending` status, no orders are created yet.\\n\\nWhen the order batch is in `complete` status, all orders are created and available.",
          "type": "string",
          "enum": [
            "pending",
            "complete",
            "failed",
            "canceled"
          ]
        },
        "from_name": {
          "type": "string",
          "description": "The name of the sender. This is displayed on the order and notifications."
        },
        "message": {
          "type": "string",
          "nullable": true,
          "description": "The message in this order batch, provided by the sender."
        },
        "orders_count": {
          "type": "integer",
          "description": "The total number of orders in this order batch. This might be blank if the order batch is scheduled for the future, or it could be fewer than the recipient count if the order batch is in the process of being sent."
        },
        "orders_preview": {
          "type": "array",
          "items": {
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
          },
          "description": "A preview of the first 10 orders in this order batch. To paginate through all of the orders, use the `/order_batches/:id/orders` endpoint with `?page&per_page`. If your use case never sends more than 10 orders in a single batch, you can use this field instead of calling `/order_batches/:id/orders`. For order batches with more than 10 recipients, this array will be empty while the orders are asynchronously created in the background."
        },
        "recipients_count": {
          "type": "integer",
          "description": "The total number of recipients in this order batch."
        },
        "recipients_preview": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "first_name": {
                "type": "string"
              },
              "last_name": {
                "type": "string",
                "nullable": true
              },
              "email": {
                "type": "string",
                "nullable": true
              }
            },
            "required": [
              "first_name"
            ]
          },
          "description": "A preview of the first 10 recipients in this order batch. To see all of the recipients, use `/order_batches/:id/recipients`. Recipients contain the original contact information provided for each recipient when the order batch was created."
        },
        "cart": {
          "description": "The cart that was sent for this order batch. This is the original cart that was created for this order batch. If individual orders were swapped, this still remains the same, whereas orders' `cart` would change if they were swapped.",
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
        "is_scheduled_send": {
          "type": "boolean",
          "description": "Whether this order batch was set up as a scheduled send. This stays as `true` after the scheduled send is complete. To determine if the order batch is scheduled to be sent for the future, check if `status` is `pending` and `scheduled_send_on` is in the future. When a order batch is scheduled, orders are only created on the scheduled send date."
        },
        "scheduled_send_on": {
          "type": "string",
          "format": "date-time",
          "description": "The date and time the order batch is scheduled to be sent. This will be `null` if the order batch is not a scheduled send. This field remains after the scheduled send completes. ISO 8601, UTC.",
          "nullable": true
        },
        "expires_at": {
          "type": "string",
          "format": "date-time",
          "description": "The date and time the order batch is set to expire. ISO 8601, UTC.",
          "nullable": true
        },
        "send_method": {
          "nullable": true,
          "type": "string",
          "enum": [
            "link_multiple_custom_list"
          ],
          "description": "The method for sending a order batch. Currently, the only supported send method is `link_multiple_custom_list` which specifies that a link should be created for each order, but no email should automatically be sent to the recipient."
        },
        "batch_name": {
          "type": "string",
          "nullable": true,
          "description": "An internal name for the order batch, falling back to an auto-generated batch name. Not displayed to recipients."
        },
        "card_id": {
          "type": "string",
          "format": "uuid",
          "nullable": true,
          "description": "The digital greeting card on this order batch."
        },
        "sender": {
          "description": "The sender of the order batch.",
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
        "workspace_id": {
          "type": "string",
          "format": "uuid",
          "description": "Organizations are sub-divided into workspaces. Order batches are contained in workspaces, identified by this ID."
        },
        "workspace_name": {
          "type": "string"
        },
        "reference_id": {
          "type": "string",
          "description": "The reference ID displayed on receipts and other locations as the ID for this order batch."
        }
      },
      "required": [
        "id",
        "send_status",
        "orders_preview",
        "orders_count",
        "cart",
        "from_name",
        "recipients_preview",
        "recipients_count",
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