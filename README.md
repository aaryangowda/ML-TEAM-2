# Gender, Crowd, and Anomaly Detection Project

## Overview
This project combines gender detection, crowd detection, and anomaly detection capabilities using advanced computer vision and deep learning techniques. It classifies faces as male or female, detects crowds, and identifies abnormal or suspicious behavior.

## Features
- **Real-time gender detection** from video input.
- **Crowd detection** using YOLOv8 for accurate object recognition.
- **Pose tracking** with MediaPipe to understand human movement.
- **Anomaly detection** using behavior analysis models, flagging unusual activities (e.g., violence, running, sudden movements).
- **Real-time processing** for immediate analysis and alerting.

## Anomaly Detection Details
The anomaly detection module works by:
1. **Pose Analysis:** Using MediaPipe to track human posture and movements.
2. **Crowd Density Detection:** Identifying unusually dense areas with YOLOv8.
3. **Behavior Recognition:** Integrating ST-GCN (Spatial-Temporal Graph Convolutional Network) to recognize violent or suspicious behavior patterns.
4. **Alert Triggering:** Automatically flags moments with high anomaly confidence scores.

Anomalies include:
- Fights, aggressive behavior
- Running or erratic movements
- Sudden crowd dispersion or clustering

### YOLOv8 Setup
YOLOv8 (You Only Look Once version 8) is a state-of-the-art object detection model from Ultralytics. It detects people and tracks their movements.

1. **Install YOLOv8:**
   ```bash
   pip install ultralytics
   ```

2. **Download pre-trained weights:**
   ```bash
   yolo download model=yolov8n.pt
   ```

3. **Use YOLO in the project:**
   ```python
   from ultralytics import YOLO
   model = YOLO('yolov8n.pt')
   results = model.predict('input_video.mp4', show=True)
   ```

4. **Fine-tuning YOLOv8:**
   - To improve accuracy on specific datasets (e.g., crowd behavior data):
   ```bash
   yolo train data=custom_dataset.yaml model=yolov8n.pt epochs=50 imgsz=640
   ```
   - Adjust hyperparameters like `epochs`, `batch-size`, and `imgsz` for better performance.

### ST-GCN Setup
ST-GCN (Spatial-Temporal Graph Convolutional Network) analyzes human keypoints over time to detect abnormal behavior patterns.

1. **Clone the ST-GCN repository:**
   ```bash
   git clone https://github.com/yysijie/st-gcn
   cd st-gcn
   pip install -r requirements.txt
   ```

2. **Prepare the model:**
   ```bash
   python main.py demo --model model_path.pt --video input_video.mp4
   ```

3. **Fine-tuning ST-GCN:**
   - Train on a custom action dataset:
   ```bash
   python main.py train --config config/custom_config.yaml
   ```
   - Adjust learning rates, batch sizes, and keypoint configurations in `config.yaml`.

### Dataset Preparation
For both models to achieve higher accuracy on anomaly detection tasks, preparing a custom dataset is key:
- **Collect videos/images** of normal and abnormal behaviors.
- **Annotate data** using tools like [LabelImg](https://github.com/heartexlabs/labelImg) for YOLO (bounding boxes) or COCO format.
- **Split data** into training, validation, and test sets (e.g., 70/20/10 split).
- **Convert dataset format** for YOLO:
   ```yaml
   train: path/to/train
   val: path/to/val
   test: path/to/test

   nc: 1
   names: ['person']
   ```
- **For ST-GCN**, ensure keypoint data is provided in `.json` format with timestamped sequences.

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
   - ST-GCN implementation: Follow installation from [ST-GCN repo](https://github.com/yysijie/st-gcn)

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
   - Anomalies flagged in real-time with visual indicators.

## Configuration
You can customize the configuration file (`config.yaml`):
- Input source (file or webcam)
- Confidence thresholds
- Anomaly detection sensitivity
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
- Implement a notification system (e.g., email or SMS alerts) when anomalies are detected.

## Contributing
Contributions are welcome! Feel free to open an issue or pull request to suggest improvements.

## License
This project is licensed under the MIT License.

---

Happy coding!

