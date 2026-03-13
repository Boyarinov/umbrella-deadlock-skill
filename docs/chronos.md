# Chronos

High-resolution monotonic timer.

## chronos

### Methods

#### `chronos.nanotime()`

Returns monotonic time in seconds with nanosecond resolution.
Uses `QueryPerformanceCounter` on Windows. Not affected by system clock changes.

**Returns:** `number` — Monotonic time in seconds.
