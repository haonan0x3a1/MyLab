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

## yolov8n-C2f-RFCBAMConv

```python
import warnings
warnings.filterwarnings('ignore')
from ultralytics import YOLO

if __name__ == '__main__':
    model = YOLO('/home/lvzhao_z/YOLO/ultralytics-main/ultralytics/cfg/models/v8/yolov8n-C2f-RFCBAMConv.yaml')
    model.train(data='/home/lvzhao_z/YOLO/ultralytics-main/data/data.yaml',
                cache=True,
                imgsz=640,
                epochs=200,
                batch=32,
                close_mosaic=10,
                workers=8,
                device='2',
                #optimizer='SGD', # using SGD
                # resume='', # last.pt path
                # amp=False, # close amp
                # fraction=0.2,
                project='runs/train',
                name='exp',
                )
```

## yolov8s-C2f-RFCBAMConv

## YOLOV9中的RepNCSPELAN进行改进yolov8s - c2f

## yolov8s efficientVIT

## 更换IOU函数为SIOU

## yolov8s unireplknet

## 增添注意力机制

### locawindowAttention
