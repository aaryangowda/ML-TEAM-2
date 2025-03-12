# Gender Detection Project

## Overview
This project focuses on detecting gender from images or video streams using advanced computer vision techniques. It leverages deep learning models to classify faces as male or female accurately.

## Features
- **Real-time gender detection** from video input.
- **Image-based classification** for photos.
- **High accuracy** leveraging pre-trained deep learning models.

## Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd gender_detection
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
   - Face detection model (e.g., Haar cascades or MTCNN)
   - Gender classification model (e.g., a pre-trained CNN)

## Usage

1. **Run the project:**
   ```bash
   python gender_detection.py
   ```

2. **Provide video input:**
   - By default, it uses your webcam. You can change this to process an image or video file by passing the filename as an argument.

3. **Output:**
   - Detected faces are labeled as **Male** or **Female**.

## Configuration
You can customize the configuration file (`config.yaml`):
- Input source (file or webcam)
- Confidence thresholds
- Model paths
- Output options

## Performance Considerations
- Ensure GPU support for faster inference (CUDA for NVIDIA GPUs).
- Optimize image resolution for performance without losing accuracy.

## Future Improvements
- Add age detection alongside gender classification.
- Implement multi-face tracking for crowded scenes.
- Support non-binary classification models.

## Contributing
Contributions are welcome! Feel free to open an issue or pull request to suggest improvements.

## License
This project is licensed under the MIT License.

---
**Author:** Aaryan Gowda

Happy coding!
