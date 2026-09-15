# 📊 Player & Guild Statistics

The bot allows you to fetch real-time statistics from the Albion Online API, and compile activity logs based on whitelisted parties and raids hosted on the server.

## 👤 Player Stats

Get detailed info about a player's Kill Fame, Death Fame, PvE progress, and gathering/crafting levels.

*   **Command:** `/albion_stats user [region] [username]`
*   **Comparison:** `/albion_stats compare_user [region] [user1] [user2]` — compares two players side-by-side, highlighting the higher stats.

---

## 🛡️ Guild Stats

Check guild-wide performance, member counts, and kill/death ratios.

*   **Command:** `/albion_stats guild [region] [name]` — displays guild details.
*   **Member List:** `/albion_stats guild_members [region] [name]` — displays a paginated list of members in the guild.
*   **Comparison:** `/albion_stats compare_guild [region] [guild1] [guild2]` — compares two guilds side-by-side.

---

## 🤝 Alliance Stats

Check details and compare statistics for entire alliances.

*   **Command:** `/albion_stats alliance [region] [alliance_id]` — displays alliance details (searches by Alliance ID).
*   **Comparison:** `/albion_stats compare_alliance [region] [alliance1] [alliance2]` — compares two alliances side-by-side.

---

## 📅 Event Statistics & Leaderboards

View stats, leaderboards, and activity analytics based on whitelisted parties and raids hosted by your server's leaders.

*   **Personal Stats:** `/party stats [member]` — shows event counts (attended/hosted), peak activity times, role breakdown, reliability rating, and aggregated PvP performance metrics (kills, deaths, assists, damage, healing, fame, silver) for yourself or a selected member.
*   **Guild Leaderboards:** `/party leaderboard [type] [timeframe]` — displays top hosts or attendees in the server over a specific timeframe (7 days, 30 days, or all time).
*   **Activity Analytics:** `/party analytics [type]` — shows server-wide trends including peak hours (`time`) and role popularity (`roles`).
    *   *Note:* Whitelisted Premium servers automatically receive high-fidelity graphic charts (pie/bar graphs) instead of text summaries.

For more details on how events are tracked, see the **[🎉 Party Management Guide](party.md)**.

---

> ⭐ Use the region selector to ensure you are searching the correct server region (Americas, Europe, or Asia).

---

[⬅️ Back to Home](index.md)
