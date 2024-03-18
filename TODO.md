# 实验清单

## 实验环境

> Ultralytics YOLOv8.1.9 🚀 Python-3.10.13 torch-2.2.1+cu121 CUDA:1 (NVIDIA GeForce RTX 3090, 24260MiB)

# 改进思路

## 对比实验/消融实验

|              |                      yolov8n                      |                   yolov8n+WIOU                   |                       yolov8s                       |                  yolov8n+repvit                  |                yolov8n+repvit+WIOU                |            yolov8n+repvit+WIOU+dyhead            |
| :----------: | :-----------------------------------------------: | :-----------------------------------------------: | :-------------------------------------------------: | :-----------------------------------------------: | :-----------------------------------------------: | :-----------------------------------------------: |
|    参数量    | 168 layers, 3151904 parameters, 3151888 gradients | 168 layers, 3151904 parameters, 3151888 gradients | 168 layers, 11156544 parameters, 11156528 gradients | 397 layers, 6844840 parameters, 6844824 gradients | 397 layers, 6844840 parameters, 6844824 gradients | 432 layers, 7315044 parameters, 7315028 gradients |
|    计算量    |                    8.7 GFLOPs                    |                    8.7 GFLOPs                    |                     28.6 GFLOPs                     |                    19.2 GFLOPs                    |                    19.2 GFLOPs                    |                    20.8 GFLOPs                    |
|   map@0.5   |                      0.84283                      |                      0.84451                      |                       0.85708                       |                      0.85346                      |                      0.85849                      |                                                  |
| map@0.5:0.95 |                      0.57522                      |                      0.57738                      |                       0.63214                       |                      0.62661                      |                      0.62459                      |                                                  |
