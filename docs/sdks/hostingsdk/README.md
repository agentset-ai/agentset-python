# HostingSDK
(*hosting*)

## Overview

### Available Operations

* [get](#get) - Retrieve hosting configuration
* [enable](#enable) - Enable hosting
* [update](#update) - Update hosting configuration
* [delete](#delete) - Delete hosting configuration

## get

Retrieve the hosting configuration for a namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="getHosting" method="get" path="/v1/namespace/{namespaceId}/hosting" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.hosting.get()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.GetHostingRequest](../../models/gethostingrequest.md)       | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetHostingResponse](../../models/gethostingresponse.md)**

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

## enable

Enable hosting for a namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="enableHosting" method="post" path="/v1/namespace/{namespaceId}/hosting" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.hosting.enable()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.EnableHostingRequest](../../models/enablehostingrequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.EnableHostingResponse](../../models/enablehostingresponse.md)**

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

## update

Update the hosting configuration for a namespace. If there is no change, return it as it is.

### Example Usage

<!-- UsageSnippet language="python" operationID="updateHosting" method="patch" path="/v1/namespace/{namespaceId}/hosting" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.hosting.update()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `title`                                                                               | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `slug`                                                                                | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `logo`                                                                                | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `protected`                                                                           | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `allowed_emails`                                                                      | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `allowed_email_domains`                                                               | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `system_prompt`                                                                       | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `example_questions`                                                                   | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `example_search_queries`                                                              | List[*str*]                                                                           | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `welcome_message`                                                                     | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `citation_metadata_path`                                                              | *Optional[str]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `search_enabled`                                                                      | *Optional[bool]*                                                                      | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `rerank_model`                                                                        | [Optional[models.UpdateHostingRerankModel]](../../models/updatehostingrerankmodel.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `llm_model`                                                                           | [Optional[models.LlmModel]](../../models/llmmodel.md)                                 | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.UpdateHostingResponse](../../models/updatehostingresponse.md)**

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

## delete

Delete the hosting configuration for a namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="deleteHosting" method="delete" path="/v1/namespace/{namespaceId}/hosting" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.hosting.delete()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.DeleteHostingRequest](../../models/deletehostingrequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.DeleteHostingResponse](../../models/deletehostingresponse.md)**

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