# NamespaceSDK
(*namespace*)

## Overview

### Available Operations

* [warm_up](#warm_up) - Warm cache for a namespace

## warm_up

Pre-loads the namespace into the vector store's cache for faster query performance. Not all vector stores support this operation. Currently only Turbopuffer supports this operation.

### Example Usage

<!-- UsageSnippet language="python" operationID="warmUp" method="post" path="/v1/namespace/{namespaceId}/warm-up" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespace.warm_up()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                      | Type                                                                                                                                           | Required                                                                                                                                       | Description                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `x_tenant_id`                                                                                                                                  | *Optional[str]*                                                                                                                                | :heavy_minus_sign:                                                                                                                             | Optional tenant id to use for the request. If not provided, the namespace will be used directly. Must be alphanumeric and up to 64 characters. |
| `retries`                                                                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                               | :heavy_minus_sign:                                                                                                                             | Configuration to override the default retry behavior of the client.                                                                            |

### Response

**[models.WarmUpResponse](../../models/warmupresponse.md)**

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