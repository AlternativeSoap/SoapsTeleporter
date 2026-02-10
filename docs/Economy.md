# Economy

SoapsTeleporter can charge players to use portals. You can set costs in money, items, experience points or custom items.

---

## Requirements

For money costs, you need:
1. **Vault** plugin installed
2. An **economy plugin** like EssentialsX, CMI, or any Vault-compatible economy
3. Economy enabled in `config.yml`:

```yaml
economy:
  enabled: true
```

Item costs and XP costs do not require Vault.

---

## Setting a Cost

```
/st setcost <portal> <amount>
```

### Money Cost

```
/st setcost spawn 100
```
Charges $100 to use the portal.

### Item Cost

```
/st setcost nether 5 DIAMOND
```
Requires 5 diamonds. The items are consumed when the player teleports.

### Experience Cost

```
/st setcost arena 30 EXP
```
Requires 30 experience points.

### Custom Item Cost (Hand)

Hold a specific item in your hand and run:

```
/st setcost <portal> hand [amount]
```

This sets the cost to the exact item you're holding, including custom name, lore and enchantments. The amount defaults to 1 if not specified.

```
/st setcost vip hand 1
```
Costs 1 of whatever custom item you're holding.

### Removing a Cost

```
/st setcost <portal> 0
```

Setting the cost to `0` makes the portal free to use.

---

## Refunds

If `refund-on-failure` is enabled in config (it is by default), players get their money back if the teleportation fails for any reason.

---

## Payment Timing

The `payment-timing` config option controls when payment is taken:

| Value | Behavior |
|-------|----------|
| `before` | Payment is taken before teleportation |
| `after` | Payment is taken after successful teleportation |

---

## Economy Messages

When a player doesn't have enough funds, they'll see a message showing:
- How much they need
- How much they have (for money costs)
- What items they're missing (for item costs)

---

## Cost vs Money Condition

These are different things:

| Feature | `/st setcost` | `/st setcondition money` |
|---------|--------------|------------------------|
| Purpose | **Charges** the player | **Checks** the player's balance |
| Money consumed? | Yes | No |
| Items consumed? | Yes (for item costs) | N/A |
| Use case | Pay-to-use portals | Minimum balance gates |

---

## Examples

**$500 toll portal:**
```
/st setcost tollgate 500
```

**Diamond entrance fee:**
```
/st setcost dungeon_entry 3 DIAMOND
```

**XP cost:**
```
/st setcost enchant_portal 50 EXP
```

**Free portal:**
```
/st setcost spawn 0
```

---

## Next Steps

- [Conditions](Conditions) - More ways to restrict portal access
- [Commands and Permissions](Commands-and-Permissions) - Full command reference
- [Interactive Management](Interactive-Management) - Manage costs through the GUI
