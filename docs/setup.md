# Setup

Install and sign in to Superwhisper first. TickTick and Notion are needed only for their respective actions.

## Superwhisper

Create a custom mode named exactly `tiny-superwhisper-agent`, then paste `superwhisper-custom-prompt.md` into Custom Instructions.

Suggested settings:

- Preset: Custom
- Language: Automatic
- Realtime: On
- Identify Speakers: Off
- Voice model / LLM: use any reliable setup

## Apple Shortcuts

Import `tiny-superwhisper-agent.shortcut`, then configure the app-specific actions:

- TickTick: choose your target list/project.
- Notion: choose your workspace/database.

The Superwhisper action is already configured to call `tiny-superwhisper-agent`.

## Test Dictations

- `add task buy milk tomorrow at 9`
- `save this note to Notion: the launch checklist needs a rollback step`

## Extending Routes

The included shortcut currently supports simple dictation, AI post-processing, TickTick task creation, and Notion page creation. You can extend it by adding another `type` to the prompt and another conditional branch in Shortcuts.
