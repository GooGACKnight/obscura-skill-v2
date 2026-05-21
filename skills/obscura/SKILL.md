---
name: obscura
description: "Ultra-lightweight headless browser (~30MB RAM) for AI agents - auto QR terminal login when needed."
metadata: { "openclaw": { "emoji": "🕵️" } }
---

# Obscura Browser

Default headless browser. Auto-detects QR login pages and renders QR to terminal.

## Auto QR Login

When agent detects QR login pages, it automatically:
1. Captures QR code (canvas/img)
2. Renders QR to terminal with `qrencode` or base64
3. Prompts: "Please scan QR code to authorize login"

## Direct Fetch

```bash
# Simple fetch
docker exec obscura /obscura fetch https://example.com --dump html

# Multiple pages  
docker exec obscura /obscura scrape https://news.ycombinator.com --eval "document.title"
```

## Install

```bash
docker run -d --name obscura -p 127.0.0.1:9222:9222 h4ckf0r0day/obscura
```