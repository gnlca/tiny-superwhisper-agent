# Privacy Checklist

Before publishing a modified shortcut export, inspect it for:

- Notion database IDs
- Notion workspace IDs
- Notion user IDs
- personal names in Notion workspace/user labels
- TickTick project/list IDs
- private iCloud shortcut links
- private Superwhisper mode names
- API keys or bearer tokens

Useful local checks:

```sh
plutil -convert json -o shortcut.json Superwhisper-Agent-Template.shortcut
rg -i "notion|ticktick|workspace|database|user|token|bearer|secret|your-name|your-email" shortcut.json
```

For binary shortcut exports, also run:

```sh
strings Tiny-Superwhisper-Agent.shortcut | rg -i "notion|ticktick|token|bearer|secret"
```
