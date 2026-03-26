---
# UI Rules — applies to src/ui/**
- No game state ownership — UI reads via signals, never writes
- All text in tr() for localization
- Minimum 44x44px click targets
- Support keyboard + mouse + gamepad
- Theme resources for all styling
- Signals for all UI → game communication
---
