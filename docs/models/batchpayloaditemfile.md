# BatchPayloadItemFile


## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `type`                                                           | *Literal["FILE"]*                                                | :heavy_check_mark:                                               | N/A                                                              |
| `file_url`                                                       | *str*                                                            | :heavy_check_mark:                                               | The URL of the file to ingest.                                   |
| `file_name`                                                      | *OptionalNullable[str]*                                          | :heavy_minus_sign:                                               | N/A                                                              |
| `config`                                                         | [Optional[models.IngestJobConfig]](../models/ingestjobconfig.md) | :heavy_minus_sign:                                               | The ingest job config.                                           |