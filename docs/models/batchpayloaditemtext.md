# BatchPayloadItemText


## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `type`                                                                     | *Literal["TEXT"]*                                                          | :heavy_check_mark:                                                         | N/A                                                                        |
| `file_name`                                                                | *OptionalNullable[str]*                                                    | :heavy_minus_sign:                                                         | N/A                                                                        |
| `text`                                                                     | *str*                                                                      | :heavy_check_mark:                                                         | The text to ingest.                                                        |
| `config`                                                                   | [Optional[models.DocumentConfigOutput]](../models/documentconfigoutput.md) | :heavy_minus_sign:                                                         | The document config.                                                       |