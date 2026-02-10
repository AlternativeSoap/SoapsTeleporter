# Introduction

## What is SoapsTeleporter?

SoapsTeleporter is a portal plugin for PaperMC servers. It lets you place portals in your world that players can walk through to teleport somewhere else. Each portal can have its own particles, sounds, costs, conditions and more.

It is designed for Minecraft 1.21+ and supports both Paper and Folia servers.

---

## Features at a Glance

### Portal System
- Create portals of any size using a selection wand
- Connect two portals together for two-way travel
- Set up one-way portals
- Random Teleport (RTP) portals that send players to random locations
- Portals detect orientation automatically (floor portals vs wall portals)

### Visual Effects
- Per-portal particle effects (choose from any Minecraft particle)
- Custom DUST particle colors with RGB values
- Adjustable particle count, spread and display interval
- 3D volumetric rendering that fills the entire portal area
- Adaptive particle density on busy servers

### Sounds
- Per-portal teleport sounds
- Adjustable pitch and volume
- Sound preview when you set a new sound

### Portal Conditions
- Time of day (day only, night only)
- Weather (rain, thunder, clear)
- Player level requirements
- Sneaking or flying requirements
- World, biome and gamemode restrictions
- Health and hunger thresholds
- Item requirements (including custom items)
- Equipment checks (armor, weapons)
- Advancement requirements
- Playtime requirements
- Nearby player count

### Economy
- Charge money to use portals (requires Vault)
- Charge items (diamonds, emeralds, anything)
- Charge experience points
- Charge custom items (hold the item and use it as cost)
- Refund on failed teleportation

### Safety
- Safe teleport destination checking
- Cross-world teleportation support
- Warmup timers (cancel if the player moves)
- Cooldown timers between uses
- Portal protection (prevents block breaking near portals)

### Server Management
- Interactive chat-based management interface
- Full tab completion on all commands
- Backup system for portal data
- Debug logging with multiple levels
- Self-test command for diagnostics
- Auto-save with configurable interval
- Hot reload without server restart

### Integrations
- **PlaceholderAPI** for scoreboards and chat
- **Vault** for economy
- **WorldGuard** for region protection
- **Lands** for land claim support
- **GriefPrevention** for claim support
- **Dynmap** and **BlueMap** for web map markers

---

## How It Works

The basic flow is simple:

1. Get the portal wand with `/st wand`
2. Left-click a block to set corner 1
3. Right-click a block to set corner 2
4. Create the portal with `/st add myportal`
5. Repeat for a second portal
6. Connect them with `/st connect myportal myportal2`

Players walk into one portal and appear at the other. That's it for a basic setup. From there you can add particles, sounds, costs and conditions to make things more interesting.

---

## Next Steps

Head to [Getting Started](Getting-Started) to install the plugin and build your first portal.
