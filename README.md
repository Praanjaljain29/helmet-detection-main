# 🪖 Helmet Detection System

A robust helmet detection system using YOLOv8 and YOLOv8-nano models that specifically detect helmets in videos.

## Features

- ✅ **Helmet-specific detection** in videos using specialized models
- ✅ Uses YOLOv8 models (standard and helmet-trained)
- ✅ Pre-trained models (no training required)
- ✅ High accuracy for helmet identification
- ✅ Easy to use with simple commands

## Installation

1. **Clone or download this repository**

2. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **The YOLO models will be automatically downloaded when you first run the script**

## Usage

### Basic Usage

**Using helmet-specific model (Recommended):**

```bash
python helmet_detector.py --video path/to/your/video.mp4 --model sharathhhhh/safetyHelmet-detection-yolov8
```

**Using standard YOLO models:**

```bash
python helmet_detector.py --video path/to/your/video.mp4
```

### Advanced Usage

#### Use a larger model for better accuracy:

```bash
# YOLOv8 Small (faster)
python helmet_detector.py --video input.mp4 --model yolov8s.pt

# YOLOv8 Medium (balanced)
python helmet_detector.py --video input.mp4 --model yolov8m.pt

# YOLOv8 Large (best accuracy)
python helmet_detector.py --video input.mp4 --model yolov8l.pt

# YOLOv8 Extra Large (maximum accuracy)
python helmet_detector.py --video input.mp4 --model yolov8x.pt
```

#### Adjust confidence threshold:

```bash
# Lower threshold (detect more objects)
python helmet_detector.py --video input.mp4 --conf 0.20

# Higher threshold (detect only high confidence)
python helmet_detector.py --video input.mp4 --conf 0.40
```

#### Specify output file:

```bash
python helmet_detector.py --video input.mp4 --output detected_output.mp4
```

#### All options:

```bash
python helmet_detector.py \
  --video input.mp4 \
  --model yolov8m.pt \
  --conf 0.25 \
  --output output.mp4
```

## Available Models

| Model | Size | Speed | Accuracy | Use Case |
|-------|------|-------|----------|----------|
| YOLOv8n | 6MB | Fastest | Good | Quick processing |
| YOLOv8s | 22MB | Fast | Better | Balanced |
| YOLOv8m | 52MB | Medium | Best Balance | Recommended |
| YOLOv8l | 87MB | Slower | Very Good | High quality |
| YOLOv8x | 136MB | Slowest | Excellent | Maximum quality |

## Requirements

- Python 3.8 or higher
- CUDA-capable GPU (optional, for faster processing)
- 4GB+ RAM

## How It Works

1. The script loads a pre-trained YOLO model (YOLOv8)
2. Each frame of the input video is analyzed
3. The model detects objects including helmets
4. Detections are drawn on the video with bounding boxes and confidence scores
5. The output video is saved with all detections

## File Structure

```
yolo/
├── helmet_detector.py    # Main detection script
├── requirements.txt       # Python dependencies
├── README.md             # This file
└── input.mp4             # Your input video (user provided)
```

## Troubleshooting

### Issue: Slow processing
- Use a smaller model (yolov8n.pt or yolov8s.pt)
- Lower the input video resolution
- Ensure you have a GPU for faster processing

### Issue: Not detecting helmets
- Try different YOLO models (larger models have better accuracy)
- Lower the confidence threshold with `--conf 0.20`
- Ensure helmets are clearly visible in the video

### Issue: Too many false positives
- Increase the confidence threshold with `--conf 0.40`
- Use a larger, more accurate model

## Notes

- Supported video formats: MP4, AVI, MOV, MKV
- The first run will download the YOLO model automatically
- Processing time depends on video length and model size
- GPU acceleration is used automatically if available

## Credits

- YOLOv8 by Ultralytics
- OpenCV for video processing



