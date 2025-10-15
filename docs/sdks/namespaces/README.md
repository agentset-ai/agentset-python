# Namespaces
(*namespaces*)

## Overview

### Available Operations

* [list](#list) - Retrieve a list of namespaces
* [create](#create) - Create a namespace.
* [get](#get) - Retrieve a namespace
* [update](#update) - Update a namespace.
* [delete](#delete) - Delete a namespace.

## list

Retrieve a list of namespaces for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="listNamespaces" method="get" path="/v1/namespace" -->
```python
from agentset import Agentset


with Agentset(
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.list()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ListNamespacesResponse](../../models/listnamespacesresponse.md)**

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

## create

Create a namespace for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="createNamespace" method="post" path="/v1/namespace" -->
```python
from agentset import Agentset


with Agentset(
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.create(name="<value>", slug="<value>", embedding_config={
        "provider": "GOOGLE",
        "model": "text-embedding-004",
        "api_key": "<value>",
    }, vector_store_config={
        "provider": "PINECONE",
        "api_key": "<value>",
        "index_host": "https://example.svc.aped-1234-a56b.pinecone.io",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                                                | Type                                                                                                                                                                     | Required                                                                                                                                                                 | Description                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `name`                                                                                                                                                                   | *str*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `slug`                                                                                                                                                                   | *str*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `embedding_config`                                                                                                                                                       | [Optional[models.EmbeddingModelConfig]](../../models/embeddingmodelconfig.md)                                                                                            | :heavy_minus_sign:                                                                                                                                                       | The embedding model config. If not provided, our managed embedding model will be used. Note: You can't change the embedding model config after the namespace is created. |
| `vector_store_config`                                                                                                                                                    | [Optional[models.CreateVectorStoreConfig]](../../models/createvectorstoreconfig.md)                                                                                      | :heavy_minus_sign:                                                                                                                                                       | The vector store config. If not provided, our MANAGED_PINECONE vector store will be used. Note: You can't change the vector store config after the namespace is created. |
| `retries`                                                                                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                                         | :heavy_minus_sign:                                                                                                                                                       | Configuration to override the default retry behavior of the client.                                                                                                      |

### Response

**[models.CreateNamespaceResponse](../../models/createnamespaceresponse.md)**

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

## get

Retrieve the info for a namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="getNamespace" method="get" path="/v1/namespace/{namespaceId}" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.get()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.GetNamespaceRequest](../../models/getnamespacerequest.md)   | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetNamespaceResponse](../../models/getnamespaceresponse.md)**

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

Update a namespace for the authenticated organization. If there is no change, return it as it is.

### Example Usage

<!-- UsageSnippet language="python" operationID="updateNamespace" method="patch" path="/v1/namespace/{namespaceId}" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.update()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `name`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `slug`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UpdateNamespaceResponse](../../models/updatenamespaceresponse.md)**

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

Delete a namespace for the authenticated organization. This will delete all the data associated with the namespace.

### Example Usage

<!-- UsageSnippet language="python" operationID="deleteNamespace" method="delete" path="/v1/namespace/{namespaceId}" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.delete()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [models.DeleteNamespaceRequest](../../models/deletenamespacerequest.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |
| `retries`                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)        | :heavy_minus_sign:                                                      | Configuration to override the default retry behavior of the client.     |

### Response

**[models.DeleteNamespaceResponse](../../models/deletenamespaceresponse.md)**

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