# OpenClaw Setup Guide

Personal AI assistant that runs in a sandboxed environment with access to your accounts.

---

## Supported Integrations

### Linear (Issue Tracking)
- CLI: linear
- Auth: Set LINEAR_API_KEY env var
- Team: Created via Linear app

### Todoist (Task Management)
- CLI: todoist
- Auth: Set TODOIST_API_TOKEN env var
- Get token from Todoist > Settings > Integrations

### Obsidian (Knowledge Base)
- CLI: obsidian
- Auth: Set GITHUB_TOKEN env var
- Requires private GitHub repo

### Airtable (Databases)
- API via curl
- Auth: Personal access token from Airtable

### MiniMax (Music Generation)
- Script: python3 /workspace/medieval_music.py
- Auth: Set MINIMAX_API_KEY env var

---

## Sandbox Environment

- OS: Linux (Docker)
- Memory: 3GB
- CPUs: 2
- Network: Full outbound internet
- Writable: /workspace, /tmp

---

## Adding Integrations

1. Create CLI wrapper at /usr/local/bin/TOOLNAME
2. Add env var to openclaw.json docker.env
3. Restart OpenClaw: systemctl restart openclaw
4. Recreate sandbox containers

---

## Sync Setup (Obsidian)

1. Clone your vault repo
2. Open as vault in Obsidian
3. Install obsidian-git plugin
4. Configure:
   - Auto pull: 5 min
   - Auto push: on
   - Pull on startup: on
