# 🛡️ Item Power Caps & Scaling Commands

The Albion Bot provides comprehensive tools to inspect Item Power (IP) soft caps, scaling penalties, minimum IP requirements, group sizes, and lethality rules across all Albion Online PvP and PvE activities.

Data is extracted directly from the official game binaries (`ao-bin-dumps`), covering **The Depths**, **Dragon Lands / Ancient Lands**, **Corrupted Dungeons**, **Hellgates**, **Crystal Arena & Crystal League**, **The Mists**, and **Open World**.

---

## 🔍 Commands Overview

### 1. View Activity Cap & Rules: `/albion_caps info [activity]`
Displays the complete reference guide for an activity, including:
* **Min Required IP**: Minimum Item Power needed to participate or enter.
* **IP Soft Cap**: Point at which surplus IP begins to scale down.
* **Scaling Penalty**: The percentage reduction applied to surplus IP (e.g. 80% penalty for a 0.2 scaling factor).
* **Zone & Lethality**: Safe (Blue), Yellow (Knockdown), Orange (Inventory Drop), or Black (Full Loot).
* **Party Size**: Required or supported group size.
* **Special Mechanics**: Portals, Infamy bonuses, Soul extraction, and Vault rules.
* **Interactive Selector**: Switch between activities on the fly using the built-in dropdown menu.

### 2. Calculate Effective IP: `/albion_caps calculate [current_ip] [activity]`
Calculates your exact effective Item Power after soft cap scaling is applied to your build.

#### Example Calculation:
Entering Stalker Corrupted Dungeons with **1500 raw IP**:
* **Soft Cap**: 1000 IP
* **Surplus IP**: +500 IP
* **Scaling Factor**: 0.2 (80% reduction)
* **Scaled Surplus Retained**: +100 IP
* **IP Lost to Penalty**: -400 IP
* **Effective Item Power**: **1100 IP**

---

[⬅️ Back to Home](index.md)

