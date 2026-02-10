# Particles and Effects

Every portal can have its own particle effect, sound, direction and timing. This page covers all the visual and audio customization options.

---

## Particle Effects

### Setting a Particle

```
/st setparticle <portal> <particle>
```

You can use any Minecraft particle type. Some popular ones:

| Particle | Look |
|----------|------|
| `DUST` | Colored dust (default). Supports custom RGB colors |
| `FLAME` | Fire particles |
| `SOUL_FIRE_FLAME` | Blue fire |
| `END_ROD` | Small white sparkles |
| `PORTAL` | Swirling purple particles |
| `ENCHANTMENT_TABLE` | Floating enchantment symbols |
| `HEART` | Floating hearts |
| `HAPPY_VILLAGER` | Green sparkles |
| `DRAGON_BREATH` | Purple dragon breath |
| `FIREWORKS_SPARK` | White sparks |
| `CRIT` | Critical hit stars |
| `SMOKE_NORMAL` | Light smoke |

Use tab completion in-game to see all available particles.

### Resetting to Default

```
/st setparticle <portal> DEFAULT
```

---

## DUST Particle Colors

When using the `DUST` particle, you can set a custom color:

```
/st setcolor <portal> <red> <green> <blue>
```

Values range from `0` to `255`.

### Examples

```
/st setcolor spawn 255 0 0
```
Red portal.

```
/st setcolor nether 255 165 0
```
Orange portal.

```
/st setcolor ocean 0 100 255
```
Blue portal.

> Color only works with the `DUST` particle type. Other particles use their built-in colors.

---

## Particle Count

```
/st setcount <portal> <count>
```

Controls how many particles appear per display cycle. Higher values make the portal look denser.

```
/st setcount spawn 30
```

---

## Particle Spread

```
/st setspread <portal> <tight> <wide>
```

Controls how the particles are distributed:
- **Tight** value = minimum spread (closer together)
- **Wide** value = maximum spread (further apart)

```
/st setspread spawn 0.1 0.5
```

A tight spread makes particles cluster in the center. A wide spread fills more area.

> Tight must be less than or equal to wide.

---

## Display Interval

```
/st setinterval <portal> <ticks>
```

How often particles are refreshed, in server ticks (20 ticks = 1 second).

```
/st setinterval spawn 10
```

Lower values = more frequent updates = smoother animation but more server load.

> Very low intervals (below 5) can impact performance on busy servers.

---

## Volumetric Rendering

When enabled in config (`volumetric-rendering: true`), particles fill the entire 3D space of the portal instead of just the edges. This is enabled by default and applies globally.

---

## Sounds

### Setting a Sound

```
/st setsound <portal> <sound> [volume] [pitch]
```

You can use any Minecraft sound. Some common ones:

| Sound | Description |
|-------|-------------|
| `ENTITY_ENDERMAN_TELEPORT` | Classic enderman teleport (default) |
| `BLOCK_PORTAL_TRIGGER` | Nether portal sound |
| `BLOCK_PORTAL_AMBIENT` | Nether portal ambient loop |
| `ENTITY_PLAYER_LEVELUP` | Level up chime |
| `BLOCK_BEACON_ACTIVATE` | Beacon activation |
| `BLOCK_ENCHANTMENT_TABLE_USE` | Enchanting table sound |

Use tab completion for the full list.

### Volume and Pitch

| Parameter | Range | Default | Description |
|-----------|-------|---------|-------------|
| Volume | `0.0` - `2.0` | `1.0` | How loud the sound is |
| Pitch | `0.0` - `2.0` | `1.0` | Sound pitch. Lower = deeper, Higher = squeakier |

### Examples

```
/st setsound spawn ENTITY_ENDERMAN_TELEPORT
```
Default sound with default pitch and volume.

```
/st setsound spawn ENTITY_ENDERMAN_TELEPORT 1.2 0.5
```
Slightly louder, lower pitch.

### Disabling Sound

```
/st setsound <portal> NONE
```

### Resetting to Default

```
/st setsound <portal> DEFAULT
```

When you set a sound, you'll hear a preview so you know what it sounds like.

---

## Teleport Direction

```
/st setdirection <portal> <direction>
```

Controls which direction the player faces after teleporting.

| Direction | Effect |
|-----------|--------|
| `NORTH` | Player faces North |
| `SOUTH` | Player faces South |
| `EAST` | Player faces East |
| `WEST` | Player faces West |
| `UP` | Player looks up |
| `DOWN` | Player looks down |
| `PLAYER` | Preserves the player's current facing direction |
| `NONE` | Same as PLAYER, no override |
| `DEFAULT` | Uses plugin default (preserves direction) |

### Horizontal Portals

Horizontal (floor) portals always face the player UP after teleporting, regardless of the direction setting. This is by design - stepping onto a floor portal and looking up makes the most sense.

---

## Warmup and Cooldown

### Warmup

```
/st setwarmup <portal> <seconds>
```

Adds a delay before teleportation. The player must stand still during the warmup. If they move, the teleport is cancelled.

```
/st setwarmup spawn 5
```
5 second warmup. Players see a countdown.

Set to `0` to disable.

> Players with `st.portal.bypass.warmup` skip the warmup.

### Cooldown

```
/st setcooldown <portal> <seconds>
```

Time a player must wait between uses of a portal.

```
/st setcooldown spawn 30
```
30 second cooldown between uses.

Set to `0` to disable.

> Players with `st.portal.bypass.cooldown` skip the cooldown.

---

## Safety Checks

```
/st setdisablesafecheck <portal>
```

Toggles safety checking for a specific portal. When safety checks are on (default), the plugin verifies the destination is safe before teleporting. When off, players teleport regardless.

Useful for adventure maps or specific setups where you want to teleport into unusual areas.

---

## Next Steps

- [Conditions](Conditions) - Set who can use a portal
- [Economy](Economy) - Charge for portal use
- [Interactive Management](Interactive-Management) - GUI for managing all settings
