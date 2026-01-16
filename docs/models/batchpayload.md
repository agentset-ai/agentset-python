# BatchPayload


## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `type`                                                                   | *Literal["BATCH"]*                                                       | :heavy_check_mark:                                                       | N/A                                                                      |
| `items`                                                                  | List[[models.BatchPayloadItemUnion](../models/batchpayloaditemunion.md)] | :heavy_check_mark:                                                       | The items to ingest.                                                     |