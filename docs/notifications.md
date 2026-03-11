# Notifications

### `notif_args`

```lua
---@alias notif_args {
  id?: string,
  duration?: number,
  precise_timer?: number,
  timer?: number,
  primary_text?: string,
  primary_image?: string|integer,
  secondary_image?: string|integer,
  secondary_text?: string,
  active?: boolean,
  position?: Vector,
  sound?: string,
  hero?: integer,
}
```

### `Notification(args)`

Creates and displays a notification.
Field notes:
- `timer` takes priority over `precise_timer` (if both present, `timer` wins).
- `sound` only plays if the notification was accepted by the notification manager.
- `hero` field is currently non-functional (no-op). When present, `primary_text` and `primary_image` are also skipped.
- `position` accepts Vector userdata for world-space positioning.
- Always returns nil. No error on bad input.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `args` | `notif_args` |  |

**Returns:** `nil`
