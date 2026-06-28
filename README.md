# Ghost / Invisibility Mode

A webcam-based invisibility effect using Python, OpenCV, NumPy, and optional MediaPipe hand tracking.

The app captures a clean background, then replaces part of the live camera frame with that saved background so the person inside the portal area appears to vanish.

## Files

- `main.py` - app entrypoint, camera setup, calibration, keyboard controls
- `engine.py` - background model, segmentation, hand tracking, portal rendering, HUD
- `requirements.txt` - Python dependencies

## Install

Use Python 3.8 or newer.

```powershell
cd C:\invisible_space_project
python -m pip install -r requirements.txt
```

## Run

```powershell
python main.py
```

If you have multiple cameras, pass the camera index:

```powershell
python main.py 1
```

## How To Use

1. Start the app.
2. During the 3-second calibration, step completely out of the camera frame.
3. Come back and stand inside the portal box.
4. Press `Space` to vanish or reappear.

If you are still visible, press `R`, step out of frame again, wait for calibration to finish, then press `Space`.

## Controls

| Key | Action |
| --- | --- |
| `Space` | Toggle vanish/reappear |
| `B` | Show or hide the manual portal box |
| `R` | Recalibrate the background |
| `S` | Save a screenshot |
| `Q` or `Esc` | Quit |

## MediaPipe Notes

If MediaPipe hand tracking works on your computer, you can create a portal by showing both hands spread apart and toggle invisibility by pinching thumb and index finger.

If MediaPipe does not work, the project still runs with keyboard controls. Use `B` for the box and `Space` to vanish.

## Tips

- Keep the camera still.
- Make sure nobody is in frame during calibration.
- Use a background that does not move.
- Good lighting improves the effect.
- Recalibrate with `R` whenever the camera moves or the lighting changes.
