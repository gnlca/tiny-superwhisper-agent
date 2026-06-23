# Output Contract

Superwhisper must return exactly one minified JSON object on one physical line.

Allowed shapes:

```json
{"type":"passthrough","data":"..."}
```

```json
{"type":"processed","data":"..."}
```

```json
{"type":"add_task","data":"...","summary":"..."}
```

```json
{"type":"add_notion_page","data":{"title":"...","body":"..."},"summary":"..."}
```

Fields:

- `type`: router mode.
- `data`: final text, TickTick natural-language task, or Notion page data.
- `summary`: short confirmation shown in notifications. Required for `add_task` and `add_notion_page`.

For `add_notion_page`, `data` contains:

- `title`: Notion page title.
- `body`: plain text body. The native Notion Shortcuts action does not render Markdown.
