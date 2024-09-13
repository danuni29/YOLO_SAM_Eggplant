# YOLOv8 Image Segmentation
_________

### SAM (Segment Anything Model)

SAM (Segment Anything Model)을 사용하여 이미지에서 객체를 자동으로 분할


### Roboflow

SAM 모델로 분할된 객체를 YOLO Segment 모델에 사용할 수 있는 형식으로 변환하기 위해 Roboflow를 사용

| Label     | 원본데이터 | Train | Validation |
|-----------|-------|-------|------------|
| Egg Plant | 2,941 | 2,100 | 589        |


모델의 성능을 향상시키기 위해 Flip을 사용하여 데이터 증강

| Label     | 증강 후 데이터 | 증강 후 Train | 증강 후 Validation |
|-----------|----------|------------|-----------------|
| Egg Plant | 5,676    | 4,793      | 589             |


### YOLO Segment

data는 data.yaml 파일이 있는 경로로 맞춰준다!

* Train 
```angular2html
yolo segment train data=datasets/data.yaml model=yolov8n-seg.pt epochs=100 imgsz=640
```

source는 test하고자 하는 이미지 파일이 있는 경로로 맞춰준다!
* Test
```angular2html
yolo segment predict model=yolov8n-seg.pt source='datasets/test/images/color_image_0000_png.rf.8dd0479bd0060210e8ef637082a25b0a.jpg'
```

### YOLO 학습결과

------------------------

#### Confusion Matrix
![confusion_matrix](https://github.com/user-attachments/assets/de77d170-4370-4891-9674-3fef293fd0a3)

#### Train & Validation Loss and Precision
![results](https://github.com/user-attachments/assets/caf74985-5b09-428a-b3dd-c37995782cba)

#### F1 Score
![BoxF1_curve](https://github.com/user-attachments/assets/30c8c722-3277-41b0-9f87-40a38e7b6993)

#### Recall
![BoxR_curve](https://github.com/user-attachments/assets/d72bd2e7-615e-49b4-b61a-e654109be99a)

