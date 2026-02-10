# Configuration

This page covers every option in `config.yml`. The plugin generates this file on first run.

To apply changes, use `/st reload` in-game or restart the server.

---

## General Settings

```yaml
general:
  debug: false
  auto-save-interval: 5
  message-cooldown: 3000
```

| Option | Default | Description |
|--------|---------|-------------|
| `debug` | `false` | Enable debug logging. Can also be toggled with `/st debug` |
| `auto-save-interval` | `5` | How often portal data is saved, in minutes. Set to `0` to disable |
| `message-cooldown` | `3000` | Minimum time between repeated messages to a player, in milliseconds. Prevents message spam |

---

## Performance Settings

```yaml
performance:
  max-particles-per-tick: 200
  max-particles-per-portal: 500
  nearby-player-radius: 30.0
  adaptive-density: true
  adaptive-density-player-threshold: 15
```

| Option | Default | Description |
|--------|---------|-------------|
| `max-particles-per-tick` | `200` | Maximum particles spawned per tick across all portals. `0` for unlimited |
| `max-particles-per-portal` | `500` | Maximum particles for a single portal. `0` for unlimited |
| `nearby-player-radius` | `30.0` | How close a player needs to be to see particles (blocks) |
| `adaptive-density` | `true` | Automatically reduce particle density when many players are online |
| `adaptive-density-player-threshold` | `15` | Number of online players before density limiting kicks in |

> **Tip:** If you have a busy server with many portals, keep `adaptive-density` enabled. It helps keep TPS stable.

---

## Particle Settings

```yaml
particles:
  enabled: true

  portal:
    particle: "DUST"
    count: 8
    spread: 0.3
    volumetric-rendering: true

  teleport:
    particle: "ENCHANTMENT_TABLE"
    count: 30

  selection:
    particle: "END_ROD"
    count: 1
    interval: 20
    spread: 0.2
```

### Global Particle Toggle

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `true` | Turn all particle effects on or off |

### Portal Particles (defaults for new portals)

| Option | Default | Description |
|--------|---------|-------------|
| `particle` | `DUST` | Default particle type for new portals |
| `count` | `8` | Number of particles per display cycle |
| `spread` | `0.3` | How spread out the particles are. `0.0` is tight, `1.0` is wide |
| `volumetric-rendering` | `true` | Fill the entire portal area with particles in 3D |

### Teleport Particles

| Option | Default | Description |
|--------|---------|-------------|
| `particle` | `ENCHANTMENT_TABLE` | Particle shown when a player teleports |
| `count` | `30` | Number of teleport particles |

### Selection Particles

| Option | Default | Description |
|--------|---------|-------------|
| `particle` | `END_ROD` | Particle at wand selection points |
| `count` | `1` | Number of selection particles |
| `interval` | `20` | Display interval in ticks (20 ticks = 1 second) |
| `spread` | `0.2` | Spread for selection markers |

> Each portal can override these defaults. Use `/st setparticle`, `/st setcount`, `/st setspread`, etc.

---

## Portal Mechanics

```yaml
portals:
  limits:
    max-portals-per-player: 0
    max-portals-per-world: 0
    max-size: 50
    min-size: 1

  teleportation:
    preserve-orientation: true
    auto-adjust-destination: true
```

### Limits

| Option | Default | Description |
|--------|---------|-------------|
| `max-portals-per-player` | `0` | Max portals a player can create. `0` for unlimited. Bypass with `st.portal.limit.bypass` |
| `max-portals-per-world` | `0` | Max portals in a single world. `0` for unlimited |
| `max-size` | `50` | Maximum portal size in blocks per side |
| `min-size` | `1` | Minimum portal size in blocks per side |

### Teleportation

| Option | Default | Description |
|--------|---------|-------------|
| `preserve-orientation` | `true` | Keep the player's current camera direction after teleporting |
| `auto-adjust-destination` | `true` | If the destination is blocked, try to find a nearby safe spot |

---

## Player Settings

```yaml
players:
  permissions:
    per-portal-permissions: true
```

| Option | Default | Description |
|--------|---------|-------------|
| `per-portal-permissions` | `true` | When enabled, each portal gets its own permission node like `st.portal.use.<name>` |

---

## Safety Settings

```yaml
safety:
  safe-teleport: true
  cross-world: true
  enhanced-safety: true
  safe-search-radius: 10
  prevent-dangerous-creation: true
```

