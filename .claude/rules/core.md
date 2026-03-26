---
# Core Systems Rules — applies to src/core/**
- Zero allocations in _process() / _physics_process()
- Thread-safe shared state access
- Changing Autoload interfaces requires discussion
- All managers handle null, empty, overflow
- Signal connections cleaned up on tree_exiting
---
