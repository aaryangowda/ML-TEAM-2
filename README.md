# Violence Detection System

This project detects violent behavior in videos using YOLOv8, MediaPipe, and OpenCV.

## Features
- **YOLOv8**: Detects objects and people.
- **MediaPipe**: Tracks body poses.
- **OpenCV**: Handles video input and frame processing.

## Installation

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <your-project-folder>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have a video file for analysis, or adjust the path in `mainsfin.py`.

## Usage

Run the script:
```bash
python mainsfin.py
```

## File Structure
- `mainsfin.py`: Core script handling video input, YOLO detection, and MediaPipe pose tracking.
- `requirements.txt`: Contains the required packages.

## Dependencies
Make sure you have Python 3.8+ installed.

## Future Improvements
- Enhance violence classification with ST-GCN.
- Add real-time video stream support.

---

Happy coding!

