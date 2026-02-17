# CircuitPad Board Data

Over-the-air board definition updates for the [CircuitPad](https://github.com/jamesarm97/CircuitPad) iOS app.

## How It Works

CircuitPad ships with bundled board data, but checks this repo for updates so new boards can be added without an App Store review cycle.

The app checks `manifest.json` for the current version number. If it's higher than the local version, the updated JSON files are downloaded and cached.

## Files

| File | Contents |
|------|----------|
| `manifest.json` | Version number and file list |
| `boards.json` | Espressif dev boards, Arduino, STM32, Raspberry Pi Pico, Teensy |
| `boards-extended.json` | M5Stack, LilyGo, Waveshare boards |

## Adding a New Board

1. Add the board definition to the appropriate JSON file
2. Bump the `version` number in `manifest.json`
3. Update the `lastUpdated` date
4. Commit and push

The app will pick up the new data next time a user taps "Check for Board Updates" in Settings.

## Board JSON Format

```json
{
  "id": "unique-board-id",
  "name": "Board Name",
  "manufacturer": "Manufacturer",
  "family": "ESP32",
  "chip": "ESP32-WROOM-32",
  "description": "Short description",
  "specs": { ... },
  "pins": [ ... ],
  "protocolDefaults": { ... },
  "bootPins": { ... },
  "warnings": [ ... ],
  "documentationUrl": "https://..."
}
```

See existing entries for the full pin format.

## License

Copyright © 2026 Armstrong Enterprises. All rights reserved.
