# BatchPayloadItemText


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `type`                                                           | *Literal["TEXT"]*                                                | :heavy_check_mark:                                               | N/A                                                              |
| `text`                                                           | *str*                                                            | :heavy_check_mark:                                               | The text to ingest.                                              |
| `file_name`                                                      | *OptionalNullable[str]*                                          | :heavy_minus_sign:                                               | N/A                                                              |
| `config`                                                         | [Optional[models.IngestJobConfig]](../models/ingestjobconfig.md) | :heavy_minus_sign:                                               | The ingest job config.                                           |