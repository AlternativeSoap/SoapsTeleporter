# Changelog

All notable updates to SoapsTeleporter.

---

## v1.0.0

The first release. Here's what's included.

### Portals
- Create portals of any size using a selection wand
- Connect portals for two-way travel
- One-way portal support
- Random Teleport (RTP) portals with configurable range and world
- Horizontal and vertical portal detection
- Portal protection (blocks can't be broken near portals)
- Move, rename and duplicate portals
- Backup and restore portal data

### Particles and Sounds
- Per-portal particle effects with any Minecraft particle type
- Custom RGB colors for DUST particles
- Adjustable particle count, spread and display interval
- 3D volumetric particle rendering
- Adaptive particle density for busy servers
- Per-portal teleport sounds with pitch and volume control
- Sound preview when setting sounds

### Conditions
- Time of day requirements (day, night)
- Weather conditions (rain, thunder, clear, sun, storm)
- Player level requirements
- Sneaking and flying requirements
- World, biome and gamemode restrictions
- Health and hunger thresholds
- Item and equipment requirements (including custom items)
- Advancement requirements
- Playtime requirements
- Nearby player count requirements
- Time and date range restrictions
- Daily usage limits
- Stack multiple conditions on one portal

### Economy
- Money costs using Vault
- Item costs (consume items to teleport)
- Experience point costs
- Custom item costs (hold item in hand)
- Refund on failed teleportation

### Portal Settings
- Warmup timers with movement cancellation
- Cooldown timers between uses
- Teleport direction control
- Safety checks for destinations
- Enter and exit commands (run commands on portal use)

### Management
- Interactive chat-based management interface
- Click-through menus for all portal settings
- Full tab completion on every command
- Paginated portal info display
- Portal list with status indicators
- Self-test diagnostics
- Debug logging

### Integrations
- PlaceholderAPI (12 placeholders for portals, players, economy, stats)
- Vault economy support
- WorldGuard region protection
- Lands claim integration
- GriefPrevention claim support
- Dynmap web map markers
- BlueMap web map markers

### Server
- Paper and Folia support
- Minecraft 1.21+ compatibility
- MiniMessage formatting for all messages
- Auto-save with configurable interval
- Hot reload without restart
- Performance caching and optimization

