---
name: osrs-setup
description: Build OSRS gear and inventory setups for a specific character from their real hiscores levels and the wiki, with costs from live GE prices. Use for requests like "Zulrah setup for <name>", "what should I wear for Barrows", "best melee gear at my levels".
---

# Gear setups for a character

Uses the `osrs-wiki` MCP server.

1. **Levels.** Take the character name from the request; if there is none, ask once. Call
   `hiscores(<name>)`. A 404 means a wrong name or an unranked character: ask for the levels instead.
   Hiscores carry no quests or bank, so treat quest-locked items as "if you have done X".
2. **Research, in one `batch`.** The activity's strategy page (`"section:Zulrah|Strategies"`,
   `"section:Barrows|Equipment"`), `Armour/Highest bonuses`, the slot tables (`Weapon slot table`,
   `Ammunition slot table`, `Amulet slot table`, `Ring slot table`), and `infobox:` for every candidate
   item's requirements.
3. **Setup.** A table per slot: item, why, requirement, cheaper alternative. Then the inventory (food,
   potions, teleports, switches, with counts), then the levels or quests still missing. Never
   recommend gear above the character's levels.
4. **Cost.** One `batch` of `price:` calls; give the total for the setup and for the budget version.
5. Cite the wiki pages used.
