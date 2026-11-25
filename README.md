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

## Sources

The following 27 sources are included in the bundled OPML manifest. Click a name to open its RSS feed.

- [AGU Advances](https://agupubs.onlinelibrary.wiley.com/feed/2576604x/most-recent)
- [Annual Review of Earth and Planetary Science: Most Recent Articles](https://www.annualreviews.org/rss/content/journals/earth/latestarticles?fmt=rss)
- [Down to Earth Questions](https://downtoearthquestions.blogspot.com/feeds/posts/default?alt=rss)
- [essoar geology](https://essopenarchive.org/action/showFeed?ui=0&mi=3fv225&type=search&feed=rss&query=%2526AllField%253Dgeology%2526content%253Dpreprints)
- [EPSL](https://rss.sciencedirect.com/publication/science/0012821X)
- [ESR](https://rss.sciencedirect.com/publication/science/00128252)
- [Frontiers in Earth Science](https://www.frontiersin.org/journals/earth-science/rss)
- [Geology](https://pubs.geoscienceworld.org/rss/site_65/advanceAccess_33.xml)
- [Geoscience Frontiers](https://rss.sciencedirect.com/publication/science/16749871)
- [Geosphere](https://pubs.geoscienceworld.org/rss/site_67/advanceAccess_34.xml)
- [GGG](https://agupubs.onlinelibrary.wiley.com/action/showFeed?jc=15252027&type=etoc&feed=rss)
- [GRL](https://agupubs.onlinelibrary.wiley.com/action/showFeed?jc=19448007&type=etoc&feed=rss)
- [GSA Bulletin](https://pubs.geoscienceworld.org/rss/site_69/advanceAccess_35.xml)
- [JAES](https://rss.sciencedirect.com/publication/science/13679120)
- [JGR SolidEarth](https://agupubs.onlinelibrary.wiley.com/action/showFeed?jc=21699356&type=etoc&feed=rss)
- [JSG](https://rss.sciencedirect.com/publication/science/01918141)
- [Lithos](https://rss.sciencedirect.com/publication/science/00244937)
- [Lithosphere](https://pubs.geoscienceworld.org/rss/site_71/36.xml)
- [Nature](https://www.nature.com/nature.rss)
- [Nature Geoscience](https://www.nature.com/ngeo.rss)
- [Nature Reviews Earth & Environment](https://www.nature.com/natrevearthenviron.rss)
- [PNAS Earth Sciences](https://www.pnas.org/action/showFeed?type=searchTopic&taxonomyCode=topic&tagCode=earth-sci)
- [Science](https://feeds.science.org/rss/science.xml)
- [Science Advances](https://www.science.org/action/showFeed?type=etoc&feed=rss&jc=sciadv)
- [Speaking of Geoscience](https://speakingofgeoscience.org/feed/)
- [Tectonics](https://agupubs.onlinelibrary.wiley.com/action/showFeed?jc=19449194&type=etoc&feed=rss)
- [Tectonophysics](https://rss.sciencedirect.com/publication/science/00401951)

The OPML is a snapshot. Update it when the subscription list or feed URLs change.
