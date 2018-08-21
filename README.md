# Start Protection

Start Protection is a simple plugin that gives new users a certain amount of time to play without stressing about being killed by other players, 
it also prevents them from attacking other players. Players can still be killed by the environment, animals and self-inflicted injuries. Only PvP is disabled, so player base still could be raided.

### Why?

Rust is full of griefers, I often read server logs and see several players rage-quit after only playing a few minutes after being gunned down by other players. 
This gives them a chance to move around a little and set up shop.

### Configuration

```
{
  "bHelicopterProtection": false,
  "bProtectionEnabled": true,
  "bSleeperProtection": true,
  "canLootFriends": false,
  "canLootFriendDeployables": true,
  "iInactiveDays": 1,
  "iPunishment": 600,
  "iTime": 1800,
  "iUpdateTimerInterval": 10,
  "canLootHeli": false,
  "canLootDrop": false,
    "showUIIcon": true,
    "UIIcon": "https://i.imgur.com/hom6JrH.png",
    "UIIconAnchorMax": "0.290 0.095",
    "UIIconAnchorMin": "0.245 0.025"
}
```

The default time is "1800", which corresponds to 30 minutes. I found this was a fair time.

### Currently StartProtected player can't loot, if configured:

- heli crates
- airdrop
- other players (but if are friends - can, if configured)
- corpses (can only own)
- dropped containers, backpacks
- not owned deployables (if are friends - can, if configured)

### Currently punishing for damaging any:

corpses, other players, doors, buildings, external walls, storages, other deployables not owned

Punishment time is "600" by default, which corresponds to 5 minutes. This is the time that will be revoked if the player tries to PvP while in SP mode.
And repeat

### API

```
object HasProtection(BasePlayer player)
```

End with an example of getting some data out of the system or using it for a little demo

### Commands

/sp (Will display all the sub-commands)
/sp time (how much time left)
/sp end (end your protection)
/sp cleardb (wipes data) 