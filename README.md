# CAFFE with depthwise convolution layers and float label support

This version of Caffe made two changes to the oringal Caffe: 

## Instructions
1 Depthwise convolution layer for [MobileNet](https://arxiv.org/abs/1704.04861). It is compatible with this Caffe [implementation](https://github.com/shicai/MobileNet-Caffe) of MobileNet, but no longer requires the group convolution trick to implement the depthwise convolution layer. See this [link](https://github.com/yonghenglh6/DepthwiseConvolution) for example prototxt files and other details.


2 Supports labels of float type in LMDB files (converted from `convert_imageset.cpp`). Original Caffe does not support float type for labels for LMDB when your `train.txt` looks like this:
```
/home/foo/caffe/data/finetune/flickr/3860781056.jpg 2.0
/home/foo/caffe/data/finetune/flickr/4559004485.jpg 3.6
/home/foo/caffe/data/finetune/flickr/3208038920.jpg 3.2
/home/foo/caffe/data/finetune/flickr/6170430622.jpg 4.0
/home/foo/caffe/data/finetune/flickr/7508671542.jpg 2.7272
```
This should help regression tasks since HDF5 layers do not support `transform_param`.

