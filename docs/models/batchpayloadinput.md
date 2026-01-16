# BatchPayloadInput


## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `type`                                                                             | *Literal["BATCH"]*                                                                 | :heavy_check_mark:                                                                 | N/A                                                                                |
| `items`                                                                            | List[[models.BatchPayloadInputItemUnion](../models/batchpayloadinputitemunion.md)] | :heavy_check_mark:                                                                 | The items to ingest.                                                               |