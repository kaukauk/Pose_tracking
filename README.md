# Pose_tracking

Body pose tracking on video clips using MediaPipe Pose, with landmarks and skeleton drawn using OpenCV.

## What it does

- Reads a video file frame by frame and runs MediaPipe Pose on each frame
- Draws the 33 pose landmarks and their connections onto the frame
- Displays the FPS on screen
- `pose_tracking_utils.py` wraps this in a reusable `pose_detector` class that also returns a list of landmark pixel coordinates (`[id, x, y]`)

Sample stock clips (from Pexels) are included in `Pose_videos/`.

## Tech

Python, OpenCV, MediaPipe (legacy `mp.solutions` API), NumPy

## Running it

```bash
pip install opencv-python mediapipe numpy
python pose_estimation_min.py
```

`pose_estimation_min.py` is the minimal, self-contained version and reads a clip from `Pose_videos/`.

`pose_tracking_ex.py` uses the `pose_detector` class, but its video path (`pose_tracking/Pose_videos/...`) assumes it is run from a parent folder; change it to `Pose_videos/pexels-rodnae-productions-7187087.mp4` to run it from the repo root.

Notes:
- The scripts loop until the video ends and do not handle end-of-file cleanly.
- Written in 2021 against an older MediaPipe release.

This was an early learning project for getting familiar with MediaPipe and OpenCV.
