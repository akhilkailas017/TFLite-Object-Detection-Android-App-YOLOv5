# TFLite-Object-Detection-Android-App-YOLOv5

**First Reffer https://github.com/akhilkailas2001/Object-Detection-using-Yolov5.git<br>**
**It is the continuation of Object Detection using Yolov5**

A. Main Idea

- Train yolov5 model
- Convert yolov5 (.pt model) into a tensorflow model(.pb file)
- Convert tensorflow model (.pb model) to tflite model.
- Download and install Android Studio
- Build and run your Object detection App.

B. Main Steps for Creating Android App

- first open yolov5 folder in command prompt then type "python export.py --data your_yaml_file.yaml --weights runs/train/exp/weights/best.pt --include tflite --img 640" for exporting the weight to tensorflow lite.
- it will create a .tflite file in yolov5/runs/train/exp/weights this location.
- test our exported data by typing "python detect.py --weights runs/train/exp/weights/best-fp16.tflite --img 640 --source data/images/"
- copy android folder to yolov5 folder.
- goto location android\app\src\main\assets and paste the best-fp16.tflite file created during exporting in yolov5.
- goto location android\app\src\main\assets and edit customclasses.txt file by adding our class name in order.type only one class name in one line.
- goto location android\app\src\main\java\org\tensorflow\lite\examples\detection\tflite then edit DetectorFactory.java file by comparing with the DetectorFactory.java that i given then save the file.
- download and install android studio then run the program.

C. Yolo Commands

- python train.py --img 415 --batch 16 --epochs 30 --data dataset.yaml --weights yolov5s.pt --cache
- python train.py --img 640 --batch 8 --epochs 100 --data mat.yaml --weights yolov5s.pt --cache
- python detect.py --source data/images/ --weights runs/train/exp/weights/best.pt
- python detect.py --source data/images/ --weights runs/train/exp/weights/best.pt --conf 0.50
- python export.py --data mat.yaml --weights runs/train/exp/weights/best.pt --include tflite --img 640
- python detect.py --weights runs/train/exp/weights/best-fp16.tflite --img 640 --source data/images/

D. References
- python : https://www.python.org/downloads/
- labelImg : https://github.com/tzutalin/labelImg
- xml to yolo converter : https://github.com/bjornstenger/xml2yolo
- yolov5 : https://github.com/ultralytics/yolov5
- labelimg annotation tutorial : https://youtu.be/Tlvy-eM8YO4
- yolov5 training tutorial : https://youtu.be/80Q3HIBy7Qg
- yolov5 app making tutorial : https://youtu.be/ROn1_O2zEtk
- android file download : https://github.com/AarohiSingla/TFLite-Object-Detection-Android-App-Tutorial-Using-YOLOv5.git
