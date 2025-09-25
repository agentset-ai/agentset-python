# UnauthorizedError


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `code`                                                              | [models.UnauthorizedCode](../models/unauthorizedcode.md)            | :heavy_check_mark:                                                  | A short code indicating the error code returned.                    | unauthorized                                                        |
| `message`                                                           | *str*                                                               | :heavy_check_mark:                                                  | A human readable explanation of what went wrong.                    | The requested resource was not found.                               |
| `doc_url`                                                           | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | A link to our documentation with more details about this error code | https://docs.agentset.ai/api-reference/errors#unauthorized          |