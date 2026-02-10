# Examples

Real-world portal setups you can use on your server. Copy the commands and adjust names to your liking.

---

## Basic Spawn Portal

Two portals that link spawn to a build area.

```
/st wand
```
Select two corners at spawn, then:
```
/st add spawn
```
Go to the build area, select two corners, then:
```
/st add buildarea
/st connect spawn buildarea
```

Done. Walk into either portal to travel between them.

---

## Hub with Multiple Destinations

Create a central hub with portals going to different locations.

```
/st add hub_to_shops
/st add shops
/st connect hub_to_shops shops

/st add hub_to_pvp
/st add pvp_arena
/st connect hub_to_pvp pvp_arena

/st add hub_to_farm
/st add farm_world
/st connect hub_to_farm farm_world
```

Customize each portal:
```
/st setparticle hub_to_shops HAPPY_VILLAGER
/st setparticle hub_to_pvp FLAME
/st setparticle hub_to_farm END_ROD

/st setcolor hub_to_shops 0 255 0
```

---

## Paid Nether Portal

A portal that costs money to use.

```
/st add nether_gate
/st add nether_exit
/st connect nether_gate nether_exit
/st setcost nether_gate 250
/st setparticle nether_gate SOUL_FIRE_FLAME
/st setcolor nether_gate 0 180 255
/st setsound nether_gate BLOCK_PORTAL_TRIGGER
```

Players pay $250 to go to the Nether. Coming back is free.

---

## VIP-Only Portal

A portal only accessible with a permission.

```
/st add vip_lounge
/st add vip_destination
/st connect vip_lounge vip_destination
/st setparticle vip_lounge DUST
/st setcolor vip_lounge 255 215 0
```

In your permissions plugin, give VIP players:
```
st.portal.use.vip_lounge
```

Make sure `per-portal-permissions` is enabled in config.

---

## Dungeon Entry with Conditions

A portal that requires preparation.

```
/st add dungeon_entry
/st add dungeon
/st connect dungeon_entry dungeon

/st addcondition dungeon_entry level 20
/st addcondition dungeon_entry item DIAMOND_SWORD 1
/st addcondition dungeon_entry night
/st setcost dungeon_entry 500
/st setwarmup dungeon_entry 5
/st setcooldown dungeon_entry 300

/st setparticle dungeon_entry DRAGON_BREATH
/st setsound dungeon_entry BLOCK_PORTAL_TRIGGER 1.0 0.5
```

This portal:
- Requires level 20
- Requires a diamond sword in inventory
- Only works at night
- Costs $500
- Has a 5 second warmup (player must stand still)
- Has a 5 minute cooldown between uses

---

## Random Teleport (RTP) Portal

A wilderness portal that sends players to a random location.

```
/st add wilderness
/st settype wilderness rtp world 500 10000
/st setcooldown wilderness 120
/st setparticle wilderness PORTAL
/st setsound wilderness ENTITY_ENDERMAN_TELEPORT 1.0 1.2
```

Players step in and get teleported to a random spot between 500 and 10,000 blocks from the center. 2 minute cooldown between uses.

---

## Nether RTP

Random teleport in the Nether:

```
/st add nether_rtp
/st settype nether_rtp rtp world_nether 100 3000
/st setparticle nether_rtp SOUL_FIRE_FLAME
/st setcooldown nether_rtp 60
```

---

## Portal with Enter/Exit Commands

Run commands when players use the portal.

```
/st add welcome_portal
/st add welcome_dest
/st connect welcome_portal welcome_dest

/st setcommand welcome_portal enter say %player% just entered the portal!
/st setcommand welcome_dest exit effect give %player% speed 30 1
```

When someone enters the portal, a message is sent. When they arrive, they get Speed I for 30 seconds.

---

## Event Portal (Holiday)

A portal that only works during December (set via portals.yml):

```
/st add christmas_portal
/st add christmas_land
/st connect christmas_portal christmas_land
/st setparticle christmas_portal DUST
/st setcolor christmas_portal 255 0 0
```

Then edit `portals.yml` and add under this portal:
```yaml
dateRange: "12-01_12-31"
```

---

## Floor Pad Portal

Create a horizontal (floor) portal:

1. Select two corners of a flat area (same Y level or 1 block height)
2. Create the portal

```
/st add launchpad
/st add landing
/st connect launchpad landing
/st setparticle launchpad END_ROD
/st setsound launchpad ENTITY_FIREWORK_ROCKET_LAUNCH
```

Floor portals are detected automatically from the selection shape. Players step onto them to teleport.

---

## Portal with Direction

Force players to face a specific direction after teleporting:

```
/st add castle_entrance
/st add castle_interior
/st connect castle_entrance castle_interior
/st setdirection castle_interior NORTH
```

When players arrive at the castle interior, they always face North.

---

## Full Setup Example

A complete server portal network:

```
# Create spawn hub portal
/st wand
# Select area at spawn
/st add spawn_hub

# Create and connect destinations
/st add shops_portal
/st connect spawn_hub shops_portal
/st setparticle spawn_hub HAPPY_VILLAGER
/st setparticle shops_portal HAPPY_VILLAGER

# Customize each
/st setcost shops_portal 0
/st setcooldown spawn_hub 5
/st setwarmup spawn_hub 3

# Create a paid portal
/st add vip_area
/st add vip_dest
/st connect vip_area vip_dest
/st setcost vip_area 1000
/st setparticle vip_area DUST
/st setcolor vip_area 255 215 0
/st addcondition vip_area level 10

# Create wilderness RTP
/st add wilderness
/st settype wilderness rtp world 1000 15000
/st setcooldown wilderness 180
/st setparticle wilderness PORTAL

# Backup
/st backup
```

---

## Next Steps

- [Portal Creation](Portal-Creation) - Detailed creation guide
- [Conditions](Conditions) - All condition types
- [Particles and Effects](Particles-and-Effects) - Visual customization
