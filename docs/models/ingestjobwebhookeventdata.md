# IngestJobWebhookEventData


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `id`                                                   | *str*                                                  | :heavy_check_mark:                                     | Unique identifier for the ingest job.                  |
| `name`                                                 | *Nullable[str]*                                        | :heavy_check_mark:                                     | Name of the ingest job.                                |
| `namespace_id`                                         | *str*                                                  | :heavy_check_mark:                                     | ID of the namespace.                                   |
| `organization_id`                                      | *str*                                                  | :heavy_check_mark:                                     | ID of the organization.                                |
| `status`                                               | [models.IngestJobStatus](../models/ingestjobstatus.md) | :heavy_check_mark:                                     | The status of the ingest job.                          |
| `error`                                                | *OptionalNullable[str]*                                | :heavy_minus_sign:                                     | Error message if ingest job failed.                    |
| `created_at`                                           | *str*                                                  | :heavy_check_mark:                                     | When the ingest job was created.                       |
| `updated_at`                                           | *str*                                                  | :heavy_check_mark:                                     | When the ingest job was last updated.                  |