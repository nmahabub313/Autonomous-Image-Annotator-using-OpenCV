# 3D Synthetic Dataset Generator for Object Detection and Segmentation

This project creates synthetic image datasets using realistic 3D models rendered from multiple angles. The generated images are automatically processed to produce segmentation masks and YOLO-compatible labels, making them ready for training object detection and segmentation models like YOLOv8.

## Features

- 3D rendering with Blender + Cycles from multiple camera angles
- Automatic mask generation using OpenCV
- Contour extraction and YOLO label formatting
- Supports YOLOv8 segmentation model training
- Fully automated pipeline (Colab + Python scripts)

## Real-World Applications

- Robotics and autonomous systems (where labeled real-world data is limited)
- Industrial object inspection using synthetic samples
- Augmenting real datasets for improved generalization

## Pipeline Overview

1. **3D Model Rendering**  
   - Blender 3D with Cycles engine  
   - Rendered from multiple viewpoints  
   - Transparent or monocolor background  

2. **Mask & Contour Extraction**  
   - OpenCV used to create binary masks  
   - Extract object contours  
   - Normalize coordinates for YOLO format  

3. **Label Generation**  
   - Outputs YOLOv8 segmentation labels (`.txt` files)

4. **Training**  
   - Model training using [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)  
   - Google Colab or local training supported

## Dependencies

- [Blender](https://www.blender.org)
- Python 3.x
- OpenCV (`cv2`)
- NumPy
- tqdm
- Ultralytics YOLOv8 (`pip install ultralytics`)

## How to Run

1. **Render Images (in Blender)**  
   Use your `.blend` file with cameras and lighting set up. Output PNGs with transparent or plain background.

2. **Upload to Colab or Local Folder**  
   Organize images into `images/train`.

3. **Run Label Generation Script**  
   ```bash
   python generate_labels.py
