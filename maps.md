# 🗺️ Avalon Maps

Manage and explore the Roads of Avalon with ease.

## 📜 Map Information

Use the `/ava check` command to retrieve detailed information about a specific map, featuring a modern grid layout and connection-themed embeds:
*   **Tier & Connection Type:** Displays the map tier and connection category (`👑 Royal`, `💀 Black Zone`, `🌀 Tunnel`, `🏛️ Deep Zone`, or Rest) with dynamic border colors matching zone danger.
*   **Chests:** Color-coded chest counts (🟢 Green, 🔵 Blue, 🟡 Gold).
*   **Resources:** Gathering nodes organized with clear icons (`🪵 Wood`, `🪨 Rock`, `⛏️ Ore`, `🌿 Fiber`, `🐗 Hide`).
*   **Dungeons:** Number of static Avalonian dungeons (`🏰 Avalonian Dungeons`).
*   **Map Graphic:** Displays the high-resolution map image if available.

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

> ℹ️ **Permissions:** Requires your Discord User ID to be defined in the bot's `ALLOWED_EDIT_IDS` configuration. Command visibility and interaction permissions can also be configured or restricted by server administrators through Discord's built-in command permissions system (**Server Settings → Integrations → Albion Assistant**).

---

[⬅️ Back to Home](index.md)
