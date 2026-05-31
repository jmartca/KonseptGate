## KonseptGate 0.6.3 — Paper 1.21.1 port

Drop `KonseptGate.jar` into your server's `plugins/` folder.

**Requires:** Paper 1.21.1, Java 21+

### What changed from the original
- Fixed all removed/renamed Material enum constants
- Fixed removed `Block.setData()` / `getData()` API
- Fixed `NullPointerException` when a gate's target world is not loaded
- Config now uses material name instead of numeric block ID (`underblock: IRON_BLOCK` instead of `underblockID: 42`)
- Added `api-version: 1.21` to plugin.yml

### Config note
If upgrading from the original plugin, update your `config.yml`:
```yaml
# Old:
underblockID: 42
# New (use the material name, e.g. IRON_BLOCK for ID 42):
underblock: IRON_BLOCK
```

**Original plugin by [DemmyDemon](https://github.com/DemmyDemon/KonseptGate) — adaptation by [Claude Code](https://claude.ai/claude-code)**
