# Dataset
[1]. Helmet Detection: [Link](https://universe.roboflow.com/checkhelmet/helmetcheck/dataset/1)  
[2]. Glasses Detection: [Link](https://universe.roboflow.com/pupildec/glasses-detection-1k2dp)  

# Project Structure
```
dataset/
    train/images/
    valid/images/
    test/images/
yolov5/
    train.py
    export.py
    README.md
models/
```

# Configuration (data.yaml example)
```yaml
train: ../../dataset/train/images
val: ../../dataset/valid/images
```

# Training Instructions
To train the model, run the following command:
```bash
python train.py --img 640 --batch 32 --epochs 25 --data ../dataset/data.yaml --weights yolov5s.pt 
```
or
```bash
python train.py --img 416 --batch 32 --epochs 12 --data ../dataset/data.yaml --weights yolov5s.pt
```

# Convert to TFLite
To convert the model to TFLite format, use the command:
```bash
python export.py --weights runs/train/exp6/weights/best.pt --include tflite --int8 --img 416 --data ../dataset/data.yaml
```