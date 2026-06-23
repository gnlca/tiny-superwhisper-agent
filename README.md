# Tiny Superwhisper Agent

An Apple Shortcut plus a Superwhisper custom prompt that turns one dictation flow into a tiny action router.

## What It Does

Superwhisper returns a JSON object, and the shortcut routes it into one of four actions:

- `passthrough`: clean dictation and copy it to the clipboard
- `processed`: run AI post-processing and copy the result to the clipboard
- `add_task`: create a TickTick task
- `add_notion_page`: create a Notion page

The shortcut is generic: it contains no personal Notion database, TickTick list, account ID, API token, or private iCloud link.

## Setup In 3 Steps

1. **Create the Superwhisper custom mode**

   Create a custom mode named exactly `tiny-superwhisper-agent`, then paste the prompt from [`docs/superwhisper-custom-prompt.md`](docs/superwhisper-custom-prompt.md).

   Use settings like these:

   ![Superwhisper custom mode settings](assets/sw-config.png)

2. **Install the Apple Shortcut**

   Import [`shortcuts/tiny-superwhisper-agent.shortcut`](shortcuts/tiny-superwhisper-agent.shortcut).

   The first Superwhisper action is already configured to call the custom mode named `tiny-superwhisper-agent`.

3. **Configure TickTick and Notion**

   Open the shortcut in Apple Shortcuts and select your own:

   - TickTick list/project
   - Notion workspace/database

   Delete the TickTick or Notion branch if you do not use that app.

## Extending It

This is a router pattern. To add more actions, add a new JSON `type` to the Superwhisper prompt and a matching `If` branch in Shortcuts.

Examples: append to Apple Notes, send a Slack message, create a calendar event, save to a file, call a webhook, or trigger a home automation.

## Note About Notion

The native Notion Shortcuts action inserts page body content as plain text. It does not render Markdown into native Notion blocks.

## License

MIT
