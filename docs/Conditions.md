# Conditions

Conditions let you control who can use a portal. You can combine multiple conditions on a single portal, and the player must meet all of them to teleport.

---

## Setting Conditions

### Set a Condition (replaces any existing condition of that type)

```
/st setcondition <portal> <condition> [value]
```

### Add a Condition (adds alongside existing conditions)

```
/st addcondition <portal> <condition> [value]
```

### Remove a Condition

```
/st removecondition <portal> <condition>
```

### Remove All Conditions

```
/st removecondition <portal> all
```

---

## Available Conditions

### Time of Day

| Condition | Description |
|-----------|-------------|
| `day` | Portal only works during daytime |
| `night` | Portal only works during nighttime |

```
/st setcondition arena day
```

### Weather

| Condition | Description |
|-----------|-------------|
| `rain` | Only during rain |
| `thunder` | Only during thunderstorms |
| `clear` | Only during clear weather |
| `sun` | Daytime with clear weather |
| `storm` | Rain and thunder at the same time |

```
/st setcondition stormgate thunder
```

### Player Level

| Condition | Value | Description |
|-----------|-------|-------------|
| `level` | Number | Minimum XP level required |

```
/st setcondition dungeon level 30
```

### Player State

| Condition | Description |
|-----------|-------------|
| `sneak` | Player must be sneaking |
| `fly` | Player must be flying |

```
/st setcondition secret sneak
```

### Environment

| Condition | Value | Description |
|-----------|-------|-------------|
| `world` | World name | Must be in specific world |
| `biome` | Biome name | Must be in specific biome |
| `gamemode` | Mode name | Must be in specific gamemode |

```
/st setcondition overworldgate world world
/st setcondition junglegate biome JUNGLE
/st setcondition creative_portal gamemode CREATIVE
```

### Items

| Condition | Value | Description |
|-----------|-------|-------------|
| `item` | `<material> [amount]` | Requires specific items in inventory |

```
/st setcondition treasure item DIAMOND 5
```
Requires 5 diamonds in inventory.

```
/st setcondition quest item ENDER_PEARL
```
Requires at least 1 ender pearl.

### Money

| Condition | Value | Description |
|-----------|-------|-------------|
| `money` | Amount | Minimum balance (not charged, just checked) |

```
/st setcondition vipportal money 1000
```
Player must have at least $1,000 in their balance. This does NOT charge them; it only checks. To charge money, use the cost system instead.

### Advancements

| Condition | Value | Description |
|-----------|-------|-------------|
| `advancement` | `namespace:path` | Must have unlocked the advancement |

```
/st setcondition endportal advancement minecraft:story/enter_the_end
```

### Playtime

| Condition | Value | Description |
|-----------|-------|-------------|
| `playtime` | Minutes | Minimum playtime on the server |

```
/st setcondition veterangate playtime 600
```
Requires 10 hours of playtime.

---

## Advanced Conditions (via portals.yml)

Some conditions can only be set by editing `portals.yml` directly or through the interactive management interface:

### Health and Hunger

| Property | Description |
|----------|-------------|
| `minHealth` | Minimum health required (0.0 - 20.0) |
| `maxHealth` | Maximum health allowed |
| `minFood` | Minimum food level required (0 - 20) |
| `maxFood` | Maximum food level allowed |

### Equipment

| Property | Description |
|----------|-------------|
| `requiredArmor` | Armor type required (LEATHER, IRON, DIAMOND, NETHERITE) |
| `requiredWeapon` | Must be holding a weapon |
| `forbiddenItem` | Item that prevents portal use |

### Nearby Players

| Property | Description |
|----------|-------------|
| `minPlayersNearby` | Minimum other players within range |
| `maxPlayersNearby` | Maximum other players within range |

### Time and Date Ranges

| Property | Description |
|----------|-------------|
| `timeRange` | Time window like `06:00-18:00` |
| `dateRange` | Date window like `12-01_12-31` (month-day format) |

### Usage Limits

| Property | Description |
|----------|-------------|
| `maxUsesPerDay` | Maximum uses per day per player |

---

## Combining Conditions

You can stack conditions. The player must meet all of them:

```
/st addcondition boss level 20
/st addcondition boss night
/st addcondition boss item DIAMOND_SWORD 1
```

This portal only works at night, for players level 20 or above, who have a diamond sword.

---

## Interactive Management

The easiest way to manage conditions is through the interactive management interface:

```
/st manage <portal>
```

Click **[Conditions & Requirements]** to see a menu where you can add and remove conditions by clicking buttons in chat. See [Interactive Management](Interactive-Management) for more.

---

## Next Steps

- [Economy](Economy) - Charge money or items to use portals
- [Portal Types](Portal-Types) - Standard, RTP, One-Way
- [Commands and Permissions](Commands-and-Permissions) - Full command list
