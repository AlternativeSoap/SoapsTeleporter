# Portal Types

SoapsTeleporter supports three types of portals. You can change a portal's type at any time.

---

## Standard Portals

This is the default type. Standard portals connect to another portal. Walk into one, come out at the other.

```
/st settype <portal> standard
```

Standard portals require a connection to work. Use `/st connect <source> <target>` to link them.

By default, standard connections are two-way. Walking into either portal sends you to the other.

---

## RTP Portals (Random Teleport)

RTP portals teleport players to a random location within a configurable range. No second portal needed.

```
/st settype <portal> rtp [world] [min] [max]
```

### Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `world` | Current world | Which world to teleport to |
| `min` | `100` | Minimum distance from world center |
| `max` | `5000` | Maximum distance from world center |

### Examples

```
/st settype wilderness rtp
```
Uses current world, range 100-5000.

```
/st settype wilderness rtp world 500 10000
```
Teleports to "world" between 500 and 10,000 blocks from center.

```
/st settype nether_rtp rtp world_nether 100 3000
```
Random location in the Nether.

### How RTP Works

1. Player steps into the portal
2. Plugin picks a random location within the range
3. Chunks at the destination are preloaded
4. Safety check runs to make sure the location isn't in lava, void, etc.
5. If the spot isn't safe, it retries (up to 10 attempts by default)
6. Player gets teleported

### RTP Settings

RTP behavior is configured globally in `config.yml`:

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

### Important Notes

- An RTP portal cannot be connected to another portal. Disconnect it first before switching to RTP.
- Range must be between 50 and 100,000 blocks.
- Minimum range must be less than maximum range.

---

## One-Way Portals

One-way portals only allow travel in one direction. Portal A sends players to Portal B, but Portal B doesn't send them back.

To set up a one-way portal:
1. Create two portals as normal
2. Connect them with `/st connect <source> <target>`
3. The portal at the source is the entrance
4. The portal at the target is the exit

Players trying to enter from the wrong side will see a "one-way" message.

---

## Changing Portal Type

You can switch a portal's type at any time:

```
/st settype <portal> standard
/st settype <portal> rtp [world] [min] [max]
```

When switching:
- Changing **to RTP** removes any existing connection
- Changing **to standard** clears RTP settings

---

## Next Steps

- [Particles and Effects](Particles-and-Effects.mdParticles-and-Effects) - Customize portal visuals
- [Conditions](Conditions.mdConditions) - Restrict who can use a portal
- [Economy](Economy.mdEconomy) - Charge for portal use

