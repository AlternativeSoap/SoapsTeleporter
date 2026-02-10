# Commands and Permissions

Every command and permission in SoapsTeleporter. The main command is `/st` (aliases: `/soapsteleporter`, `/teleporter`).

---

## Commands

### Portal Creation

| Command | Description | Permission |
|---------|-------------|------------|
| `/st wand` | Get the portal selection wand | `st.command.tool` |
| `/st set p1` | Set position 1 at your location | `st.command.set` |
| `/st set p2` | Set position 2 at your location | `st.command.set` |
| `/st add <name>` | Create a portal from your selection | `st.command.add` |
| `/st remove <portal>` | Delete a portal | `st.command.remove` |
| `/st duplicate <source> <newname>` | Copy a portal with all settings | `st.command.add` |

### Portal Connections

| Command | Description | Permission |
|---------|-------------|------------|
| `/st connect <source> <target>` | Link two portals together | `st.command.connect` |
| `/st unlink <portal>` | Disconnect a portal from its target | `st.command.unlink` |

### Portal Management

| Command | Description | Permission |
|---------|-------------|------------|
| `/st enable <portal>` | Enable a disabled portal | `st.command.enable` |
| `/st disable <portal>` | Temporarily disable a portal | `st.command.disable` |
| `/st rename <portal> <newname>` | Change a portal's name | `st.command.rename` |
| `/st move <portal>` | Enter move mode to relocate a portal | `st.command.move` |
| `/st move cancel` | Cancel move mode | `st.command.move` |
| `/st reset <portal>` | Reset portal settings to defaults | `st.command.reset` |
| `/st manage [portal]` | Open interactive management | `st.manage` |

### Particle Settings

| Command | Description | Permission |
|---------|-------------|------------|
| `/st setparticle <portal> <particle>` | Set particle effect | `st.command.setparticle` |
| `/st setcolor <portal> <r> <g> <b>` | Set DUST particle color (0-255) | `st.command.setcolor` |
| `/st setcount <portal> <count>` | Set particle count | `st.command.setcount` |
| `/st setspread <portal> <tight> <wide>` | Set particle spread | `st.command.setspread` |
| `/st setinterval <portal> <ticks>` | Set particle display interval | `st.command.setinterval` |

### Sound Settings

| Command | Description | Permission |
|---------|-------------|------------|
| `/st setsound <portal> <sound> [volume] [pitch]` | Set teleport sound | `st.command.setsound` |

### Portal Settings

| Command | Description | Permission |
|---------|-------------|------------|
| `/st setdirection <portal> <direction>` | Set exit direction | `st.command.setdirection` |
| `/st settype <portal> <standard\|rtp> [world] [min] [max]` | Change portal type | `st.command.settype` |
| `/st setcost <portal> <amount> [type]` | Set usage cost | `st.command.setcost` |
| `/st setcooldown <portal> <seconds>` | Set cooldown between uses | `st.command.setcooldown` |
| `/st setwarmup <portal> <seconds>` | Set warmup timer | `st.command.setwarmup` |
| `/st setdisablesafecheck <portal>` | Toggle safety checks | `st.command.setdisablesafecheck` |

### Conditions

| Command | Description | Permission |
|---------|-------------|------------|
| `/st setcondition <portal> <condition> [value]` | Set a condition | `st.command.setcondition` |
| `/st addcondition <portal> <condition> [value]` | Add a condition | `st.command.setcondition` |
| `/st removecondition <portal> <condition\|all>` | Remove a condition | `st.command.setcondition` |

### Portal Commands (run on enter/exit)

| Command | Description | Permission |
|---------|-------------|------------|
| `/st setcommand <portal> <enter\|exit> <command>` | Add a command to run on portal use | `st.command.setcommand` |

### Information

| Command | Description | Permission |
|---------|-------------|------------|
| `/st list` | List all portals | `st.command.list` |
| `/st info <portal> [page]` | View portal details | `st.command.info` |
| `/st tp <portal>` | Teleport directly to a portal | `st.command.tp` |
| `/st help [command]` | Show help | None |

### Admin

| Command | Description | Permission |
|---------|-------------|------------|
| `/st reload` | Reload all config files | `st.command.reload` |
| `/st backup` | Create a backup of portal data | `st.command.backup` |
| `/st debug` | Toggle debug mode | `st.command.debug` |

---

## Permissions

### Admin Permissions

| Permission | Default | Description |
|------------|---------|-------------|
| `st.admin` | OP | Full access to all commands |
| `st.manage` | OP | Access to interactive management interface |
| `st.debug` | OP | Access to debug commands |

### Command Permissions

| Permission | Default | Description |
|------------|---------|-------------|
| `st.command.set` | OP | Use `/st set` commands |
| `st.command.add` | OP | Create portals |
| `st.command.connect` | OP | Connect portals |
| `st.command.remove` | OP | Remove portals |
| `st.command.list` | OP | List portals |
| `st.command.disable` | OP | Disable portals |
| `st.command.enable` | OP | Enable portals |
| `st.command.reload` | OP | Reload the plugin |
| `st.command.tp` | OP | Teleport to portals |
| `st.command.tool` | OP | Get the portal wand |
| `st.command.info` | OP | View portal info |
| `st.command.backup` | OP | Create backups |
| `st.command.setdirection` | OP | Set portal direction |
| `st.command.settype` | OP | Set portal type |
| `st.command.setcommand` | OP | Set portal commands |
| `st.command.setcondition` | OP | Set conditions |
| `st.command.reset` | OP | Reset portals |
| `st.command.rename` | OP | Rename portals |
| `st.command.move` | OP | Move portals |
| `st.command.unlink` | OP | Unlink portals |
| `st.command.setparticle` | OP | Set particles |
| `st.command.setcolor` | OP | Set particle colors |
| `st.command.setcount` | OP | Set particle count |
| `st.command.setspread` | OP | Set particle spread |
| `st.command.setinterval` | OP | Set display interval |
| `st.command.setsound` | OP | Set sounds |
| `st.command.setcost` | OP | Set costs |
| `st.command.setcooldown` | OP | Set cooldowns |
| `st.command.setwarmup` | OP | Set warmup timers |
| `st.command.setdisablesafecheck` | OP | Toggle safety checks |

### Usage Permissions

| Permission | Default | Description |
|------------|---------|-------------|
| `st.portal.use` | Everyone | General permission to use any portal |
| `st.portal.use.<name>` | Everyone | Permission for a specific portal (when per-portal permissions are enabled) |
| `st.portal.bypass.warmup` | OP | Skip warmup timers |
| `st.portal.bypass.cooldown` | OP | Skip cooldown timers |
| `st.portal.limit.bypass` | OP | Bypass portal creation limits |
| `st.portal.group.*` | None | Portal group access (st.portal.group.groupname) |

### Protection Permissions

| Permission | Default | Description |
|------------|---------|-------------|
| `st.protection.bypass` | OP | Break/place blocks inside portals |

---

## Direction Values

For `/st setdirection`:

```
NORTH, SOUTH, EAST, WEST, UP, DOWN, PLAYER, NONE, DEFAULT
```

## Condition Values

For `/st setcondition` and `/st addcondition`:

```
day, night, rain, thunder, clear, sun, storm, level, sneak, fly, 
world, biome, gamemode, item, money, advancement, playtime
```

---

## Next Steps

- [Interactive Management](Interactive-Management.mdInteractive-Management) - Manage portals with a click-based GUI
- [Integrations](Integrations.mdIntegrations) - PlaceholderAPI, WorldGuard and more
- [Examples](Examples.mdExamples) - Real setup examples

