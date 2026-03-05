# IngestJobStatus

The status of the ingest job.

## Example Usage

```python
from agentset.models import IngestJobStatus
value: IngestJobStatus = "BACKLOG"
```


## Values

| Name                | Value               |
| ------------------- | ------------------- |
| `BACKLOG`           | BACKLOG             |
| `QUEUED`            | QUEUED              |
| `QUEUED_FOR_RESYNC` | QUEUED_FOR_RESYNC   |
| `QUEUED_FOR_DELETE` | QUEUED_FOR_DELETE   |
| `PRE_PROCESSING`    | PRE_PROCESSING      |
| `PROCESSING`        | PROCESSING          |
| `DELETING`          | DELETING            |
| `CANCELLING`        | CANCELLING          |
| `COMPLETED`         | COMPLETED           |
| `FAILED`            | FAILED              |
| `CANCELLED`         | CANCELLED           |