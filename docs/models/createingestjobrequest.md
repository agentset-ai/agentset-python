# CreateIngestJobRequest


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `name`                                                           | *OptionalNullable[str]*                                          | :heavy_minus_sign:                                               | The name of the ingest job.                                      |
| `payload`                                                        | [models.IngestJobPayload](../models/ingestjobpayload.md)         | :heavy_check_mark:                                               | The ingest job payload.                                          |
| `config`                                                         | [Optional[models.IngestJobConfig]](../models/ingestjobconfig.md) | :heavy_minus_sign:                                               | The ingest job config.                                           |