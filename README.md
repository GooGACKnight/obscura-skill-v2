# obscura-skill-v2

`obscura` skill for OpenClaw / Kilo Code — remote headless browser agent skill.

## What

**Obscura** is an ultra-lightweight headless browser (~30MB RAM) for AI agents.
Auto-detects QR login pages and renders QR to terminal.

## File Structure

```
obscura-skill-v2/
├── README.md          ← this file
└── skills/
    └── obscura/
        └── SKILL.md   ← skill content
```

## Usage (OpenClaw / Kilo-safe)

The skill requires `obscura` Docker to be running:

```bash
docker run -d --name obscura -p 127.0.0.1:9222:9222 h4ckf0r0day/obscura
```

```bash
# Fetch a page
docker exec obscura /obscura fetch https://example.com --dump html

# Scrape with JS eval
docker exec obscura /obscura scrape https://news.ycombinator.com --eval "document.title"
```

## Install

Source skill from GitHub in your `kilo.jsonc` / `openclaw.json`:

```jsonc
{
  "skills": {
    "urls": ["https://raw.githubusercontent.com/GooGACKnight/obscura-skill-v2/main/skills/obscura/"]
  }
}
```

Or drop `skills/obscura/SKILL.md` into your local OpenClaw/Kilo skills path.
