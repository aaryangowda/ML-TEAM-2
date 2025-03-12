# Gender and Crowd Detection Project

## Overview
This project combines gender detection and crowd detection capabilities using advanced computer vision techniques. It leverages deep learning models to classify faces as male or female and detect crowds in video streams.

## Features
- **Real-time gender detection** from video input.
- **Crowd detection** using YOLOv8 for object recognition.
- **Pose tracking** with MediaPipe to understand human movement.
- **High accuracy** leveraging pre-trained deep learning models.
- **Real-time processing** for immediate analysis and response.

## Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd detection_project
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Linux/Mac
   venv\Scripts\activate      # On Windows
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download pretrained models:**
   - YOLOv8 weights: Download from [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
   - MediaPipe: Install via `pip install mediapipe`
   - Gender classification model (e.g., pre-trained CNN)

## Usage

1. **Run the project:**
   ```bash
   python mainsfin2.py
   ```

2. **Provide video input:**
   - By default, it uses your webcam. You can change this to process an image or video file by passing the filename as an argument.

3. **Output:**
   - Detected faces labeled as **Male** or **Female**.
   - Crowd detection with recognized people and activities highlighted.

## Configuration
You can customize the configuration file (`config.yaml`):
- Input source (file or webcam)
- Confidence thresholds
- Model paths
- Output preferences

## Performance Considerations
- Ensure GPU support for faster inference (CUDA for NVIDIA GPUs).
- Optimize image and video resolution for performance without losing accuracy.

## Future Improvements
- Add age detection alongside gender classification.
- Implement multi-face tracking for crowded scenes.
- Support non-binary classification models.
- Enhance behavior analysis with more advanced activity recognition.

## Contributing
Contributions are welcome! Feel free to open an issue or pull request to suggest improvements.

## License
This project is licensed under the MIT License.

---

Happy coding!

