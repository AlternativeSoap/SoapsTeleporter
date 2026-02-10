# FAQ

Common questions about SoapsTeleporter.

---

## General

**How do I update the plugin?**

Replace the jar file in your `plugins/` folder and restart the server. Your config and portal data are preserved.

**Does it support Folia?**

Yes. The plugin is Folia-compatible.

**What Minecraft versions are supported?**

Minecraft 1.21 and above, running on Paper or Folia.

**Where are portals stored?**

In `plugins/SoapsTeleporter/portals.yml`. The plugin saves automatically at a configurable interval.

---

## Portals

**My portal isn't teleporting players. What's wrong?**

Check these things:
1. Is the portal enabled? Check with `/st info <portal>`
2. Is it connected to another portal? Use `/st connect <source> <target>`
3. Does the player have `st.portal.use` permission?
4. If per-portal permissions are on, does the player have `st.portal.use.<name>`?
5. Run `/st debug selftest` to check for issues

**Can portals connect across worlds?**

Yes, as long as `cross-world` is set to `true` in config (it is by default).

**What happens when I break blocks inside a portal?**

If protection is enabled, you can't. Players with `st.protection.bypass` can break blocks in portal areas.

**How big can a portal be?**

Default is 1 to 50 blocks per side. You can change `min-size` and `max-size` in config.

**Can I have overlapping portals?**

No. The plugin prevents creating portals that overlap with existing ones.

**Is there a portal limit?**

Not by default. You can set limits per player and per world in config.

---

## Particles

**Particles aren't showing. What do I do?**

1. Check that `particles.enabled` is `true` in config
2. Make sure you're within the `nearby-player-radius` (default 30 blocks)
3. Check your client video settings. Particles set to "Minimal" in Minecraft won't show some effects

**Can I turn off particles for one portal?**

You can set the count to a very low number, but there's no per-portal toggle for particles.

**How do I change the color?**

Only `DUST` particles support custom colors. Use `/st setcolor <portal> <r> <g> <b>` with values from 0 to 255.

---

## Economy

**Economy isn't working.**

You need three things:
1. `economy.enabled: true` in config
2. Vault plugin installed
3. An economy plugin (EssentialsX, CMI, etc.) installed

**What's the difference between cost and money condition?**

`/st setcost` charges the player. The money is taken from their balance.
`/st setcondition money` just checks their balance without charging.

---

## Permissions

**How do I give players access to a specific portal?**

If `per-portal-permissions` is enabled in config, each portal has its own permission: `st.portal.use.<portalname>`. Give this to players using your permission plugin.

**Can normal players create portals?**

Not by default. All management commands default to OP. You can give `st.command.add`, `st.command.connect`, etc. to players if you want.

---

## Performance

**Will having many portals impact server performance?**

The plugin uses caching and adaptive density to stay light. If you have many portals and many players, adjust the performance settings in config:
- Lower `max-particles-per-tick`
- Enable `adaptive-density`
- Increase `nearby-player-radius` if portals only need to render close up
- Increase the display interval

**Is the plugin async?**

Teleportation and chunk preloading use async operations where possible.

---

## Troubleshooting

**I see errors in console after updating.**

Try `/st reload` first. If errors persist, check that your config files are valid YAML. You can delete the config files and let the plugin regenerate them, or check [Default Config Files](Default-Config-Files) for the correct format.

**Self-test says something is wrong.**

Run `/st debug selftest` and read the output. It checks:
- Config file validity
- Messages file
- Portal data
- Particle system
- Permissions
- Required files

**How do I report a bug?**

Join the support Discord: [discord.gg/mawAzwFq](https://discord.gg/mawAzwFq)

---

## Next Steps

- [Getting Started](Getting-Started) - Start from the beginning
- [Configuration](Configuration) - Full config reference
- [Commands and Permissions](Commands-and-Permissions) - All commands
