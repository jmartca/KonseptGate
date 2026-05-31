KonseptGate
===========

A [Paper](https://papermc.io) plugin designed to make it quick and easy to move players around the world using pressure-plate gates.

This is a fork of the original [KonseptGate by DemmyDemon](https://github.com/DemmyDemon/KonseptGate), updated for modern Paper versions.

## Credits

- **Original concept & code** — [DemmyDemon](https://github.com/DemmyDemon) (Fredrik Vold)
- **Paper 1.21.1 adaptation** — [Claude Code](https://claude.ai/claude-code) by Anthropic

## Changes in this fork

- **Paper 1.21.1 compatibility** — fixed all removed/renamed API calls
- Updated deprecated `Material` enum constants (`STONE_PLATE` → `STONE_PRESSURE_PLATE`, `LONG_GRASS` → `SHORT_GRASS`, `RAILS` → `RAIL`, etc.)
- Replaced removed `Material.getMaterial(int)` with `Material.matchMaterial(String)` — config now uses material names instead of numeric IDs
- Replaced removed `Block.setData(byte)` / `Block.getData()` with the modern `BlockData` API
- Fixed `NullPointerException` crash when a gate's target world is not loaded
- Removed external `KonseptUpdate` dependency
- Added `api-version: '1.21'` to `plugin.yml`
- Replaced Ant build with Maven (`pom.xml`)

## Building

Requires Java 21+ and Maven.

```
mvn package
```

Output: `target/KonseptGate.jar`

## Config

```yaml
verbose: false
underblock: NETHER_BRICKS   # any valid block material name
defaultTarget: ''
defaultCommand: ''
fireEffect: true
missingDestinationMessage: true
gatesPerPage: 9
```

## Commands

```
/kg create <name>              Create a gate at your location
/kg delete <name>              Delete a gate
/kg move <name>                Move a gate to your location
/kg link <from> <to>           Link two gates together
/kg jump <name>                Teleport to a gate
/kg list [page|search]         List all gates
/kg command <name> [cmd]       Attach a command to a gate
/kg ignore                     Toggle ignoring gates for yourself
/kg reload                     Reload config and gates
```

## License

Released under the [Evil Software License](http://fredrikvold.info/ESL.htm) by the original author DemmyDemon (Fredrik Vold).
