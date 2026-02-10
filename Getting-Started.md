# Getting Started

This page walks you through installing SoapsTeleporter and creating your first portal pair.

---

## Requirements

| Requirement | Details |
|-------------|---------|
| Server | Paper or Folia 1.21+ |
| Java | Java 21 or newer |
| Optional | Vault + economy plugin for costs |
| Optional | PlaceholderAPI for placeholders |

---

## Installation

1. Download `SoapsTeleporter.jar`
2. Drop it into your server's `plugins/` folder
3. Start or restart the server
4. The plugin will generate its config files automatically

You should see something like this in the console:

```
Plugin Loaded: SoapsTeleporter v1.0.0
Created by AlternativeSoap
```

---

## Your First Portal

### Step 1: Get the Wand

```
/st wand
```

You'll receive a **Portal Wand** item. This is what you use to select the area for your portal.

### Step 2: Select Two Corners

**Left-click** a block to set position 1.
**Right-click** a block to set position 2.

These two positions define the corners of your portal. The portal can be any rectangular size.

> **Tip:** Both positions must be in the same world.

### Step 3: Create the Portal

```
/st add spawn
```

Replace `spawn` with whatever you want to name your portal. Names are not case-sensitive.

You'll see a confirmation message showing the portal's particle type, sound, direction and orientation.

### Step 4: Create a Second Portal

Repeat steps 2 and 3 to create another portal somewhere else:

```
/st add market
```

### Step 5: Connect Them

```
/st connect spawn market
```

This links the two portals together. Walking into `spawn` will teleport you to `market`, and walking into `market` will teleport you to `spawn`.

---

## Verify It Works

Walk into one of your portals. You should:
- See particles at the portal
- Hear the teleport sound
- Appear at the other portal

If something seems off, run the self-test:

```
/st debug selftest
```

This checks your config files, portal data, particle system and permissions.

---

## Portal Orientation

The plugin automatically detects if your portal is **horizontal** (like a floor pad) or **vertical** (like a doorway).

- **Vertical portals** work like doors. Walk through them.
- **Horizontal portals** work like floor pads. Step on them.

This is detected from the shape of your selection. If it's flat on the ground (1 block tall), it's horizontal. Otherwise it's vertical.

---

## Basic Commands to Know

| Command | What it does |
|---------|-------------|
| `/st wand` | Get the selection wand |
| `/st add <name>` | Create a portal from your selection |
| `/st connect <a> <b>` | Link two portals |
| `/st list` | Show all portals |
| `/st info <name>` | Show portal details |
| `/st remove <name>` | Delete a portal |
| `/st help` | See all commands |

---

## What's Next?

- [Portal Creation](Portal-Creation.mdPortal-Creation) - In-depth portal building
- [Portal Types](Portal-Types.mdPortal-Types) - Standard, RTP and One-Way
- [Configuration](Configuration.mdConfiguration) - Customize the plugin
- [Particles and Effects](Particles-and-Effects.mdParticles-and-Effects) - Make portals look good

