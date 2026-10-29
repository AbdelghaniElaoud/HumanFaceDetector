# Human Face Detector

**Point a webcam at a face and get a live box around it, with no model to train.**

![Python](https://img.shields.io/badge/Python-OpenCV-blue)
![Haar cascade](https://img.shields.io/badge/detector-Haar%20frontal%20face-green)

One script. The default camera. OpenCV's frontal-face cascade. A blue rectangle on every face it finds, until you press `q`.

```
webcam (camera 0)
        |
        v
   grayscale frame
        |
        v
 haarcascade_frontalface_default
        |
        v
 blue box on each face  -->  window "Faces"
```

## Why this exists

A face detector usually means a downloaded weights file, a GPU note, or a call to someone else's API. For a box on a frontal face, that is a lot of setup.

This script uses the cascade OpenCV already ships. Open the camera, scan the frame, draw the box. Nothing else to install beyond OpenCV itself.

## Quick start

A webcam on camera index 0, and Python with OpenCV.

```bash
git clone https://github.com/AbdelghaniElaoud/HumanFaceDetector.git && cd HumanFaceDetector && pip install opencv-python && python main.py
```

1. The window titled **Faces** opens on the live camera.
2. Stand in front of the lens. Each frontal face gets a blue rectangle.
3. Press **q** to close the window and release the camera.

## What you get

- A box on every frontal face in the frame, updated as the camera reads.
- No weights to download. The file is `haarcascade_frontalface_default.xml`, loaded from OpenCV's own data folder.
- A search on the grayscale frame, so the detector is looking at shape, not shirt color.
- A box only when five neighboring hits agree, and only when the face is at least 30 by 30 pixels. Small noise stays off the window.
- One file to edit, `main.py`, if you want a different camera, a thicker box, or a larger minimum face.

The rectangle is blue, 2 pixels thick, in the BGR color `(255, 0, 0)`. The scan uses `scaleFactor=1.1`.

The cascade is the frontal-face one. A face turned hard to the side is outside what this file was built to catch.

## Make it yours

The whole program is [`main.py`](main.py). Fork it, change the box or the camera index, and open a pull request.

If a box on a webcam frame was all you needed, [star Human Face Detector](https://github.com/AbdelghaniElaoud/HumanFaceDetector). [Star history](https://star-history.com/#AbdelghaniElaoud/HumanFaceDetector&Date).

The repository does not ship a license file yet.