| Option | Default | Description |
|--------|---------|-------------|
| `safe-teleport` | `true` | Check if the destination is safe before teleporting |
| `cross-world` | `true` | Allow portals to connect across different worlds |
| `enhanced-safety` | `true` | Additional safety checks (lava, fire, void, etc.) |
| `safe-search-radius` | `10` | How many blocks to search for a safe landing spot |
| `prevent-dangerous-creation` | `true` | Block portal creation in dangerous areas |

> You can disable safety checks on individual portals with `/st setdisablesafecheck <portal>`.

---

## Random Teleport (RTP) Settings

```yaml
rtp:
  preload:
    enabled: true
    radius: 1
    timeout: 5000
    allow-new-chunk-generation: true

  cooldown:
    enabled: true
    time: 60

  retry:
    max-attempts: 10
    retry-delay: 100
```

### Chunk Preloading

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `true` | Preload chunks at the destination before teleporting |
| `radius` | `1` | Chunk radius to preload. `1` loads a 3x3 area (9 chunks) |
| `timeout` | `5000` | Max wait time for chunks to load, in milliseconds |
| `allow-new-chunk-generation` | `true` | Allow generating brand new chunks |

### Cooldown

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `true` | Enable cooldown for RTP portals |
| `time` | `60` | Cooldown in seconds between uses |

### Retry

| Option | Default | Description |
|--------|---------|-------------|
| `max-attempts` | `10` | How many times to try finding a safe random location |
| `retry-delay` | `100` | Delay between retry attempts in milliseconds |

---

## Portal Protection

```yaml
protection:
  enabled: true
  radius: 2
  protect-frame: true
  bypass-permission: "st.protection.bypass"
```

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `true` | Protect blocks around portals from being broken or placed |
| `radius` | `2` | Protection radius in blocks around the portal |
| `protect-frame` | `true` | Also protect the frame blocks of the portal |
| `bypass-permission` | `st.protection.bypass` | Permission node to bypass protection |

---

## Economy Settings

```yaml
economy:
  enabled: true
  currency-format: "$%.2f"
  payment-timing: "before"
  refund-on-failure: true
```

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `true` | Enable Vault economy integration |
| `currency-format` | `$%.2f` | How money amounts are displayed |
| `payment-timing` | `before` | Take payment `before` or `after` teleportation |
| `refund-on-failure` | `true` | Give money back if the teleport fails |

> Requires **Vault** and an economy plugin like EssentialsX installed on the server.

---

## Integration Settings

```yaml
integrations:
  maps:
    enabled: false
    show-destination: true
    show-status: true
    portal-icon: "portal"

  worldguard:
    enabled: false
    require-build-permission: true
    check-teleport-permission: true
    respect-claims-rtp: true

  lands:
    enabled: false
    respect-claims-rtp: true
    require-land-permission: true

  griefprevention:
    enabled: false
    respect-claims-rtp: true
    require-build-permission: true
```

### Map Integration (Dynmap / BlueMap)

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `false` | Show portals as markers on web maps |
| `show-destination` | `true` | Display destination info in marker popup |
| `show-status` | `true` | Show enabled/disabled status on map |
| `portal-icon` | `portal` | Icon name for the map marker |

### WorldGuard

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `false` | Respect WorldGuard regions |
| `require-build-permission` | `true` | Require build permission in region to create portals |
| `check-teleport-permission` | `true` | Check if player can teleport within the region |
| `respect-claims-rtp` | `true` | Avoid RTP landing inside claimed regions |

### Lands

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `false` | Respect Lands claims |
| `respect-claims-rtp` | `true` | Avoid RTP landing inside land claims |
| `require-land-permission` | `true` | Need permission to create portals in claimed land |

### GriefPrevention

| Option | Default | Description |
|--------|---------|-------------|
| `enabled` | `false` | Respect GriefPrevention claims |
| `respect-claims-rtp` | `true` | Avoid RTP landing inside claims |
| `require-build-permission` | `true` | Need build trust in claim to create portals |

---

## Next Steps

- [Particles and Effects](Particles-and-Effects.mdParticles-and-Effects) - Customize portal visuals
- [Conditions](Conditions.mdConditions) - Set usage requirements
- [Default Config Files](Default-Config-Files.mdDefault-Config-Files) - See the full default files

