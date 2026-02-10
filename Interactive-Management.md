# Interactive Management

SoapsTeleporter includes a chat-based interactive management interface. Instead of typing commands, you can click through menus to configure portals.

---

## Opening the Manager

```
/st manage [portal]
```

If you don't specify a portal name, it shows a list of portals to choose from.

**Permission required:** `st.manage`

---

## Main Menu

When you open the manager for a portal, you see the main menu with:
- Portal status (enabled/disabled)
- Portal type (standard/RTP)
- Current connection

Below that are category buttons you can click:

| Category | What it manages |
|----------|----------------|
| **Visual Effects** | Particle type, color, count, spread, interval |
| **Audio Settings** | Sound, pitch, volume |
| **Economy & Timing** | Cost, cooldown, warmup |
| **Connection Settings** | Connect/unlink, portal type, direction |
| **Conditions & Requirements** | All portal conditions |
| **Commands & Events** | Enter and exit commands |
| **Administrative** | Enable/disable, rename, move, reset |

Click any category to open its settings.

---

## Visual Effects

Shows current particle settings and buttons to change:
- **Set Particle** - Change the particle type
- **Set Color** - Set DUST particle color
- **Set Count** - Adjust particle density
- **Set Spread** - Configure particle distribution
- **Set Interval** - Change display timing

---

## Audio Settings

Shows current sound and controls for:
- **Set Sound** - Change the teleport sound
- **Disable Sound** - Turn sounds off
- **Pitch controls** - Low (0.8), Normal (1.0), High (1.5), or Custom
- **Volume controls** - Quiet (0.3), Normal (1.0), Loud (1.5), or Custom

---

## Economy & Timing

Shows current cost, cooldown and warmup settings:
- **Set Cost** - Configure portal cost
- **Set Cooldown** - Time between uses
- **Set Warmup** - Activation delay

---

## Connection Settings

Manage portal connections:
- **Connect Portal** - Link to another portal
- **Unlink Portal** - Remove connection
- **Set Type** - Switch between standard/RTP
- **Set Direction** - Change exit direction

---

## Conditions & Requirements

The conditions menu has categorized buttons for adding conditions:

**Time & Weather:** Day, Night, Rain, Thunder, Clear, Sun, Storm

**Economy & Items:** Add Item Requirement, Add Money Requirement

**Player Level:** Custom Level, Min Level, Max Level

**Health & Food:** Min/Max Health, Min/Max Food

**Equipment:** Armor, Weapon, Naked, Full Armor

**Player State:** Sneaking, Flying, Jumping, On Fire, Sprinting

**Environment:** World, Biome, GameMode

**Social:** Min Players, Max Players, Solo Only

**Achievements:** Advancement, Playtime

Click a button and type the value in chat when prompted. Type `cancel` at any time to abort.

Existing conditions are shown with delete buttons next to them.

---

## Commands & Events

Manage commands that run automatically when players use the portal:
- **Add Command** - Add a new enter or exit command
- Click the trash icon next to a command to remove it

Commands support the `%player%` placeholder for the player's name.

**Enter commands** run when a player enters the portal (before teleporting).
**Exit commands** run when a player arrives at the destination.

### Example Commands

```
say Welcome %player%!
give %player% diamond 1
effect give %player% speed 30 1
tp %player% spawn
```

---

## Administrative

- **Enable/Disable Portal** - Toggle portal on/off
- **Rename Portal** - Change the name
- **Move Portal** - Relocate to new position
- **Reset Settings** - Reset everything to defaults

---

## Navigation

Every submenu has a **Back to Main Menu** button. Breadcrumbs at the top show where you are:

```
Portal Management > Conditions > Add Condition
```

Paginated lists (like commands and conditions) have Previous/Next buttons.

---

## Next Steps

- [Integrations](Integrations.mdIntegrations) - PlaceholderAPI, WorldGuard and more
- [Commands and Permissions](Commands-and-Permissions.md) - Full command reference

