# SciFeeds by Source

A shareable [Hermes Agent](https://github.com/NousResearch/hermes-agent) skill that lists recent RSS articles grouped by source.

## What it does

- Uses the SciFeeds MCP to read feeds directly when it is available.
- Includes a portable OPML manifest with 27 RSS sources, so the source list does not depend on a local MCP installation.
- Falls back to Hermes `web_extract` for feeds that fail or return no entries, including blocked ScienceDirect RSS endpoints.
- Filters entries by publication date, deduplicates results, and reports empty or unreadable feeds separately.

## Install in Hermes Agent

Clone this repository into your Hermes skills directory:

```bash
git clone https://github.com/wenrongcao/scifeeds-by-source-en.git \
  "${HERMES_HOME:-$HOME/.hermes}/skills/scifeeds-by-source-en"
```

Start a new Hermes session and ask it to list recent SciFeeds articles, for example:

> List every article from these feeds in the last 30 days, grouped by source.

The SciFeeds MCP is optional. Without it, the skill uses the bundled source manifest and `web_extract` to read RSS feeds. Tool availability can vary by Hermes setup.

## Repository contents

- `SKILL.md` — workflow and output requirements for Hermes Agent.
- `references/sources.opml` — bundled 27-feed source manifest (titles, RSS URLs, and homepages).

The OPML is a snapshot. Update it when the subscription list or feed URLs change.
