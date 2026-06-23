# Tiny Superwhisper Agent

A small Apple Shortcut plus Superwhisper custom prompt that routes dictation into four actions:

- `passthrough`: simple cleaned dictation copied to the clipboard
- `processed`: post-processed AI output copied to the clipboard
- `add_task`: TickTick task creation
- `add_notion_page`: Notion page creation

The shortcut is intentionally generic. It contains no personal Notion workspace, Notion database, TickTick list, API token, or account ID.

## Install

1. Import [`shortcuts/tiny-superwhisper-agent.shortcut`](shortcuts/tiny-superwhisper-agent.shortcut).
2. In Superwhisper, create a custom mode and paste [`docs/superwhisper-custom-prompt.md`](docs/superwhisper-custom-prompt.md).
3. In Shortcuts, open the imported shortcut and select your own:
   - Superwhisper custom mode using that exact prompt
   - TickTick list/project
   - Notion workspace and database

Make sure the Superwhisper action inside the shortcut points to the same custom mode where you pasted this prompt. If it points to another mode, the shortcut will receive the wrong output format.

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

- `passthrough`: copy simple cleaned dictation to clipboard and notify
- `processed`: copy post-processed AI output to clipboard and notify
- `add_task`: create a TickTick task, show `summary`, vibrate
- `add_notion_page`: create a Notion page, copy/open its returned URL, show `summary`, vibrate

## Extending It

The shortcut is a router pattern. To add more actions, add a new JSON `type` to the Superwhisper prompt and a matching `If` branch in Shortcuts. Examples: append to Apple Notes, send a Slack message, create a calendar event, save to a file, call a webhook, or trigger a home automation.

## Notes

The native Notion Shortcuts action treats the body as plain text, not rendered Markdown. The included prompt avoids Markdown-only formatting for Notion body content.

## License

MIT
