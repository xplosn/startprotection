**Start Protection** is a simple plugin that gives new users a certain amount of time to play without stressing about being killed by other players, it also prevents them from attacking other players. Players can still be killed by the environment, animals and self-inflicted injuries or turrets, bots. Only PvP is disabled, so player base still could be raided.

Rust is full of griefers, I often read server logs and see several players rage-quit after only playing a few minutes after being gunned down by other players. This gives them a chance to move around a little and set up shop.

## Configuration

```json
{
  "Settings": {
    "bCanPickupWeapons": false,
    "bHelicopterProtection": false,
    "bProtectionEnabled": true,
    "bSleeperProtection": true,
    "bUseRaidZones": false,
    "canLootDrop": false,
    "canLootFriendDeployables": true,
    "canLootFriends": false,
    "canLootHeli": false,
    "iInactiveDays": 1,
    "iPunishment": 600,
    "iTime": 1800,
    "iTimeAssign": 3600,
    "iUpdateTimerInterval": 60,
    "showUIIcon": true,
    "UIFontSize": 16,
    "UIIcon": "https://i.imgur.com/hom6JrH.png",
    "UIIconAnchorMax": "0.290 0.095",
    "UIIconAnchorMin": "0.245 0.025",
    "UIIconFontSize": 16,
    "UILayer": "hud",
    "UISecondsWarningBeforeEnd": 10
  }
}
```

The default time is "1800", which corresponds to 30 minutes. I found this was a fair time.

## Caveats

### A protected player can't loot if the below are configured:

- heli crates
- airdrop
- other players (but if they are friends - can)
- corpses (only own)
- dropped containers, backpacks
- not owned deployables (if are friends - can)

### Damage to anything

Also note that damage to corpses, other players, doors, buildings, external walls, storages, and other deployables not owned will be punished.
Punishment time is "600" by default, which corresponds to 10 minutes. This is the time that will be revoked if the player tries to PvP while in SP mode.

### NoEscape support

If NoEscape is configured with ZoneManager, you can enable "bUseRaidZones", so when SP player enters raid zone - he will loose his protection in some seconds if not exit the zone.
Otherwise, when player turns off his protection or it ends by time, it will end in "UISecondsWarningBeforeEnd" time with effect showing everyone he hasn't any protection now.

## Chat Commands

- `/sp` -- Display all sub-commands and help
- `/sp time` -- Show how much time left
- `/sp end` -- End your protection
- `/sp cleardb` -- Wipe all data

## Console Commands for server/owner

- `sp.assign steamID` -- assign protection for player
- `sp.end steamID` -- manually end protection for player

## Developer API

```csharp
bool HasProtection(BasePlayer player)
```

## Credits

- **Norn**, the original idea of this plugin