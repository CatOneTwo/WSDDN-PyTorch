# WSDDN PyTorch
This repository contains the PyTorch implementation of paper [`Weakly Supervised Deep Detection Networks`](https://arxiv.org/abs/1511.02853) (CVPR 2016)

Implementation differences: Spatial regulariser isn't added

## Architecture
![WSSSN](https://raw.githubusercontent.com/CatOneTwo/Picbed_PicGo/master/img/WSDDN.png)

## Contents
1. [Requirements: software](#requirements-software)
2. [Requirements: hardware](#requirements-hardware)
3. [Basic installation](#basic-installation)
4. [Installation for training and testing](#installation-for-training-and-testing)
5. [Extra Downloads (selective search)](#extra-downloads-selective-search)
6. [Extra Downloads (ImageNet models)](dxtra-downloads-imageNet-models)
7. [Usage](#usage)


## Requirements: software
- python3 packages and versions used (listed using freeze frin pip):
    - cycler==0.10.0
    - Cython==0.29.16
    - joblib==0.14.1
    - kiwisolver==1.2.0
    - matplotlib==3.2.1
    - numpy==1.18.2
    - opencv-python==4.2.0.34
    - packaging==20.3
    - Pillow==6.1.0
    - protobuf==3.11.3
    - pycocotools==2.0.0 (available from pip)
    - pyparsing==2.4.7
    - python-dateutil==2.8.1
    - PyYAML==5.3.1
    - scikit-learn==0.22.2.post1
    - scipy==1.4.1
    - six==1.14.0
    - sklearn==0.0
    - tensorboardX==2.0
    - torch==1.2.0+cu92
    - torchvision==0.4.0+cu92
## Requirements: hardware
- We used cuda 9.0 and cudnn 7.0
    - We used an Nvidia GeForce GTX with 10.9G of memory. But it shold be ok to train if you have a GPU with at least 8Gb.
    - **NOTICE**: different versions of Pytorch have different memory usages.

## Basic installation
Clone this repository
```shell
```
## Installation for training and testing
1. Create a "data" folder in  $WSDDN_ROOT and enter in this folder
    ```Shell
    cd $WSDDN_ROOT
    mkdir data
    cd data
    ```
2. Download the training, validation, test data, and VOCdevkit
    ```Shell
    wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtrainval_06-Nov-2007.tar
    wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar
    ```
    Optional, normally faster to download, links to VOC (from darknet):
    ```Shell
    wget https://pjreddie.com/media/files/VOCtrainval_06-Nov-2007.tar
    wget https://pjreddie.com/media/files/VOCtest_06-Nov-2007.tar
    ```
3. Extract all of these tars into one directory named `VOCdevkit`
    ```Shell
    tar xvf VOCtrainval_06-Nov-2007.tar
    tar xvf VOCtest_06-Nov-2007.tar
    ```

4. Download the VOCdevkit evaluation code adapted to octave
    ```Shell
    wget http://inf.ufrgs.br/~lfazeni/CVPR_deepvision2020/VOCeval_octave.tar
    ```

5. Extract VOCeval_octave
    ```Shell
    tar xvf VOCeval_octave.tar
    ```

6. Download pascal annotations in the COCO format
    ```Shell
    wget http://inf.ufrgs.br/~lfazeni/CVPR_deepvision2020/coco_annotations_VOC.tar
    ```
7. Extract the annotations
    ```Shell
    tar xvf coco_annotations_VOC.tar
    ```

8. It should have this basic structure
    ```Shell
    $VOC2007/                           
    $VOC2007/annotations
    $VOC2007/JPEGImages
    $VOC2007/VOCdevkit        
    # ... and several other directories ...
    ```
9. [Optional] download and extract PASCAL VOC 2012.
    ```Shell
    wget http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar
    tar xvf VOCtrainval_11-May-2012.tar
    ```
    or
    ```Shell
    wget https://pjreddie.com/media/files/VOCtrainval_11-May-2012.tar
    tar xvf VOCtrainval_11-May-2012.tar
    ```
    **Observation:** The  `2012 test set` is only available in the [PASCAL VOC Evaluation Server](http://host.robots.ox.ac.uk:8080/) to download. You must create a user and download it by yourself. After downloading, you can extract it in the data folder.
## Extra Downloads (selective search)
1. Download the proposals data generated by selective search to data folder
    ```Shell
    wget http://inf.ufrgs.br/~lfazeni/CVPR_deepvision2020/selective_search_data.tar
    ```
2. Extract the proposals
    ```Shell
    tar xvf selective_search_data.tar
    ```

## Extra Downloads (ImageNet models)
1. Download the pre-trained VGG16 model to data folder
    ```Shell
    wget http://inf.ufrgs.br/~lfazeni/CVPR_deepvision2020/pretrained_model.tar
    ```
2. Extract the pre-trained VGG16 model 
    ```Shell
    tar xvf pretrained_model.tar
    ```
## Usage
