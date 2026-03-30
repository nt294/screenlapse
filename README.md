# screenlapse

A macOS command-line tool that captures screenshots at a set interval and saves them as labeled JPEG frames. Each frame is resized, timestamped with its elapsed time, and given a header bar showing the frame number and time offset. Captures run until you hit Ctrl+C, then all frames are processed and saved to an output directory.

## Usage

```
screenlapse [interval] [output_dir]
```

- `interval` — seconds between captures (default: `1`)
- `output_dir` — output directory (default: `screenlapse_YYYY-MM-DD_HH-MM-SS`)

## Examples

```bash
# Capture every 1 second (default) until Ctrl+C
screenlapse

# Capture every 0.25 seconds
screenlapse 0.25

# Capture every 2 seconds to a specific directory
screenlapse 2 ~/my_captures
```

## Requirements

- macOS (uses `screencapture`)
- Python 3 with Pillow (`pip install Pillow`)
- `gdate` (from coreutils via `brew install coreutils`) for precise timing, falls back to Python if unavailable
