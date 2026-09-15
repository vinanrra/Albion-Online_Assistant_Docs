# 🗺️ Avalon Maps

Manage and explore the Roads of Avalon with ease.

## 📜 Map Information

Use the `/ava check` command to retrieve detailed information about a specific map, including:
*   Tier, chests (green, blue, gold), resource enchantment levels (rock, wood, ore, fiber, hide), and static dungeons.
*   The map image if available.

**Usage:** `/ava check map_name:MapName`
*   *Tip:* Supports substring and abbreviation searches (e.g. searching `"FA"` will find `"Fasites-Azazsum"`).

---

## 🛤️ Shortest Route

Find the fastest way between multiple Avalon maps. You can specify a duration and up to 10 maps to include in the route path.

**Usage:** `/ava route hours:2 route1:MapA route2:MapB`
*   **hours:** The active duration of the connection.
*   **route1 - route10:** Maps to include in the route calculation.

---

## 👹 Boss Guides

The bot includes detailed guides for Avalonian Bosses covering mechanics, phases, and recommended builds.

**Usage:** `/ava boss`
*   Select the boss you want to learn about (Constructor, Sacerdotisa, Basilisco, etc.) from the interactive dropdown menu.

---

## 🛠️ Map Editing (Admin Only)

Authorized administrators can update resource levels for Avalon maps to keep them current.

**Usage:** `/ava edit [map_name] [options...]`
*   **map_name:** The map to edit.
*   **green / blue / gold:** Number of chest spawns.
*   **rock / wood / ore / fiber / hide:** Enchantment levels.
*   **dungeon:** Number of static dungeons.
*   *Note:* This command is restricted to Discord user IDs specified in the bot's environment configuration (`ALLOWED_EDIT_IDS`).

---

[⬅️ Back to Home](index.md)
