# Umbrella Lua API for Deadlock

Complete API reference for the Umbrella Lua scripting system in Deadlock (Valve's Source 2 / Citadel). Lua 5.4 runtime with access to game entities, rendering, input, and more.

## Quick Start

New to Umbrella scripting? See the [Getting Started](getting-started.md) guide for script structure, load order, and your first working script.

## API Reference

| Category | Description |
|----------|-------------|
| [Entities](entities.md) | Game entities, player pawns, abilities, modifiers |
| [Rendering](rendering.md) | 2D drawing, fonts, images, render targets |
| [Input & Commands](input-commands.md) | User commands, key bindings, convars |
| [Callbacks](callbacks.md) | Event hooks for game state changes |
| [Tracing](tracing.md) | Raycasting and collision detection |
| [Utilities](utilities.md) | Helper functions, math, prediction |
| [Menu System](menu.md) | In-game configuration UI |
| [Panorama UI](panorama.md) | Valve's Panorama UI interaction |
| [HTTP](http.md) | Network requests |
| [Types & Math](types.md) | Vector, Angle, Color, Vec2 |
| [Enums](enums.md) | Game constants and flags |

## Additional References

- [Target Selection](target-selection.md) — Target filtering and priority helpers
- [Notifications](notifications.md) — In-game notification system
- [Raw Struct Access](raw-struct.md) — Direct schema field access on entities
