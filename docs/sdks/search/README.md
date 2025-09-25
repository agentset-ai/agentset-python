# Search
(*search*)

## Overview

### Available Operations

* [execute](#execute) - Search a namespace

## execute

Search a namespace for a query.

### Example Usage

<!-- UsageSnippet language="python" operationID="search" method="post" path="/v1/namespace/{namespaceId}/search" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.search.execute(query="<value>", top_k=10, rerank=True, include_relationships=False, include_metadata=True, mode="semantic")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `query`                                                                 | *str*                                                                   | :heavy_check_mark:                                                      | The query to search for.                                                |
| `top_k`                                                                 | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | The number of results to fetch from the vector store. Defaults to `10`. |
| `rerank`                                                                | *Optional[bool]*                                                        | :heavy_minus_sign:                                                      | Whether to rerank the results. Defaults to `true`.                      |
| `rerank_limit`                                                          | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | The number of results to return after reranking. Defaults to `topK`.    |
| `filter_`                                                               | Dict[str, *Any*]                                                        | :heavy_minus_sign:                                                      | A filter to apply to the results.                                       |
| `min_score`                                                             | *Optional[float]*                                                       | :heavy_minus_sign:                                                      | The minimum score to return.                                            |
| `include_relationships`                                                 | *Optional[bool]*                                                        | :heavy_minus_sign:                                                      | Whether to include relationships in the results. Defaults to `false`.   |
| `include_metadata`                                                      | *Optional[bool]*                                                        | :heavy_minus_sign:                                                      | Whether to include metadata in the results. Defaults to `true`.         |
| `keyword_filter`                                                        | *Optional[str]*                                                         | :heavy_minus_sign:                                                      | N/A                                                                     |
| `mode`                                                                  | [Optional[models.Mode]](../../models/mode.md)                           | :heavy_minus_sign:                                                      | N/A                                                                     |
| `retries`                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)        | :heavy_minus_sign:                                                      | Configuration to override the default retry behavior of the client.     |

### Response

**[models.SearchResponse](../../models/searchresponse.md)**

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