# /blacklist

The `/blacklist` command in the Albion Online Assistant Discord Bot is designed to manage the blacklist of users, guilds, and alliances. This command has several subcommands, each serving a different purpose. Below is a detailed overview of each subcommand:

## /blacklist add

This command adds a user, guild, or alliance to the blacklist.

| Parameter | Function |
| --- | --- |
| `albion_region`    | The Albion Online server region (choices: East, West). |
| `name`             | The name of the Albion Online user, guild, or alliance to search. |
| `reason`           | Blacklist reason |
| `type`             | Select what are you gonna blacklist user, guild or alliance |
| `albion_id` | The Albion Online ID to blacklist. If provided, the name parameter is ignored. |

## /blacklist remove

This command removes a user, guild, or alliance from the blacklist.

| Parameter | Function |
| --- | --- |
| `albion_region`    | The Albion Online server region (choices: East, West). |
| `name`             | The name of the Albion Online user, guild, or alliance to search. |
| `type`             | Select what are you gonna blacklist user, guild or alliance |
| `albion_id` | The Albion Online ID to blacklist. If provided, the name parameter is ignored. |


## /blacklist show

This command shows information about a blacklisted user, guild, or alliance.

| Parameter | Function |
| --- | --- |
| `albion_region`    | The Albion Online server region (choices: East, West). |
| `name`             | The name of the Albion Online user, guild, or alliance to search. |
| `type`             | Select what are you gonna blacklist user, guild or alliance |
| `albion_id` | The Albion Online ID to blacklist. If provided, the name parameter is ignored. |


## /blacklist list

This command lists all blacklisted users, guilds, and alliances.

| Parameter | Function |
| --- | --- |
| `albion_region`    | The Albion Online server region (choices: East, West). |
| `type`             | Select what are you gonna blacklist user, guild or alliance |
