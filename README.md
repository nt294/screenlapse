# screenlapse

A macOS command-line tool that captures screenshots at a set interval and saves them as labeled JPEG frames. Each frame is resized, timestamped with its elapsed time, and given a header bar showing the frame number and time offset. Captures run until you hit Ctrl+C, then all frames are processed and saved to an output directory.

## Usage

```
screenlapse [options]
```

| Flag | Long form | Description | Default |
|------|-----------|-------------|---------|
| `-i` | `--interval` | Capture interval in seconds | `1` |
| `-dir` | `--directory` | Output directory | `screenlapse_<timestamp>` |
| `-w` | `--width` | Output frame width in pixels | `1280` |
| `-d` | `--display` | Display number to capture | current display |
| `-h` | `--help` | Show help message | |

## Examples

```bash
# Capture every 1 second (default) until Ctrl+C
screenlapse

# Capture every 0.25 seconds
screenlapse -i 0.25

# Capture every 2 seconds to a specific directory
screenlapse -i 2 -dir ~/my_captures

# Capture from display 2 at 5 second intervals
screenlapse -d 2 -i 5

# Capture at a wider resolution
screenlapse -w 1920 -dir ~/hires_captures
```

## Requirements

- macOS (uses `screencapture`)
- Python 3 with Pillow (`pip install Pillow`)
- `gdate` (from coreutils via `brew install coreutils`) for precise timing, falls back to Python if unavailable
