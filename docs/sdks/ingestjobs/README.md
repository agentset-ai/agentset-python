# IngestJobs
(*ingest_jobs*)

## Overview

### Available Operations

* [list](#list) - Retrieve a list of ingest jobs
* [create](#create) - Create an ingest job
* [get](#get) - Retrieve an ingest job
* [delete](#delete) - Delete an ingest job
* [re_ingest](#re_ingest) - Re-ingest a job

## list

Retrieve a paginated list of ingest jobs for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="listIngestJobs" method="get" path="/v1/namespace/{namespaceId}/ingest-jobs" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.ingest_jobs.list(order_by="createdAt", order="desc", cursor_direction="forward", per_page=30)

    while res is not None:
        # Handle items

        res = res.next()

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `statuses`                                                                              | List[[models.IngestJobStatus](../../models/ingestjobstatus.md)]                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `order_by`                                                                              | [Optional[models.ListIngestJobsOrderBy]](../../models/listingestjobsorderby.md)         | :heavy_minus_sign:                                                                      | The field to order by. Default is `createdAt`.                                          |
| `order`                                                                                 | [Optional[models.ListIngestJobsOrder]](../../models/listingestjobsorder.md)             | :heavy_minus_sign:                                                                      | The sort order. Default is `desc`.                                                      |
| `cursor`                                                                                | *Optional[str]*                                                                         | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `cursor_direction`                                                                      | [Optional[models.PaginationCursorDirection]](../../models/paginationcursordirection.md) | :heavy_minus_sign:                                                                      | The direction to paginate by.                                                           |
| `per_page`                                                                              | *Optional[float]*                                                                       | :heavy_minus_sign:                                                                      | N/A                                                                                     |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.ListIngestJobsResponse](../../models/listingestjobsresponse.md)**

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

Create an ingest job for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="createIngestJob" method="post" path="/v1/namespace/{namespaceId}/ingest-jobs" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.ingest_jobs.create(payload={
        "type": "TEXT",
        "text": "<value>",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `payload`                                                           | [models.IngestJobPayload](../../models/ingestjobpayload.md)         | :heavy_check_mark:                                                  | The ingest job payload.                                             |
| `name`                                                              | *OptionalNullable[str]*                                             | :heavy_minus_sign:                                                  | The name of the ingest job.                                         |
| `config`                                                            | [Optional[models.IngestJobConfig]](../../models/ingestjobconfig.md) | :heavy_minus_sign:                                                  | The ingest job config.                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreateIngestJobResponse](../../models/createingestjobresponse.md)**

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

Retrieve the info for an ingest job.

### Example Usage

<!-- UsageSnippet language="python" operationID="getIngestJobInfo" method="get" path="/v1/namespace/{namespaceId}/ingest-jobs/{jobId}" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.ingest_jobs.get(job_id="job_123")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `job_id`                                                            | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | job_123                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.GetIngestJobInfoResponse](../../models/getingestjobinforesponse.md)**

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

Delete an ingest job for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="deleteIngestJob" method="delete" path="/v1/namespace/{namespaceId}/ingest-jobs/{jobId}" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.ingest_jobs.delete(job_id="job_123")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `job_id`                                                            | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | job_123                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.DeleteIngestJobResponse](../../models/deleteingestjobresponse.md)**

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

## re_ingest

Re-ingest a job for the authenticated organization.

### Example Usage

<!-- UsageSnippet language="python" operationID="reIngestJob" method="post" path="/v1/namespace/{namespaceId}/ingest-jobs/{jobId}/re-ingest" -->
```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.ingest_jobs.re_ingest(job_id="job_123")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `job_id`                                                            | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | job_123                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.ReIngestJobResponse](../../models/reingestjobresponse.md)**

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