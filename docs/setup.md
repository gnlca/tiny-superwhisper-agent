# Setup

## Superwhisper

Create a custom mode and paste `docs/superwhisper-custom-prompt.md` into Custom Instructions.

Suggested settings:

- Preset: Custom
- Language: Automatic
- Realtime: On
- Identify Speakers: Off
- Voice model / LLM: use any reliable setup

## Apple Shortcuts

Import `shortcuts/Tiny-Superwhisper-Agent.shortcut`, then configure the app-specific actions:

- Superwhisper: choose your custom mode.
- TickTick: choose your target list/project, or delete the `add_task` branch.
- Notion: choose your workspace/database, or delete the `add_notion_page` branch.

## Test Dictations

- `add task buy milk tomorrow at 9`
- `save this note to Notion: the launch checklist needs a rollback step`
- `don't format hello world`

## Notion Body Formatting

The native Notion Shortcuts action inserts body text as plain text. It does not parse Markdown into Notion blocks. For real headings, bullets, and code blocks, use the Notion API instead of the native Shortcuts action.
