# ForbiddenError

The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401 Unauthorized, the client's identity is known to the server.


## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          | Example                                              |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `success`                                            | *bool*                                               | :heavy_check_mark:                                   | N/A                                                  | false                                                |
| `error`                                              | [models.ForbiddenError](../models/forbiddenerror.md) | :heavy_check_mark:                                   | N/A                                                  |                                                      |