---
name: osrs
description: Answer any Old School RuneScape (OSRS) question (items, quests, monsters, drop rates, NPCs, skills, training, mechanics, locations, dialogue, Grand Exchange prices) from the full OSRS wiki and live GE data on the osrs-wiki MCP server, citing wiki pages.
---

# OSRS answers from the wiki

The `osrs-wiki` MCP server (https://osrs.skunk.to) holds the whole OSRS wiki (articles and NPC
dialogue transcripts), a Grand Exchange price history collected every minute, and live hiscores.
Answer game facts from it, never from memory: drop rates, requirements and stats change with updates.

## Tools

- `lookup(name)`: start here for one thing. Resolves aliases and returns the infobox and section list,
  plus the GE price and droppers for an item, the drop table for a monster, requirements for a quest.
- `batch(calls)`: up to 25 calls in one request. Shorthand strings work: `"infobox:Zulrah"`,
  `"section:Zulrah|Strategies"`, `"price:Rune pickaxe"`, `"drops:Vorkath"`, `"history:Twisted bow|24h|30"`.
  Use it whenever more than two lookups are needed.
- `search_wiki(query, kind)`: find pages; `kind` = Item, Monster, Npc, Quest, Location, …
- `get_infobox(title)`: exact stats, ids, requirements, max hits.
- `get_section(title, heading)`: one section (Drops, Strategies, Requirements, Creation, Changes);
  much cheaper than `get_page`.
- `get_drops(monster)`, `who_drops(item)`: drop tables with quantity and rarity.
- `ge_price(item)`, `ge_history(item, step, days)`, `ge_movers(hours, direction)`, `ge_ticks(item)`.
- `hiscores(player)`: live levels, XP and boss kill counts.
- `recent_changes(days, kind)`, `wiki_status()`: what changed lately and how current the wiki copy is.

## How to answer

1. One `lookup` or one `batch`; read only the sections the question needs.
2. Lead with the answer, numbers first, and keep it short.
3. Cite page titles, e.g. *(wiki: Abyssal whip)*.
4. If a page is missing, search with other terms; don't guess. If the fact could have changed since the
   date `wiki_status` reports, say so.
5. GE prices: `high` is the instant-buy price, `low` the instant-sell price. Sales pay 2% tax (none
   under 50 gp, capped at 5M, some items exempt). Mention a large 7-day change: spikes often revert.
6. NPC dialogue lives in pages titled `Transcript:<name>`.
