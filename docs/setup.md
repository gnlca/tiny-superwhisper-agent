# Setup

## Superwhisper

Create a custom mode and paste `docs/superwhisper-custom-prompt.md` into Custom Instructions. Remember the exact custom mode name.

Suggested settings:

- Preset: Custom
- Language: Automatic
- Realtime: On
- Identify Speakers: Off
- Voice model / LLM: use any reliable setup

## Apple Shortcuts

Import `shortcuts/tiny-superwhisper-agent.shortcut`, then configure the app-specific actions:

- Superwhisper: choose the exact custom mode that uses this prompt.
- TickTick: choose your target list/project, or delete the `add_task` branch.
- Notion: choose your workspace/database, or delete the `add_notion_page` branch.

The Superwhisper action in the shortcut must point to the custom mode that uses this prompt. If it points to a different mode, the shortcut will not receive the expected JSON shape.

## Test Dictations

- `add task buy milk tomorrow at 9`
- `save this note to Notion: the launch checklist needs a rollback step`
- `don't format hello world`

## Extending Routes

The included shortcut currently supports simple dictation, AI post-processing, TickTick task creation, and Notion page creation. You can extend it by adding another `type` to the prompt and another conditional branch in Shortcuts.

## Notion Body Formatting

The native Notion Shortcuts action inserts body text as plain text. It does not parse Markdown into Notion blocks. For real headings, bullets, and code blocks, use the Notion API instead of the native Shortcuts action.
