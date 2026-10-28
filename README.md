# osrs-claude-skills

A Claude Code plugin for Old School RuneScape. It connects Claude to [osrs.skunk.to](https://osrs.skunk.to),
a public MCP server with the whole OSRS wiki, a Grand Exchange price history collected every minute and
live hiscores, and adds three skills that use it. No API key and nothing to run locally.

## Install

In Claude Code:

```
/plugin marketplace add dannycake/osrs-claude-skills
/plugin install osrs@osrs-claude-skills
```

## Skills

| Skill | Ask things like |
|---|---|
| `osrs` | "what drops the dragon warhammer", "requirements for Desert Treasure II", "how do I get to Fossil Island" |
| `osrs-setup` | "Barrows setup for &lt;name&gt;", "best ranged gear I can use" |
| `osrs-money` | "find money making methods for &lt;name&gt;", "is tanning green dragonhide still worth it" |

## Only the server

Any MCP client can use `https://osrs.skunk.to/mcp` (Streamable HTTP). In Claude Code without the plugin:

```
claude mcp add --transport http osrs-wiki https://osrs.skunk.to/mcp
```

Tool list and JSON endpoints: [osrs.skunk.to](https://osrs.skunk.to). For agents: [llms.txt](https://osrs.skunk.to/llms.txt).

## Data

- Wiki text: the [Old School RuneScape Wiki](https://oldschool.runescape.wiki), CC BY-NC-SA 3.0.
- GE prices: the [prices.runescape.wiki](https://prices.runescape.wiki) real-time feed.
- Hiscores: Jagex, fetched live.

## Privacy

No accounts, cookies or tracking. The server's log keeps request paths, which include the queries sent to
the JSON endpoints, but not client IP addresses. IPs are used in memory for rate limiting only. MCP tool
calls are not logged beyond the request line.

Skills are MIT licensed. Contact: danny@skunk.pet
