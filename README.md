# Drone-vs-Bird-Detection-using-YOLOv4-YOLOv5-YOLOv6-YOLOv7-and-YOLOv8
This project provides a comprehensive comparison of multiple YOLO versions applied to a Drone/Bird dataset already annotated in the YOLO format. The objective is to train different models, evaluate their performance, and deliver a clean, reproducible, and GitHub-ready project structure.
# Content of the data.yaml file
To place in: dataset/data.yaml
# Dependency installation
pip install -r requirements.txt

The YOLO frameworks used in the project will be installed automatically.
# Train each version of YOLO
YOLOv5:

cd yolov5

python train.py --img 640 --batch 16 --epochs 100 --data ../dataset/data.yaml --weights yolov5s.pt

YOLOv7:

cd yolov7

python train.py --img 640 --batch 16 --epochs 100 --data ../dataset/data.yaml --weights yolov7.pt

YOLOv8:

cd yolov8

yolo detect train data=../dataset/data.yaml model=yolov8s.pt epochs=100 imgsz=640

(The YOLOv4 and YOLOv6 commands are added later in the corresponding folders.)
# Detection
YOLOv5:

python detect.py --weights runs/train/exp/weights/best.pt --source 0

YOLOv8:

yolo detect predict model=runs/detect/train/weights/best.pt source=0

# Expected results
