---
# Gameplay Code Rules — applies to src/gameplay/**
- All game values data-driven (@export or Resource .tres)
- No hardcoded numbers — named constants only
- Always use delta for time-based logic
- No direct UI references — signals only
- State changes through state machine
- All public functions typed: func name(p: Type) -> Type:
- Score calculations documented step-by-step in comments
---
