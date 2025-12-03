# BatchPayloadInputItemFile


## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `type`                                                         | *Literal["FILE"]*                                              | :heavy_check_mark:                                             | N/A                                                            |
| `file_url`                                                     | *str*                                                          | :heavy_check_mark:                                             | The URL of the file to ingest.                                 |
| `file_name`                                                    | *OptionalNullable[str]*                                        | :heavy_minus_sign:                                             | N/A                                                            |
| `config`                                                       | [Optional[models.DocumentConfig]](../models/documentconfig.md) | :heavy_minus_sign:                                             | The document config.                                           |