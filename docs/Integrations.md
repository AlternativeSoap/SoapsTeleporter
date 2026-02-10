# Integrations

SoapsTeleporter works with several popular plugins. All integrations are optional and disabled by default.

---

## PlaceholderAPI

If PlaceholderAPI is installed, the plugin registers placeholders you can use in scoreboards, chat plugins, holograms and more.

### Portal Placeholders

| Placeholder | Returns |
|-------------|---------|
| `%soapsteleporter_portals_count%` | Total number of portals |
| `%soapsteleporter_portals_connected%` | Number of connected portals |
| `%soapsteleporter_portals_nearest%` | Name of the nearest portal |
| `%soapsteleporter_portals_nearest_distance%` | Distance to the nearest portal |

### Player Placeholders

| Placeholder | Returns |
|-------------|---------|
| `%soapsteleporter_player_teleports%` | Total teleports by this player |
| `%soapsteleporter_player_portals_created%` | Portals created by this player |
| `%soapsteleporter_player_last_portal%` | Last portal the player used |
| `%soapsteleporter_player_cooldown%` | Remaining cooldown in seconds |

### Economy Placeholders

| Placeholder | Returns |
|-------------|---------|
| `%soapsteleporter_economy_balance%` | Player's current balance |
| `%soapsteleporter_economy_spent%` | Total money spent on portals |

### Stats Placeholders

| Placeholder | Returns |
|-------------|---------|
| `%soapsteleporter_stats_server_teleports%` | Total teleports server-wide |
| `%soapsteleporter_stats_most_used_portal%` | Name of the most used portal |

### Setup

No extra setup needed. If PlaceholderAPI is installed, placeholders register automatically on startup. You'll see this in the console:

```
[OK] PlaceholderAPI integration enabled!
```

---

## Vault (Economy)

Required for money-based portal costs.

### What you need

1. [Vault](https://www.spigotmc.org/resources/vault.34315/) plugin
2. An economy plugin compatible with Vault (EssentialsX, CMI, etc.)

### Config

```yaml
economy:
  enabled: true
  currency-format: "$%.2f"
  payment-timing: "before"
  refund-on-failure: true
```

### What it enables

- Charge money to use portals (`/st setcost <portal> <amount>`)
- Display player balance via PlaceholderAPI
- Money condition checks (`/st setcondition <portal> money <amount>`)
- Refunds when teleportation fails

---

## WorldGuard

Prevents portals from being created or used in protected regions.

### Config

```yaml
integrations:
  worldguard:
    enabled: false
    require-build-permission: true
    check-teleport-permission: true
    respect-claims-rtp: true
```

| Option | Description |
|--------|-------------|
| `require-build-permission` | Players need build access in a region to create portals there |
| `check-teleport-permission` | Check if the player is allowed to teleport within the region |
| `respect-claims-rtp` | RTP won't land players inside protected regions |

---

## Lands

Integrates with the Lands plugin for land claim support.

### Config

```yaml
integrations:
  lands:
    enabled: false
    respect-claims-rtp: true
    require-land-permission: true
```

| Option | Description |
|--------|-------------|
| `respect-claims-rtp` | RTP won't land players inside land claims |
| `require-land-permission` | Need permission in the land area to create portals |

---

## GriefPrevention

Integrates with GriefPrevention for claim protection.

### Config

```yaml
integrations:
  griefprevention:
    enabled: false
    respect-claims-rtp: true
    require-build-permission: true
```

| Option | Description |
|--------|-------------|
| `respect-claims-rtp` | RTP won't land players inside claims |
| `require-build-permission` | Need build trust in a claim to create portals there |

---

## Dynmap and BlueMap

Show portals as markers on your web map.

### Config

```yaml
integrations:
  maps:
    enabled: false
    show-destination: true
    show-status: true
    portal-icon: "portal"
```

| Option | Description |
|--------|-------------|
| `show-destination` | Show where the portal connects to in the marker popup |
| `show-status` | Display enabled/disabled status on the map |
| `portal-icon` | Icon name for the marker |

Both Dynmap and BlueMap are supported. The plugin detects which one is installed and uses it automatically.

---

## Soft Dependencies

These are all **optional**. The plugin works fine without any of them:

| Plugin | Purpose |
|--------|---------|
| PlaceholderAPI | Custom placeholders |
| Vault | Economy support |
| WorldGuard | Region protection |
| Lands | Land claim integration |
| GriefPrevention | Claim protection |
| Dynmap | Web map markers |
| BlueMap | Web map markers |

---

## Next Steps

- [Configuration](Configuration) - All config options
- [Commands and Permissions](Commands-and-Permissions) - Full command reference
- [Examples](Examples) - Real setup examples
