# 📊 Player & Guild Statistics

The bot allows you to fetch real-time statistics from the Albion Online API, and compile activity logs based on whitelisted parties and raids hosted on the server.

## 👤 Player Stats

Get detailed info about a player's Kill Fame, Death Fame, PvE progress, gathering/crafting levels, external killboard links, and estimated PvP profit & loss.

*   **Command:** `/albion_stats user [region] [username]` — displays comprehensive player statistics including fame breakdowns, guild details, external killboard links, and estimated PvP profit & loss.
*   **Comparison:** `/albion_stats compare_user [region] [user1] [user2]` — compares two players side-by-side, highlighting the higher stats.

### 💰 Estimated Profit & Loss (PvP)
The `/albion_stats user` embed includes a dedicated **Estimated Profit & Loss (PvP)** tracker:
*   **Timeframes:** Audits player combat activity across **Today**, **Yesterday**, **Last 7 Days**, and **Lifetime**.
*   **Net Silver Indicators:** Clearly displays net silver balance with visual status badges (🟢 positive gain, 🔴 net loss, ⚪ even).
*   **Detailed Breakdown:** Shows gross profit (`📈 Profit: +X`), equipment loss (`📉 Loss: -Y`), and combat records (`⚔️ X kills, Y assists, Z deaths`).
*   **Market Price Valuation:** Integrated with real-time market data from the **Albion Online Data Project**, protected by a 7-day database pricing cache and rate-limit fallbacks to value kills and deaths accurately.

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
