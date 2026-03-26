# Path-Specific Rules

Rules in `.claude/rules/` are automatically enforced when editing files in matching paths:

| Rule File | Path Pattern | Enforces |
| ---- | ---- | ---- |
| `gameplay.md` | `src/gameplay/**` | Data-driven values, delta time, no UI references |
| `core.md` | `src/core/**` | Zero allocs in hot paths, thread safety, API stability |
| `ui.md` | `src/ui/**` | No game state ownership, localization-ready, accessibility |
| `audio.md` | `assets/audio/**` | Naming conventions, format requirements, mixing standards |
| `shaders.md` | `assets/shaders/**` | Naming conventions, performance targets, cross-platform rules |
| `prototypes.md` | `prototypes/**` | Relaxed standards, README required, hypothesis documented |
