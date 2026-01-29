# IngestJobWebhookEvent

Triggered when an ingest job is queued, processed, ready, or deleted.


## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `id`                                                                       | *str*                                                                      | :heavy_check_mark:                                                         | N/A                                                                        |
| `event`                                                                    | *Literal["ingest_job.queued"]*                                             | :heavy_check_mark:                                                         | N/A                                                                        |
| `created_at`                                                               | *str*                                                                      | :heavy_check_mark:                                                         | N/A                                                                        |
| `data`                                                                     | [models.IngestJobWebhookEventData](../models/ingestjobwebhookeventdata.md) | :heavy_check_mark:                                                         | N/A                                                                        |