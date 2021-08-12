# Common Objects Day and Night
Common Objects Day and Night (CODaN) is an image classification dataset for zero-shot day-night domain adaptation / generalization.

The CODaN dataset consists of 15,500 224x224 colour images in 10 classes, with 1,550 images per class. There are 10,000 training images, 500 validation images, 2,500 daytime test images and 2,500 nighttime test images. 

The dataset is collected from the excellent [COCO](https://cocodataset.org/#home), [ImageNet](http://imagenet.stanford.edu) and [ExDark](https://github.com/cs-chan/Exclusively-Dark-Image-Dataset) datasets. All images are filtered and cropped such that they have the same dimensions and are completely mutually exclusive, i.e. do not contain objects of different classes, nor do belong objects to multiple classes.

![CODaN dataset](https://github.com/Attila94/CODaN/raw/main/codan.gif)
  
## Usage
The dataset is packaged as a Torchvision dataset for easy use with Pytorch:
1. Clone repository: `git clone https://github.com/Attila94/CODaN`.
2. Copy `codan.py` to your project folder.
3. Call dataset using `dataset = CODaN(root=<PATH_TO_data_DIR>)`. The `.tar.bz2` files will be extracted automatically. For more arguments see `codan.py`.

For use with other frameworks simply manually extract all `.tar.bz2` files. Splits and classes will be organized in different folders.

## Citation

If you find this dataset useful for your research, please cite

```
@article{lengyel2021zeroshot,
      title={Zero-Shot Domain Adaptation with a Physics Prior}, 
      author={Attila Lengyel and Sourav Garg and Michael Milford and Jan C. van Gemert},
      year={2021},
      eprint={2108.05137},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

## Baselines
We provide weights of a ResNet-18 baseline, as mentioned in [Zero-Shot Day-Night Domain Adaptation with a Physics Prior]().

|                       | Day accuracy (%)| Night accuracy (%) |
| --------------------- | --------------- | ------------------ |
| ResNet-18             | 80.39 +- 0.38   | 48.31 +- 1.33.     |


## Dataset composition
CODaN is composed of images from three datasets. ImageNet images used for the validation or daytime test splits are all sampled from the ImageNet validation set to ensure fair evaluation of ImageNet pre-trained models.
|           | Day                                                          | Night                   |
| --------- | ------------------------------------------------------------ | ----------------------- |
| Bicycle   | COCO [2: 328/35/176]<br />ImageNet [n02835271: 310/7/34]<br />ImageNet [n03792782: 362/8/40] | ExDark [Bicycle: 250]   |
| Car       | COCO [3: 654/33/163]<br />ImageNet [n02814533: 115/5/29]<br />ImageNet [n04037443: 115/6/29]<br />ImageNet [n04285008: 116/6/29] | ExDark [Car: 250]       |
| Motorbike | COCO [4: 1,000/50/250]                                       | ExDark [Motorbike: 250] |
| Bus       | COCO [6: 1,000/50/250]                                       | ExDark [Bus: 250]       |
| Boat      | COCO  [9: 673/34/168]<br />ImageNet [n02951358: 65/3/16]<br />ImageNet [n02981792: 65/3/16]<br />ImageNet [n03095699: 65/3/16]<br />ImageNet [n03673027: 66/3/17]<br />ImageNet [n04612504: 66/4/17] | ExDark [Boat: 250]      |
| Cat       | COCO [17: 1,000/50/250]                                      | ExDark [Cat: 250]       |
| Dog       | COCO [18: 1,000/50/250]                                      | ExDark [Dog: 250]       |
| Bottle    | COCO [44: 274/26/124]<br />ImageNet [n02823428: 179/6/31]<br />ImageNet [n03983396: 236/8/41]<br />ImageNet [n04557648: 161/5/28]<br />ImageNet [n04591713: 150/5/26] | ExDark [Bottle: 250]    |
| Cup       | COCO [46/47: 641/32/160]<br />ImageNet [n02823750: 132/7/33]<br />ImageNet [n07892512: 96/5/24]<br />ImageNet [n07930864: 131/6/33] | ExDark [Cup: 250]       |
| Chair     | COCO [42: 1,000/50/250]                                      | ExDark [Chair: 250]     |
