# Skript-Worldguard-Tab-Completions

Adds tab completion support to WorldGuard `/region` commands using Skript.

[SpigotMC Resource](https://www.spigotmc.org/resources/skript-worldgaurd-tab-completions.129487/)

---

## Dependencies

- [Skript](https://github.com/SkriptLang/Skript)
- [SkBee](https://github.com/ShaneBeee/SkBee)

---

## Features

- Tab-completion for common WorldGuard region commands: `/rg`, `/regions`, `/region`
- Suggests region names and flag names
- Supports multiple WorldGuard subcommands and context-aware completions

---

## How to Use

Put the following snippet in your Skript file.
Be sure to set `{regions::*}` to your actual region list.

```skript
on tab complete of "/rg", "/regions" or "/region":
    set {regions::*} to                                       # REPLACE WITH YOUR REGIONS
    set tab completions for position 1 to "addmember", "addowner", "claim", "create", "define", "delete", "flag", "flags", "list", "move", "redefine", "remmember", "removeowner", "remove", "select", "setparent", "setpriority", "teleport", "update" and "info"
    if tab arg-1 is "flags" or "flag" or "info" or "redefine" or "select" or "setpriority" or "remove" or "teleport" or "setparent" or "claim":
        set tab completions for position 2 to {regions::*}
    if tab arg-1 is "addmember" or "addowner" or "remmember" or "removeowner" or "delete":
        set tab completions for position 2 to {regions::*}
    if tab arg-1 is "flag":
        set tab completions for position 2 to {regions::*}
        set tab completions for position 3 to "passthrough", "nonplayer-protection-domains", "build", "interact", "block-break", "block-place", "use", "damage-animals", "chest-access", "ride", "pvp", "sleep", "respawn-anchors", "tnt", "vehicle-place", "vehicle-destroy", "lighter", "block-trampling", "frosted-ice-form", "item-frame-rotation", "firework-damage", "use-anvil", "use-dripleaf", "creeper-explosion", "enderdragon-block-damage", "ghast-fireball", "other-explosion", "fire-spread", "enderman-grief", "snowman-trails", "ravager-grief", "mob-damage", "mob-spawning", "deny-spawn", "entity-painting-destroy", "entity-item-frame-destroy", "wither-damage", "lava-fire", "lightning", "water-flow", "lava-flow", "snow-fall", "snow-melt", "ice-form", "ice-melt", "frosted-ice-melt", "mushroom-growth", "leaf-decay", "grass-growth", "mycelium-spread", "vine-growth", "rock-growth", "sculk-growth", "crop-growth", "soil-dry", "coral-fade", "copper-fade", "entry", "exit", "exit-via-teleport", "exit-override", "entry-deny-message", "exit-deny-message", "notify-enter", "notify-leave", "greeting", "greeting-title", "farewell", "farewell-title", "enderpearl", "chorus-fruit-teleport", "teleport", "spawn", "teleport-message", "item-pickup", "item-drop", "exp-drops", "deny-message", "invincible", "fall-damage", "game-mode", "time-lock", "weather-lock", "natural-health-regen", "natural-hunger-drain", "heal-delay", "heal-amount", "heal-min-health", "heal-max-health", "feed-delay", "feed-amount", "feed-min-hunger", "feed-max-hunger", "blocked-cmds", "allowed-cmds", "pistons", "send-chat", "receive-chat" and "potion-splash"
        set tab completions for position 4 to "ALLOW" and "DENY"
```

---

## Notes

- This simply acts as a tab completion helper for region commands; edit `{regions::*}` to match your regions.
- Can be adjusted for more commands or completions as you wish.

---
