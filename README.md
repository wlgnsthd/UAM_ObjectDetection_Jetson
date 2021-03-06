# UAM_UOU_ObjectDetection

https://user-images.githubusercontent.com/88171531/169685250-d3ea8430-a4da-4f9f-91c8-68bb6254915d.mp4

https://github.com/dusty-nv/jetson-inference.git

## /home/nvidia/jetson-inference/python/training/detection/ssd/mine

# annotation example
```
<annotation>
    <filename>20220503-090219.jpg</filename>
    <folder>LadderTruck</folder>
    <source>
        <database>LadderTruck</database>
        <annotation>custom</annotation>
        <image>custom</image>
    </source>
    <size>
        <width>1280</width>
        <height>720</height>
        <depth>3</depth>
    </size>
    <segmented>0</segmented>
    <object>
        <name>Ladder</name>
        <pose>unspecified</pose>
        <truncated>0</truncated>
        <difficult>0</difficult>
        <bndbox>
            <xmin>794</xmin>
            <ymin>430</ymin>
            <xmax>946</xmax>
            <ymax>518</ymax>
        </bndbox>
    </object>
    <object>
        <name>Ladder</name>
        <pose>unspecified</pose>
        <truncated>0</truncated>
        <difficult>0</difficult>
        <bndbox>
            <xmin>981</xmin>
            <ymin>426</ymin>
            <xmax>1031</xmax>
            <ymax>510</ymax>
        </bndbox>
    </object>
</annotation>
```
# file tree
jetson-inference/python/training/detection/ssd / models/Laddertruck,mobilenet~.pth
                                               /data/Laddertruck/(Annotaions,ImageSets,JPEGImages),labels.txt

![20220529_214138](https://user-images.githubusercontent.com/88171531/170869440-80374f9f-1b47-4eda-bd29-0b02a2d5fd42.jpg)




```
root@ubuntu:/jetson-inference/python/training/detection/ssd# python3 train_ssd.py --dataset-type=voc --data=data/Laddertruck --model-dir=models/Laddertruck --batch-size=16 --workers=1 --epochs=500
2022-05-18 04:30:12 - Using CUDA...
2022-05-18 04:30:12 - Namespace(balance_data=False, base_net=None, base_net_lr=0.001, batch_size=16, checkpoint_folder='models/Laddertruck', dataset_type='voc', datasets=['data/Laddertruck'], debug_steps=10, extra_layers_lr=None, freeze_base_net=False, freeze_net=False, gamma=0.1, lr=0.01, mb2_width_mult=1.0, milestones='80,100', momentum=0.9, net='mb1-ssd', num_epochs=500, num_workers=1, pretrained_ssd='models/mobilenet-v1-ssd-mp-0_675.pth', resume=None, scheduler='cosine', t_max=100, use_cuda=True, validation_epochs=1, weight_decay=0.0005)
2022-05-18 04:30:12 - Prepare training datasets.
2022-05-18 04:30:12 - VOC Labels read from file: ('BACKGROUND', 'ladder', 'truck')
2022-05-18 04:30:12 - Stored labels into file models/Laddertruck/labels.txt.
2022-05-18 04:30:12 - Train dataset size: 92
2022-05-18 04:30:12 - Prepare Validation datasets.
2022-05-18 04:30:12 - VOC Labels read from file: ('BACKGROUND', 'ladder', 'truck')
2022-05-18 04:30:12 - Validation dataset size: 6
2022-05-18 04:30:12 - Build network.
2022-05-18 04:30:12 - Init from pretrained ssd models/mobilenet-v1-ssd-mp-0_675.pth
2022-05-18 04:30:12 - Took 0.14 seconds to load the model.
2022-05-18 04:30:17 - Learning rate: 0.01, Base net learning rate: 0.001, Extra Layers learning rate: 0.01.
2022-05-18 04:30:17 - Uses CosineAnnealingLR scheduler.
2022-05-18 04:30:17 - Start training from epoch 0.
/usr/local/lib/python3.6/dist-packages/torch/optim/lr_scheduler.py:134: UserWarning: Detected call of `lr_scheduler.step()` before `optimizer.step()`. In PyTorch 1.1.0 and later, you should call them in the opposite order: `optimizer.step()` before `lr_scheduler.step()`.  Failure to do this will result in PyTorch skipping the first value of the learning rate schedule. See more details at https://pytorch.org/docs/stable/optim.html#how-to-adjust-learning-rate
  "https://pytorch.org/docs/stable/optim.html#how-to-adjust-learning-rate", UserWarning)
/usr/local/lib/python3.6/dist-packages/torch/nn/_reduction.py:42: UserWarning: size_average and reduce args will be deprecated, please use reduction='sum' instead.
  warnings.warn(warning.format(ret))
2022-05-18 04:30:39 - Epoch: 0, Validation Loss: 7.1450, Validation Regression Loss 2.7278, Validation Classification Loss: 4.4172
2022-05-18 04:30:39 - Saved model models/Laddertruck/mb1-ssd-Epoch-0-Loss-7.144967079162598.pth
2022-05-18 04:30:45 - Epoch: 1, Validation Loss: 5.9035, Validation Regression Loss 2.5426, Validation Classification Loss: 3.3609
2022-05-18 04:30:45 - Saved model models/Laddertruck/mb1-ssd-Epoch-1-Loss-5.9035186767578125.pth
2022-05-18 04:30:50 - Epoch: 2, Validation Loss: 5.5850, Validation Regression Loss 2.4618, Validation Classification Loss: 3.1232
```
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fwlgnsthd&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)
