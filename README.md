# Tiny Superwhisper Agent

A small Apple Shortcut plus Superwhisper custom prompt that routes dictation into:

- cleaned clipboard text
- TickTick tasks
- Notion pages

The shortcut is intentionally generic. It contains no personal Notion workspace, Notion database, TickTick list, API token, or account ID.

## Install

1. Import [`shortcuts/Tiny-Superwhisper-Agent.shortcut`](shortcuts/Tiny-Superwhisper-Agent.shortcut).
2. In Superwhisper, create a custom mode and paste [`docs/superwhisper-custom-prompt.md`](docs/superwhisper-custom-prompt.md).
3. In Shortcuts, open the imported shortcut and select your own:
   - Superwhisper custom mode
   - TickTick list/project
   - Notion workspace and database

Suggested Superwhisper settings:

- Preset: Custom
- Language: Automatic
- Realtime: On
- Identify Speakers: Off
- Voice model / LLM: any reliable transcription and instruction-following setup

## How It Works

Superwhisper returns one JSON object:

```json
{"type":"add_task","data":"Tomorrow at 9 buy milk","summary":"Task added: buy milk tomorrow at nine."}
```

The shortcut reads `type` and routes the result:

- `passthrough` / `processed`: copy text to clipboard and notify
- `add_task`: create a TickTick task, show `summary`, vibrate
- `add_notion_page`: create a Notion page, copy/open its returned URL, show `summary`, vibrate

## Notes

The native Notion Shortcuts action treats the body as plain text, not rendered Markdown. The included prompt avoids Markdown-only formatting for Notion body content.

## License

MIT
