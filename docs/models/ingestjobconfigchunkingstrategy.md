# ~~IngestJobConfigChunkingStrategy~~

[Deprecated] The legacy chunking strategy. This option is ignored by the current partition pipeline and kept only for backwards compatibility.

> :warning: **DEPRECATED**: We no longer support this option..

## Example Usage

```python
from agentset.models import IngestJobConfigChunkingStrategy
value: IngestJobConfigChunkingStrategy = "basic"
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `BASIC`    | basic      |
| `BY_TITLE` | by_title   |