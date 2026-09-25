# 🌀 Ancient Lands Portal Timers

The Ancient Lands Portal Timers system allows servers to monitor, configure, and display recurring Albion Online Ancient Lands portal spawn schedules across both **Lethal** (Red/Black Zones) and **Non-Lethal** (Yellow Zones).

The system generates two dedicated, high-resolution visual schedule boards (one for **⚔️ Lethal Zones** and one for **🛡️ Non-Lethal Zones**) featuring live countdowns, next spawn times in UTC, and subsequent upcoming timers.

---

## 🖼️ Live Visual Schedule Boards

When configured with `/albion_ancient_lands_portal channel`, the bot posts and automatically maintains two dynamic visual graphic messages in the designated channel:
* **Auto-Refreshing:** Updated in-place every 5 minutes and immediately whenever timers are updated or cleared.
* **Zero Notification Spam:** Edits messages directly without pinging members or posting duplicates.
* **Embed Responses:** Slash commands respond with clean, ephemeral or direct Discord Embeds without attaching bulky image files.

---

## ⏱️ Confirmed vs. Estimated Timers & Cooldown Jitter

Albion Online's Ancient Lands portals feature **anti-camping cooldown jitter (random variance)** between portal spawns (~50 minutes base recurrence with random variance):

* 🟢 **CONFIRMED**: When a scout or player enters the remaining minutes shown in the in-game map tooltip (e.g. `minute:14`), the active cycle until the portal unlocks and closes is tracked as **`CONFIRMED`**.
* 🟡 **ESTIMATED**: Once the confirmed portal cycle closes, subsequent projected cycles are displayed as **`ESTIMATED`** (e.g. `OPENS IN ~25M • ESTIMATED` and `~12:45 UTC`). The timer continues counting down automatically, indicating that the exact spawn moment is subject to game variance until updated by a scout.

---

## 📋 Portal Commands (`/albion_ancient_lands_portal`)

| Command | Parameters | Default Permission* | Description |
| :--- | :--- | :--- | :--- |
| **`/albion_ancient_lands_portal show`** | None | None (Everyone) | Displays a summary embed of current portal timers for both zones and refreshes the live channel graphics. |
| **`/albion_ancient_lands_portal channel`** | `channel` | **Manage Server** | Sets the text channel where live, auto-updating portal schedule graphics are posted and maintained. |
| **`/albion_ancient_lands_portal set`** | `zone`, `type`, `minute` | **Manage Server** | Sets when a portal **OPENS** (unlocks) using the remaining minutes from the in-game map tooltip. |
| **`/albion_ancient_lands_portal config`** | `zone`, `[small_interval]`, `[medium_interval]`, `[big_interval]` | **Manage Server** | Customizes recurrence intervals (in minutes) for portals in a zone without resetting the anchor time. |
| **`/albion_ancient_lands_portal clear`** | `zone`, `event_type` | **Manage Server** | Clears active timer(s) for a specific portal size or all portals in a zone. |

> ℹ️ *\*Commands require the **Manage Server** permission by default, unless configured otherwise by server administrators through Discord's built-in command permissions system (**Server Settings → Integrations → Albion Assistant**).*

---

### Command Details

#### 1. Set Portal Timer
* **Command:** `/albion_ancient_lands_portal set zone:[zone] type:[type] minute:[minute]`
* **Parameters:**
  * `zone`: `⚔️ Lethal` (`lethal`) or `🛡️ Non-Lethal` (`non_lethal`).
  * `type`: `Small`, `Medium`, or `Large`.
  * `minute`: Minutes remaining until the portal unlocks (as seen on the map tooltip).
* *Example:* `/albion_ancient_lands_portal set zone:⚔️ Lethal type:Small minute:14`

#### 2. Configure Recurrence Intervals
* **Command:** `/albion_ancient_lands_portal config zone:[zone] [small_interval] [medium_interval] [big_interval]`
* *Example:* `/albion_ancient_lands_portal config zone:⚔️ Lethal small_interval:50 medium_interval:50 big_interval:50`

#### 3. Clear Timers
* **Command:** `/albion_ancient_lands_portal clear zone:[zone] event_type:[type]`
* *Options for `event_type`:* `Small Portal`, `Medium Portal`, `Large Portal`, or `All Portals`.

---

## 📐 Portal Specifications & Mechanics

The bot's graphics and countdown scheduler adhere to official Albion Online portal timing specifications:

| Portal Size | Group Size & Matchmaking | Lock Time | Entry Window After Unlock | Instance Lifetime |
| :--- | :--- | :--- | :--- | :--- |
| **Small Portal** | 1–5 players *(Pools: solo vs solo, 2–3 vs 2–3, 4–5 vs 4–5)* | 15 minutes | 8 minutes | Normal |
| **Medium Portal** | 5–7 players *(Matched against 5–7)* | 60 minutes | 5 minutes | Normal |
| **Large Portal** | 15–20 players *(Matched against 15–20)* | 180 minutes (3 hours) | 5 minutes | 60 minutes |

* **Reappearance Interval:** Default recurrence interval is ~50 minutes (plus random anti-camping variance).

### ⚔️ Zone & Loot Rules
* **🛡️ Non-Lethal (Yellow Zones):** Takes groups to partial-loot orange-zone Ancient Lands (only inventory dropped on death; 1200 IP soft cap with 20% scaling).
* **⚔️ Lethal (Red & Black Zones):** Takes groups to full-loot Ancient Lands (all gear and inventory dropped on death; 1200 IP soft cap with 35% scaling).

---

[⬅️ Back to Home](index.md)
