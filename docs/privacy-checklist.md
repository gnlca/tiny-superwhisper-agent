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

Useful local check if you have an unsigned JSON export:

```sh
rg -i "notion|ticktick|workspace|database|user|token|bearer|secret|your-name|your-email" shortcut.json
```

For signed shortcut exports, also run a string scan:

```sh
strings tiny-superwhisper-agent.shortcut | rg -i "notion|ticktick|token|bearer|secret"
```
