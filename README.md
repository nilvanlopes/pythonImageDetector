# Alarm Image Detector

A Python application that monitors the screen for a specific image and plays an alarm sound when detected.

## Features

- Monitors screen for image detection using computer vision
- Plays alarm sound when the target image is found
- Configurable confidence level for image detection

## Requirements

- Python 3.12 or higher
- `uv` package manager

## Installation

1. Clone or download this project
2. Navigate to the project directory:
   ```bash
   cd alarm
   ```
3. Install dependencies using `uv`:
   ```bash
   uv sync
   ```

## Setup

Before running the application, you need to prepare the following files:

1. **popup.png** - Screenshot of the image you want to detect
   - Take a screenshot of the popup or window you want to monitor
   - Save it as `popup.png` in the project directory

2. **alarm.mp3** - Audio file to play as alarm
   - Prepare an MP3 audio file
   - Save it as `alarm.mp3` in the project directory

## Usage

Run the application using `uv`:

```bash
uv run jupyter notebook alarm.ipynb
```

Or activate the virtual environment and run directly:

```bash
source .venv/bin/activate  # On Windows: .venv\Scripts\Activate.ps1
jupyter notebook alarm.ipynb
```

### How it works

1. The program starts monitoring your screen every second
2. It searches for the image `popup.png` on your screen
3. When the image is detected with at least 90% confidence, it:
   - Prints "Image found!"
   - Loads and plays `alarm.mp3`
   - Exits the program

### Configuration

You can adjust the detection parameters in the code:

- **filename**: Change `'popup.png'` to your image file name
- **confidence**: Modify the confidence level (0.0 to 1.0) - higher values require more precise matches

## Requirements File

The project uses `pyproject.toml` for dependency management, which includes:

- **pyautogui**: For screen automation and image detection
- **pygame**: For audio playback
- **opencv-python**: For advanced image matching
- **Pillow**: For image processing support

Dependencies are managed by `uv` which generates a `uv.lock` file for reproducible installs.

## Troubleshooting

- **Image not found**: Make sure `popup.png` is in the project directory and visible on screen
- **Audio not playing**: Verify `alarm.mp3` exists and is in the correct format
- **pyautogui issues**: On some systems, you may need additional dependencies for screenshot functionality

## License

This project is provided as-is for personal use.
