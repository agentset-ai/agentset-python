# Uploads
(*uploads*)

## Overview

### Available Operations

* [create](#create) - Create presigned URL for file upload
* [create_batch](#create_batch) - Create presigned URLs for batch file upload

## create

Generate a presigned URL for uploading a single file to the specified namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="createUpload" method="post" path="/v1/namespace/{namespaceId}/uploads" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.uploads.create(file_name="document.pdf", content_type="application/pdf", file_size=1024)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `file_name`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `content_type`                                                      | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `file_size`                                                         | *float*                                                             | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateUploadResponse](../../models/createuploadresponse.md)**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.BadRequestError          | 400                             | application/json                |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.ForbiddenError           | 403                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.ConflictError            | 409                             | application/json                |
| errors.InviteExpiredError       | 410                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.RateLimitExceededError   | 429                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.AgentsetDefaultError     | 4XX, 5XX                        | \*/\*                           |

## create_batch

Generate presigned URLs for uploading multiple files to the specified namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="createBatchUpload" method="post" path="/v1/namespace/{namespaceId}/uploads/batch" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.uploads.create_batch(files=[])

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `files`                                                             | List[[models.UploadFileSchema](../../models/uploadfileschema.md)]   | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateBatchUploadResponse](../../models/createbatchuploadresponse.md)**

### Errors

| Error Type                      | Status Code                     | Content Type                    |
| ------------------------------- | ------------------------------- | ------------------------------- |
| errors.BadRequestError          | 400                             | application/json                |
| errors.UnauthorizedError        | 401                             | application/json                |
| errors.ForbiddenError           | 403                             | application/json                |
| errors.NotFoundError            | 404                             | application/json                |
| errors.ConflictError            | 409                             | application/json                |
| errors.InviteExpiredError       | 410                             | application/json                |
| errors.UnprocessableEntityError | 422                             | application/json                |
| errors.RateLimitExceededError   | 429                             | application/json                |
| errors.InternalServerError      | 500                             | application/json                |
| errors.AgentsetDefaultError     | 4XX, 5XX                        | \*/\*                           |