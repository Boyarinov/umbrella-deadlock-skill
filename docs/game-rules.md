# Game Rules

## game_rules

Game rules interface.

### Methods

#### `game_rules.get()`

Returns C_CitadelGameRules as raw_struct for schema field access.

**Returns:** `raw_struct`

#### `game_rules.game_time()`

Returns current game time in seconds.

**Returns:** `number`

#### `game_rules.match_id()`

Returns the current match ID. Returns 0 if Game Coordinator is not ready.

**Returns:** `integer`
