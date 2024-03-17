# 实验清单

## 实验环境

> Ultralytics YOLOv8.1.9 🚀 Python-3.10.13 torch-2.2.1+cu121 CUDA:1 (NVIDIA GeForce RTX 3090, 24260MiB)

## yolov8s

* > （YOLOv8s summary (fused): 168 layers, 11156544 parameters, 11156528 gradients, 28.6 GFLOPs）
  >
* > model weights:/home/lvzhao_z/YOLO/yolov8s.pt size:21.5M (bs:1)Latency:0.00493s +- 0.00038s fps:202.9
  >

## yolov8n

* > （YOLOv8n summary (fused): 168 layers, 3151904 parameters, 3151888 gradients, 8.7 GFLOPs）
  >
* > model weights:yolov8n.pt size:6.2M (bs:1)Latency:0.00477s +- 0.00045s fps:209.8
  >

## yolov8n-repvit

* > （YOLOv8n-repvit summary (fused): 397 layers, 6844840 parameters, 6844824 gradients, 19.2 GFLOPs）
  >
* > model weights:yolov8n-repvit.pt size:13.4M (bs:1)Latency:0.01092s +- 0.00142s fps:91.5
  >

## YOLOV9中的RepNCSPELAN进行改进yolov8s - c2f

## 更换IOU函数为SIOU，WIOU

# 改进思路

## 对比实验/消融实验

|              |                      yolov8n                      |                       yolov8s                       |                  yolov8n+repvit                  | yolov8n+WIOU | yolov8n+repvit+WIOU |
| :----------: | :-----------------------------------------------: | :-------------------------------------------------: | :-----------------------------------------------: | :----------: | :-----------------: |
|    参数量    | 168 layers, 3151904 parameters, 3151888 gradients | 168 layers, 11156544 parameters, 11156528 gradients | 397 layers, 6844840 parameters, 6844824 gradients |  参数无改变  |     参数无改变     |
|    计算量    |                    8.7 GFLOPs                    |                     28.6 GFLOPs                     |                    19.2 GFLOPs                    |    无改变    |       无改变       |
|   map@0.5   |                      0.84283                      |                       0.85708                       |                      0.85346                      |   0.84451   |                    |
| map@0.5:0.95 |                      0.57522                      |                       0.63214                       |                      0.62661                      |   0.57738   |                    |
