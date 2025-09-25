# agentset

Developer-friendly & type-safe Python SDK specifically catered to leverage *agentset* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=agentset&utm_campaign=python"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/agentset-ktc/api). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

AgentsetAPI: Agentset is agentic rag-as-a-service
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [agentset](#agentset)
  * [SDK Installation](#sdk-installation)
  * [IDE Support](#ide-support)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Global Parameters](#global-parameters)
  * [Pagination](#pagination)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Resource Management](#resource-management)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!TIP]
> To finish publishing your SDK to PyPI you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


> [!NOTE]
> **Python version upgrade policy**
>
> Once a Python version reaches its [official end of life date](https://devguide.python.org/versions/), a 3-month grace period is provided for users to upgrade. Following this grace period, the minimum python version supported in the SDK will be updated.

The SDK can be installed with *uv*, *pip*, or *poetry* package managers.

### uv

*uv* is a fast Python package installer and resolver, designed as a drop-in replacement for pip and pip-tools. It's recommended for its speed and modern Python tooling capabilities.

```bash
uv add git+<UNSET>.git
```

### PIP

*PIP* is the default package installer for Python, enabling easy installation and management of packages from PyPI via the command line.

```bash
pip install git+<UNSET>.git
```

### Poetry

*Poetry* is a modern tool that simplifies dependency management and package publishing by using a single `pyproject.toml` file to handle project metadata and dependencies.

```bash
poetry add git+<UNSET>.git
```

### Shell and script usage with `uv`

You can use this SDK in a Python shell with [uv](https://docs.astral.sh/uv/) and the `uvx` command that comes with it like so:

```shell
uvx --from agentset python
```

It's also possible to write a standalone Python script without needing to set up a whole project like so:

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.9"
# dependencies = [
#     "agentset",
# ]
# ///

from agentset import Agentset

sdk = Agentset(
  # SDK arguments
)

# Rest of script here...
```

Once that is saved to a file, you can run it with `uv run script.py` where
`script.py` can be replaced with the actual file name.
<!-- End SDK Installation [installation] -->

<!-- Start IDE Support [idesupport] -->
## IDE Support

### PyCharm

Generally, the SDK will work well with most IDEs out of the box. However, when using PyCharm, you can enjoy much better integration with Pydantic by installing an additional plugin.

- [PyCharm Pydantic Plugin](https://docs.pydantic.dev/latest/integrations/pycharm/)
<!-- End IDE Support [idesupport] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```python
# Synchronous Example
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

</br>

The same SDK client can also be used to make asynchronous requests by importing asyncio.

```python
# Asynchronous Example
from agentset import Agentset
import asyncio

async def main():

    async with Agentset(
        token="AGENTSET_API_KEY",
    ) as a_client:

        res = await a_client.namespaces.create_async(name="<value>", slug="<value>", embedding_config={
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

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name    | Type | Scheme      | Environment Variable |
| ------- | ---- | ----------- | -------------------- |
| `token` | http | HTTP Bearer | `AGENTSET_TOKEN`     |

To authenticate with the API the `token` parameter must be set when initializing the SDK client instance. For example:
```python
from agentset import Agentset


with Agentset(
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.list()

    # Handle response
    print(res)

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>


### [documents](docs/sdks/documents/README.md)

* [list](docs/sdks/documents/README.md#list) - Retrieve a list of documents
* [get](docs/sdks/documents/README.md#get) - Retrieve a document
* [delete](docs/sdks/documents/README.md#delete) - Delete a document

### [ingest_jobs](docs/sdks/ingestjobs/README.md)

* [list](docs/sdks/ingestjobs/README.md#list) - Retrieve a list of ingest jobs
* [create](docs/sdks/ingestjobs/README.md#create) - Create an ingest job
* [get](docs/sdks/ingestjobs/README.md#get) - Retrieve an ingest job
* [delete](docs/sdks/ingestjobs/README.md#delete) - Delete an ingest job
* [re_ingest](docs/sdks/ingestjobs/README.md#re_ingest) - Re-ingest a job

### [namespaces](docs/sdks/namespaces/README.md)

* [list](docs/sdks/namespaces/README.md#list) - Retrieve a list of namespaces
* [create](docs/sdks/namespaces/README.md#create) - Create a namespace.
* [get](docs/sdks/namespaces/README.md#get) - Retrieve a namespace
* [update](docs/sdks/namespaces/README.md#update) - Update a namespace.
* [delete](docs/sdks/namespaces/README.md#delete) - Delete a namespace.

### [search](docs/sdks/search/README.md)

* [execute](docs/sdks/search/README.md#execute) - Search a namespace

### [uploads](docs/sdks/uploads/README.md)

* [create](docs/sdks/uploads/README.md#create) - Create presigned URL for file upload
* [create_batch](docs/sdks/uploads/README.md#create_batch) - Create presigned URLs for batch file upload

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Global Parameters [global-parameters] -->
## Global Parameters

Certain parameters are configured globally. These parameters may be set on the SDK client instance itself during initialization. When configured as an option during SDK initialization, These global values will be used as defaults on the operations that use them. When such operations are called, there is a place in each to override the global value, if needed.

For example, you can set `namespaceId` to `"ns_123"` at SDK initialization and then you do not have to pass the same value on calls to operations like `get`. But if you want to do so you may, which will locally override the global setting. See the example code below for a demonstration.


### Available Globals

The following global parameters are available.
Global parameters can also be set via environment variable.

| Name         | Type | Description                                                                             | Environment           |
| ------------ | ---- | --------------------------------------------------------------------------------------- | --------------------- |
| namespace_id | str  | The namespace_id parameter.                                                             | AGENTSET_NAMESPACE_ID |
| x_tenant_id  | str  | The tenant id to use for the request. If not provided, the default tenant will be used. | AGENTSET_X_TENANT_ID  |

### Example

```python
from agentset import Agentset


with Agentset(
    namespace_id="ns_123",
    x_tenant_id="<id>",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.get()

    # Handle response
    print(res)

```
<!-- End Global Parameters [global-parameters] -->

<!-- Start Pagination [pagination] -->
## Pagination

Some of the endpoints in this SDK support pagination. To use pagination, you make your SDK calls as usual, but the
returned response object will have a `Next` method that can be called to pull down the next group of results. If the
return value of `Next` is `None`, then there are no more pages to be fetched.

Here's an example of one such pagination call:
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
<!-- End Pagination [pagination] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `RetryConfig` object to the call:
```python
from agentset import Agentset
from agentset.utils import BackoffStrategy, RetryConfig


with Agentset(
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.list(,
        RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False))

    # Handle response
    print(res)

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `retry_config` optional parameter when initializing the SDK:
```python
from agentset import Agentset
from agentset.utils import BackoffStrategy, RetryConfig


with Agentset(
    retry_config=RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False),
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.list()

    # Handle response
    print(res)

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`AgentsetError`](./src/agentset/errors/agentseterror.py) is the base class for all HTTP error responses. It has the following properties:

| Property           | Type             | Description                                                                             |
| ------------------ | ---------------- | --------------------------------------------------------------------------------------- |
| `err.message`      | `str`            | Error message                                                                           |
| `err.status_code`  | `int`            | HTTP response status code eg `404`                                                      |
| `err.headers`      | `httpx.Headers`  | HTTP response headers                                                                   |
| `err.body`         | `str`            | HTTP body. Can be empty string if no body is returned.                                  |
| `err.raw_response` | `httpx.Response` | Raw HTTP response                                                                       |
| `err.data`         |                  | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```python
from agentset import Agentset, errors


with Agentset(
    token="AGENTSET_API_KEY",
) as a_client:
    res = None
    try:

        res = a_client.namespaces.list()

        # Handle response
        print(res)


    except errors.AgentsetError as e:
        # The base class for HTTP error responses
        print(e.message)
        print(e.status_code)
        print(e.body)
        print(e.headers)
        print(e.raw_response)

        # Depending on the method different errors may be thrown
        if isinstance(e, errors.BadRequestError):
            print(e.data.success)  # bool
            print(e.data.error)  # models.BadRequestError
```

### Error Classes
**Primary errors:**
* [`AgentsetError`](./src/agentset/errors/agentseterror.py): The base class for HTTP error responses.
  * [`BadRequestError`](./src/agentset/errors/badrequesterror.py): The server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing). Status code `400`.
  * [`UnauthorizedError`](./src/agentset/errors/unauthorizederror.py): Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response. Status code `401`.
  * [`ForbiddenError`](./src/agentset/errors/forbiddenerror.py): The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401 Unauthorized, the client's identity is known to the server. Status code `403`.
  * [`NotFoundError`](./src/agentset/errors/notfounderror.py): The server cannot find the requested resource. Status code `404`.
  * [`ConflictError`](./src/agentset/errors/conflicterror.py): This response is sent when a request conflicts with the current state of the server. Status code `409`.
  * [`InviteExpiredError`](./src/agentset/errors/inviteexpirederror.py): This response is sent when the requested content has been permanently deleted from server, with no forwarding address. Status code `410`.
  * [`UnprocessableEntityError`](./src/agentset/errors/unprocessableentityerror.py): The request was well-formed but was unable to be followed due to semantic errors. Status code `422`.
  * [`RateLimitExceededError`](./src/agentset/errors/ratelimitexceedederror.py): The user has sent too many requests in a given amount of time ("rate limiting"). Status code `429`.
  * [`InternalServerError`](./src/agentset/errors/internalservererror.py): The server has encountered a situation it does not know how to handle. Status code `500`.

<details><summary>Less common errors (5)</summary>

<br />

**Network errors:**
* [`httpx.RequestError`](https://www.python-httpx.org/exceptions/#httpx.RequestError): Base class for request errors.
    * [`httpx.ConnectError`](https://www.python-httpx.org/exceptions/#httpx.ConnectError): HTTP client was unable to make a request to a server.
    * [`httpx.TimeoutException`](https://www.python-httpx.org/exceptions/#httpx.TimeoutException): HTTP request timed out.


**Inherit from [`AgentsetError`](./src/agentset/errors/agentseterror.py)**:
* [`ResponseValidationError`](./src/agentset/errors/responsevalidationerror.py): Type mismatch between the response data and the expected Pydantic model. Provides access to the Pydantic validation error via the `cause` attribute.

</details>
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `server_url: str` optional parameter when initializing the SDK client instance. For example:
```python
from agentset import Agentset


with Agentset(
    server_url="https://api.agentset.ai",
    token="AGENTSET_API_KEY",
) as a_client:

    res = a_client.namespaces.list()

    # Handle response
    print(res)

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Python SDK makes API calls using the [httpx](https://www.python-httpx.org/) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with your own HTTP client instance.
Depending on whether you are using the sync or async version of the SDK, you can pass an instance of `HttpClient` or `AsyncHttpClient` respectively, which are Protocol's ensuring that the client has the necessary methods to make API calls.
This allows you to wrap the client with your own custom logic, such as adding custom headers, logging, or error handling, or you can just pass an instance of `httpx.Client` or `httpx.AsyncClient` directly.

For example, you could specify a header for every request that this sdk makes as follows:
```python
from agentset import Agentset
import httpx

http_client = httpx.Client(headers={"x-custom-header": "someValue"})
s = Agentset(client=http_client)
```

or you could wrap the client with your own custom logic:
```python
from agentset import Agentset
from agentset.httpclient import AsyncHttpClient
import httpx

class CustomClient(AsyncHttpClient):
    client: AsyncHttpClient

    def __init__(self, client: AsyncHttpClient):
        self.client = client

    async def send(
        self,
        request: httpx.Request,
        *,
        stream: bool = False,
        auth: Union[
            httpx._types.AuthTypes, httpx._client.UseClientDefault, None
        ] = httpx.USE_CLIENT_DEFAULT,
        follow_redirects: Union[
            bool, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
    ) -> httpx.Response:
        request.headers["Client-Level-Header"] = "added by client"

        return await self.client.send(
            request, stream=stream, auth=auth, follow_redirects=follow_redirects
        )

    def build_request(
        self,
        method: str,
        url: httpx._types.URLTypes,
        *,
        content: Optional[httpx._types.RequestContent] = None,
        data: Optional[httpx._types.RequestData] = None,
        files: Optional[httpx._types.RequestFiles] = None,
        json: Optional[Any] = None,
        params: Optional[httpx._types.QueryParamTypes] = None,
        headers: Optional[httpx._types.HeaderTypes] = None,
        cookies: Optional[httpx._types.CookieTypes] = None,
        timeout: Union[
            httpx._types.TimeoutTypes, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
        extensions: Optional[httpx._types.RequestExtensions] = None,
    ) -> httpx.Request:
        return self.client.build_request(
            method,
            url,
            content=content,
            data=data,
            files=files,
            json=json,
            params=params,
            headers=headers,
            cookies=cookies,
            timeout=timeout,
            extensions=extensions,
        )

s = Agentset(async_client=CustomClient(httpx.AsyncClient()))
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Resource Management [resource-management] -->
## Resource Management

The `Agentset` class implements the context manager protocol and registers a finalizer function to close the underlying sync and async HTTPX clients it uses under the hood. This will close HTTP connections, release memory and free up other resources held by the SDK. In short-lived Python programs and notebooks that make a few SDK method calls, resource management may not be a concern. However, in longer-lived programs, it is beneficial to create a single SDK instance via a [context manager][context-manager] and reuse it across the application.

[context-manager]: https://docs.python.org/3/reference/datamodel.html#context-managers

```python
from agentset import Agentset
def main():

    with Agentset(
        token="AGENTSET_API_KEY",
    ) as a_client:
        # Rest of application here...


# Or when using async:
async def amain():

    async with Agentset(
        token="AGENTSET_API_KEY",
    ) as a_client:
        # Rest of application here...
```
<!-- End Resource Management [resource-management] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass your own logger class directly into your SDK.
```python
from agentset import Agentset
import logging

logging.basicConfig(level=logging.DEBUG)
s = Agentset(debug_logger=logging.getLogger("agentset"))
```

You can also enable a default debug logger by setting an environment variable `AGENTSET_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=agentset&utm_campaign=python)
