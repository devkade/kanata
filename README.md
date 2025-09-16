# Kanata Keyboard Configuration

A Miryoku-inspired keyboard remapping configuration for [Kanata](https://github.com/jtroo/kanata), featuring home row modifiers and layered keyboard layouts.

## Features

- **Home Row Modifiers**: Transform ASDF and JKL; into modifiers when held
- **7 Specialized Layers**: Symbols, navigation, media, numbers, functions, and mouse control
- **Tap-Hold Behavior**: Keys have different functions when tapped vs held (150ms timing)
- **macOS Integration**: LaunchAgent configuration for system service

## Layer Overview

| Layer | Trigger | Purpose |
|-------|---------|---------|
| `base` | Default | QWERTY with home row mods |
| `symbols` | Esc/Enter hold | Special characters and symbols |
| `nav` | Space hold | Arrow keys, copy/paste, window nav |
| `media` | Return hold | Volume, brightness, media controls |
| `num` | Backspace hold | Number pad and math symbols |
| `func` | Alt hold | Function keys F1-F12 |
| `mouse` | Shift hold | Mouse movement and scroll |

## Installation

1. Install Kanata via Homebrew:
   ```bash
   brew install kanata
   ```

2. Test the configuration:
   ```bash
   kanata --check -c kanata.kbd
   ```

3. Run temporarily (requires sudo):
   ```bash
   sudo kanata -c kanata.kbd
   ```

4. Install as system service:
   ```bash
   # Update config path in plist file
   cp com.example.kanata.plist ~/Library/LaunchAgents/
   launchctl load ~/Library/LaunchAgents/com.example.kanata.plist
   ```

## Key Mappings

### Home Row Modifiers
- `a` → Cmd when held, `a` when tapped
- `s` → Alt when held, `s` when tapped  
- `d` → Shift when held, `d` when tapped
- `f` → Ctrl when held, `f` when tapped
- `j` → Ctrl when held, `j` when tapped
- `k` → Shift when held, `k` when tapped
- `l` → Alt when held, `l` when tapped
- `;` → Cmd when held, `;` when tapped

### Layer Access
- `Space` + hold → Navigation layer
- `Esc/Enter` + hold → Symbols layer
- `Backspace` + hold → Numbers layer
- `Return` + hold → Media layer
- `Alt` + hold → Function keys
- `Shift` + hold → Mouse layer

## Troubleshooting

Check service status:
```bash
launchctl list | grep kanata
```

View logs:
```bash
# Output logs
tail -f /Library/Logs/Kanata/kanata.out.log

# Error logs  
tail -f /Library/Logs/Kanata/kanata.err.log
```

Restart service:
```bash
launchctl unload ~/Library/LaunchAgents/com.example.kanata.plist
launchctl load ~/Library/LaunchAgents/com.example.kanata.plist
```

## Configuration

Edit `kanata.kbd` to customize:
- Timing variables (`tap-time`, `hold-time`)
- Key mappings and aliases
- Layer definitions
- Add new layers or modify existing ones

## License

Personal configuration - modify as needed.