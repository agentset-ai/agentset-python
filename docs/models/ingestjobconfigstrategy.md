# ~~IngestJobConfigStrategy~~

[Deprecated] Legacy processing strategy used by the previous partition API. This option is ignored by the current pipeline and kept only for backwards compatibility.

> :warning: **DEPRECATED**: We no longer support this option. Use `mode` instead..

## Example Usage

```python
from agentset.models import IngestJobConfigStrategy
value: IngestJobConfigStrategy = "auto"
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `AUTO`     | auto       |
| `FAST`     | fast       |
| `HI_RES`   | hi_res     |
| `OCR_ONLY` | ocr_only   |