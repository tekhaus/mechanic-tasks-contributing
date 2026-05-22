# Monitor for variants with zero price

Tags: Alert, Custom Webhook, Price, Products, Variants, Watch

Use this task to send an email alert any time an active, published product is updated that has one or more variants with a zero price. Optionally choose to cache the alerts for X number of hours, so the task does not alert on the same product in that time period.

* View in the task library: [tasks.mechanic.dev/monitor-for-variants-with-zero-price](https://tasks.mechanic.dev/monitor-for-variants-with-zero-price)
* Task JSON, for direct import: [task.json](../../tasks/monitor-for-variants-with-zero-price.json)
* Preview task code: [script.liquid](./script.liquid)

## Default options

```json
{
  "mechanic_user_topic__required": "user/product_update/variants_zero_price",
  "alert_email_recipients__array_required": null,
  "cache_alert_for_x_hours__number": null
}
```

[Learn about task options in Mechanic](https://learn.mechanic.dev/core/tasks/options)

## Subscriptions

```liquid
user/product_update/variants_zero_price
```

[Learn about event subscriptions in Mechanic](https://learn.mechanic.dev/core/tasks/subscriptions)

## Documentation

Use this task to send an email alert any time an active, published product is updated that has one or more variants with a zero price. Optionally choose to cache the alerts for X number of hours, so the task does not alert on the same product in that time period.

**IMPORTANT**: This task requires a [custom Shopify webhook](https://learn.mechanic.dev/platform/shopify/custom-webhooks) to be enabled and configured as follows:
- _Name_: (suggested - "Variants with zero price")
- _Mechanic topic_: (must start with `user/`, must match what you configure in this task configuration)
- _Shopify topic_: `shopify/products/update`
- _Filter_: `variants.price:"0.00" AND status:active AND published_at:*`
- _Include fields_:
    - id
    - updated_at
    - title
    - status
    - published_at
    - variants.id
    - variants.updated_at
    - variants.title
    - variants.sku
    - variants.price

Alternatively, copy the custom webhook JSON import from [here](https://learn.mechanic.dev/resources/task-library/custom-webhook-imports).

## Installing this task

Find this task [in the library at tasks.mechanic.dev](https://tasks.mechanic.dev/monitor-for-variants-with-zero-price), and use the "Try this task" button. Or, import [this task's JSON export](../../tasks/monitor-for-variants-with-zero-price.json) – see [Importing and exporting tasks](https://learn.mechanic.dev/core/tasks/import-and-export) to learn how imports work.

## Contributions

Found a bug? Got an improvement to add? Start here: [../../CONTRIBUTING.md](../../CONTRIBUTING.md).

## Task requests

Submit your [task requests](https://mechanic.canny.io/task-requests) for consideration by the Mechanic community, and they may be chosen for development and inclusion in the [task library](https://tasks.mechanic.dev/)!
