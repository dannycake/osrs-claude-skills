---
name: osrs-money
description: Find OSRS money-making methods for a character from live Grand Exchange prices, their levels and game data, documented and undocumented, ranked by gp/hour with effort, requirements and risk. Use for "how can I make money", "best money maker for <name>", "is <method> still profitable".
---

# Money-making for a character

Uses the `osrs-wiki` MCP server, which prices every wiki recipe (about 4,100 conversions), every high
alch and two-step chains against the live GE feed.

1. **Levels.** `hiscores(<name>)`; ask for the name once if it is missing. Ask about preferences only
   when they change the answer (low-click or AFK, no combat, budget).
2. **Scan.** `profit_scan(player=<name>, kind="all", include_documented=true, min_volume=2000, limit=40)`.
   Each row has profit per action, raw gp/h and gp/h capped by the GE buy limit and 24-hour volume.
   `documented_in` names the wiki guide when one exists; rows without it are undocumented finds.
   `kind="chains"` finds raw → intermediate → product margins. The scan does not model quest locks,
   fail chances or Make-X speed, so check those.
3. **Gathering and combat** are not in the scan. Use `search_wiki("Money making guide <activity>")`,
   then `get_section` on the `Money making guide/<name>` pages. Their profit figures date from the
   last edit, so reprice the outputs with `price:` calls.
4. **Verify the top five in one `batch`.** `price:` for every input and output (an item that moved more
   than 20% in `change_7d` is probably a temporary spike), `infobox:` for requirements and quest locks,
   `"section:<item>|Creation"` for the exact recipe.
5. **Answer.** A short table: method, gp/h (capped), effort, what is needed. Then one line per pick on
   why, and what to avoid right now (spikes, thin volume). Say the prices are live as of the answer.
