# 🛡️ Albion Killboard Notifications

The Albion Killboard system allows you to receive real-time notifications of kills and deaths for specific **players**, **guilds**, or **alliances** directly in your Discord server.

## 🚀 Setup Guide

To enable killboard notifications, follow these three simple steps:

### 1. Set the Notification Channel
Use the command `/albion_killboard channel` to select the text channel where you want the notifications to be sent.
*   The bot will only send notifications to this channel.
*   Ensure the bot has permissions to `Send Messages` and `Embed Links` in the selected channel.

### 2. Add Entities to Track
Use the command `/albion_killboard add` to start tracking a player, guild, or alliance.
*   **Name**: Enter the name of the entity.
*   **Region**: Select the server region (Americas, Europe, or Asia).
*   **Type**: Choose if you are adding a **Guild** or a **Player**. (Alliances are currently added by name through the Guild search or if explicitly supported in the logic).
*   You can track multiple entities in the same server.

### 3. Verify Your Configuration
Use the command `/albion_killboard status` to see:
*   The current notification channel.
*   The list of all tracked players, guilds, and alliances.
*   The region for each tracked entity.

---

## 🛠️ Management Commands

| Command | Description |
| :--- | :--- |
| **`/albion_killboard status`** | Displays current settings and the list of tracked entities. |
| **`/albion_killboard channel`** | Sets or updates the notification channel. |
| **`/albion_killboard add`** | Adds a new Player or Guild to the tracking list. |
| **`/albion_killboard remove`** | Removes a specific entity from the tracking list. |
| **`/albion_killboard reset`** | Completely clears the configuration (deletes channel and all tracked data). |

---

## ℹ️ How it Works
*   When a kill involves a tracked entity (as a killer or victim), the bot generates a custom notification.
*   Each notification includes a detailed summary of the event, including fame, gear used, and participants.
*   Notifications are sent immediately to your configured channel.

---

[⬅️ Back to Home](index.md)
