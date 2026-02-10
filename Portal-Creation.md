# Portal Creation

This page covers everything about creating, connecting, moving and removing portals.

---

## The Portal Wand

Before you can create a portal, you need the selection wand.

```
/st wand
```

The wand is a special item. When you hold it:
- **Left-click** a block to set **Position 1**
- **Right-click** a block to set **Position 2**

These two positions define the opposite corners of your portal area (like how WorldEdit works).

> Both positions must be in the same world.

Once both positions are set, you'll see a message telling you they're ready.

---

## Creating a Portal

With both positions selected:

```
/st add <name>
```

The name must be unique. It's not case-sensitive, so `Spawn` and `spawn` are treated the same.

When the portal is created, you'll see a summary showing:
- The portal name
- Particle type (defaults to DUST)
- Sound (defaults to ENTITY_ENDERMAN_TELEPORT)
- Direction setting
- Orientation (horizontal or vertical)
- The permission assigned to it

### Size Limits

Portal size is limited by config settings:
- Minimum: `1` block per side (default)
- Maximum: `50` blocks per side (default)

You can change these in `config.yml` under `portals.limits`.

### Portal Limits

You can limit how many portals each player can create and how many portals can exist per world. See [Configuration](Configuration).

---

## Connecting Portals

Portals don't do anything until you connect them.

```
/st connect <source> <target>
```

This creates a two-way link. Walking into either portal teleports you to the other.

**Rules:**
- You can't connect a portal to itself
- A portal can only be connected to one other portal at a time
- If a portal is already connected, unlink it first with `/st unlink <portal>`

### Cross-World Connections

Portals can connect across different worlds (Overworld to Nether, etc.) as long as `cross-world` is enabled in config.

---

## Unlinking Portals

```
/st unlink <portal>
```

This disconnects the portal from its target. Both portals still exist, they just aren't linked anymore.

---

## Removing Portals

```
/st remove <portal>
```

This permanently deletes a portal. The blocks in the world stay; only the portal data is removed.

---

## Renaming Portals

```
/st rename <portal> <newname>
```

Changes the portal's name. All connections and settings are kept.

---

## Moving Portals

If you need to relocate a portal without losing its settings:

```
/st move <portal>
```

This enters **move mode**. While in move mode:
1. Use the wand to select two new positions
2. The portal automatically moves to the new location

To cancel:

```
/st move cancel
```

All settings (particles, sounds, costs, connections, conditions) are preserved when moving.

---

## Portal Orientation

The plugin automatically figures out if your portal is vertical or horizontal based on the selection.

**Vertical** portals are standing up like a door or archway. Players walk through them.

**Horizontal** portals are flat on the ground like a floor pad. Players step onto them.

The detection works like this:
- If the height (Y difference) is small (1 block or less) and the width/length is larger, it's horizontal
- Otherwise it's vertical

### Direction Behavior

- **Vertical portals** respect the direction setting. You can make players face North, South, East or West after teleporting.
- **Horizontal portals** always face the player UP after teleporting. Direction overrides are ignored for horizontal portals.

---

## Duplicating Portals

```
/st duplicate <source> <newname>
```

Creates a copy of an existing portal with all its settings. The new portal is placed at your current wand selection.

---

## Resetting a Portal

```
/st reset <portal>
```

Resets all of a portal's settings back to defaults. This clears custom particles, sounds, costs, conditions and more. The portal's position and connections are kept.

---

## Portal Info

```
/st info <portal>
```

Shows detailed information about a portal across multiple pages:
- Status (enabled/disabled)
- World, positions and size
- Connected portal
- Portal type
- Particle settings (type, count, spread, color)
- Sound settings (type, pitch, volume)
- Direction
- Warmup and cooldown
- Safety checks
- Costs
- Conditions
- Permission

Use `/st info <portal> 2` or `/st info <portal> 3` to see more pages.

---

## Listing All Portals

```
/st list
```

Shows every portal with:
- Status indicator (green dot = enabled, red dot = disabled)
- Connection target
- Portal type badges (RTP, Disabled)
- Warmup, cooldown and cost info

---

## Next Steps

- [Portal Types](Portal-Types) - Standard, RTP and One-Way portals
- [Particles and Effects](Particles-and-Effects) - Customize how portals look
- [Commands and Permissions](Commands-and-Permissions) - Full command reference
