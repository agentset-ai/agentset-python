<!-- Start SDK Example Usage [usage] -->
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