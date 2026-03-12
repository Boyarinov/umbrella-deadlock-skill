# Umbrella Deadlock Skill

A Claude Code skill that teaches Claude how to write Lua scripts for the Umbrella framework in Valve's Deadlock.

## What this does

A skill pack with two layers:

- **SKILL.md** -- compact API patterns, callback reference, and rules loaded into context
- **docs/** -- full API reference (17 pages) loaded on-demand when Claude needs exact signatures

Claude reads the skill to know the correct API, callbacks, patterns, and rules for writing Deadlock Lua scripts.

## Installation

1. Clone into your Claude skills directory:

```bash
git clone https://github.com/Boyarinov/umbrella-deadlock-skill ~/.claude/skills/deadlock-lua
```

On Windows:

```bash
git clone https://github.com/Boyarinov/umbrella-deadlock-skill %USERPROFILE%\.claude\skills\deadlock-lua
```

2. Done. Claude Code automatically loads skills from `~/.claude/skills/`.

**Alternative:** for project-level install, clone into `.claude/skills/deadlock-lua` inside your project repo instead.

## Pairing with the MCP bridge

For full functionality -- executing Lua in-game, reading ability data, managing scripts -- install the companion MCP bridge:
[deadlock-mcp-bridge](https://github.com/Boyarinov/deadlock-mcp-bridge)

## What's included

```
umbrella-deadlock-skill/
  SKILL.md                -- Skill definition (loaded into context)
  docs/
    getting-started.md    -- Onboarding guide
    entities.md           -- Entity, player_pawn, ability, modifier, entity_list
    rendering.md          -- Render API, fonts, images, vertex
    input-commands.md     -- CUserCmd, input, convar
    callbacks.md          -- All callback hooks
    tracing.md            -- trace.line, hull, bullet, bullet_hitbox
    utilities.md          -- utils, db, global_vars, game_rules, meta, etc.
    menu.md               -- Menu system and all widget types
    panorama.md           -- Panorama UI
    http.md               -- HTTP requests
    types.md              -- Color, Vector, Angle, Vec2
    target-selection.md   -- TargetSelection system
    notifications.md      -- Notification system
    raw-struct.md         -- Raw struct field access
    enums.md              -- All game enums
```
