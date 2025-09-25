# BatchPayloadOutputItemManagedFile


## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `type`                                                                       | *Literal["MANAGED_FILE"]*                                                    | :heavy_check_mark:                                                           | N/A                                                                          |
| `key`                                                                        | *str*                                                                        | :heavy_check_mark:                                                           | The key of the managed file to ingest.                                       |
| `file_name`                                                                  | *OptionalNullable[str]*                                                      | :heavy_minus_sign:                                                           | N/A                                                                          |
| `config`                                                                     | [Optional[models.IngestJobConfigOutput]](../models/ingestjobconfigoutput.md) | :heavy_minus_sign:                                                           | The ingest job config.                                                       |