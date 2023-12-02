# /alliance

The /alliance command is used for managing alliances in your Discord bot. It includes several subcommands:

## /alliance add

This command allows admins to add an alliance to the bot's configuration, specifying the region, alliance ID, role, and tag.

### Usage:

`/alliance add [region] [alliance_id] [alliance_role] [alliance_tag]`

| Parameter | Function |
| --- | --- |
| `region`           | The Albion Online server region                                                           |
| `albionAllianceId` | The unique ID of the alliance in Albion Online, you can get this from [AlbionKillboard](https://albiononline.com/killboard) |
| `allianceRole`     | The Discord role associated with this alliance.                                           |
| `allianceTag`      | The tag of the alliance (maximum 7 characters).                                           |

## /alliance remove

This command is used to remove an alliance from the bot's configuration. It requires the region and alliance ID.

### Usage:

`/alliance remove [region] [alliance_id]`

| Parameter | Function |
| --- | --- |
| `region`           | The Albion Online server region                                                           |
| `albionAllianceId` | The unique ID of the alliance in Albion Online, you can get this from [AlbionKillboard](https://albiononline.com/killboard) |


## /alliance show

### Usage:

`/alliance show [region] [alliance_id]`

This command displays the details of a specific alliance, including its ID, name, role, and tag.

| Parameter | Function |
| --- | --- |
| `region`           | The Albion Online server region                                                           |
| `albionAllianceId`| The unique ID of the alliance in Albion Online, you can get this from [AlbionKillboard](https://albiononline.com/killboard) |


## /alliance list

This command lists all alliances that have been configured in the bot, showing their names and IDs.

### Usage:

`/alliance list [region]`
