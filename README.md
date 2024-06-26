# Faster R-CNN
### 数据准备
* 下载数据
```
wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtrainval_06-Nov-2007.tar
wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar
wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCdevkit_08-Jun-2007.tar
```
修改configs/_base_/datasets/voc0712.py 里的数据路径

* 模型权重

链接：https://pan.baidu.com/s/1wRshb52WTga0X1-Lv-l27g?pwd=s038 

提取码：s038

保存至work_dirs/faster-rcnn_regnetx-3.2GF_fpn_ms-3x_coco/epoch_12.pth

### 训练模型
* 配置文件：./configs/regnet/faster-rcnn_regnetx-3.2GF_fpn_ms-3x_coco.py
* 模型日志保存地址：修改./configs/_base_/default_runtime.py 里的地址，即之后可视化的logdir
* 训练模型：
```
python tools/train.py ./configs/regnet/faster-rcnn_regnetx-3.2GF_fpn_ms-3x_coco.py
```
### 模型结果可视化
使用tensorboard对模型结果可视化
```
tensorboard --logdir=vis-result --port=6006
```
### 测试模型
```
python tools/test.py configs/regnet/faster-rcnn_regnetx-3.2GF_fpn_ms-3x_coco.py work_dirs/faster-rcnn_regnetx-3.2GF_fpn_ms-3x_coco/epoch_12.pth --show --output-dir vis-result
```

