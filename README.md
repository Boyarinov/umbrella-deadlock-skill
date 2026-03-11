# deadlock-lua

Claude Code skill for writing Lua scripts with the Umbrella framework for Valve's Deadlock.

## What this is

A skill pack that teaches Claude how to write Deadlock Lua scripts correctly. It provides:

- **SKILL.md** -- compact API patterns, callback reference, and rules loaded into the system prompt (~8KB)
- **docs/** -- full API reference (17 pages) loaded on-demand when Claude needs exact function signatures

Claude reads only what it needs: the skill itself is always in context, doc pages are fetched via `skill://deadlock-lua/docs/<page>.md` when it needs to look up specific API details.

## Installation

### Option A: Clone into `.claude/skills/`

```bash
# User-level (available in all projects)
git clone https://github.com/<your-org>/umbrella-deadlock-skill ~/.claude/skills/deadlock-lua

# Or project-level (committed to repo)
git clone https://github.com/<your-org>/umbrella-deadlock-skill .claude/skills/deadlock-lua
```

### Option B: Custom directory

Clone anywhere, then add to your Claude settings:

```jsonc
// .claude/settings.json or ~/.claude/settings.json
{
  "skills": {
    "customDirectories": [
      "/path/to/umbrella-deadlock-skill/.."
    ]
  }
}
```

Note: `customDirectories` scans one level deep, so point it at the **parent** of the skill directory.

## Structure

```
umbrella-deadlock-skill/
  SKILL.md              -- Skill definition (system prompt content)
  README.md             -- This file
  docs/
    getting-started.md  -- Onboarding guide
    entities.md         -- Entity, player_pawn, ability, modifier, entity_list
    rendering.md        -- Render API, fonts, images, vertex
    input-commands.md   -- CUserCmd, input, convar
    callbacks.md        -- All callback hooks
    tracing.md          -- trace.line, hull, bullet, bullet_hitbox
    utilities.md        -- utils, db, global_vars, game_rules, meta, etc.
    menu.md             -- Menu system and all widget types
    panorama.md         -- Panorama UI
    http.md             -- HTTP requests
    types.md            -- Color, Vector, Angle, Vec2
    target-selection.md -- TargetSelection system
    notifications.md    -- Notification system
    raw-struct.md       -- Raw struct field access
    enums.md            -- All game enums
    SUMMARY.md          -- GitBook table of contents
    README.md           -- Docs landing page
```

## Updating docs

Docs are generated from LuaLS annotation files. To regenerate:

```bash
cd deadlock-api-vscode
python scripts/generate_docs.py --output ../umbrella-deadlock-skill/docs/
```
