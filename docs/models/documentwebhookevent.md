# DocumentWebhookEvent

Triggered when a document is queued, processed, ready, or deleted.


## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `id`                                                                     | *str*                                                                    | :heavy_check_mark:                                                       | N/A                                                                      |
| `event`                                                                  | *Literal["document.queued"]*                                             | :heavy_check_mark:                                                       | N/A                                                                      |
| `created_at`                                                             | *str*                                                                    | :heavy_check_mark:                                                       | N/A                                                                      |
| `data`                                                                   | [models.DocumentWebhookEventData](../models/documentwebhookeventdata.md) | :heavy_check_mark:                                                       | N/A                                                                      |