# Remote sensing image classification
This project focuses on remote sensing image classification using deep learning. 

The current implementations are based on PyTorch and Keras with TensorFlow backend. 

## Overview
In the script, we first conduct image segmentation and divide the image to several objects.
Then, we generate training samples and train a network. The network is used to predict the whole image.
Finally, the object-based post-classification refinement strategy is utilized to refine the classification maps.

### Networks
    [2] Wide Contextual Residual Network - WCRN
    [3] Double Branch Multi Attention Mechanism Network - DBMA
    Residual Network with Average Pooling - ResNet99_avg
    [4] Residual Network - ResNet99

### Requirements
    pytorch==1.1.0 # for PyTorch implementation
    skimage==0.15.0
    sciPy==1.0.0
    sklearn==0.19.1
    keras==2.1.6 # for Keras implementation
    tensorflow==1.9.0 # for Keras implementation

## How to use
### Run main.py
You will see two predicted maps under the current directory when finished.
One is raw classification, and the other is after object-based post-classification refinement (superpixel-based regularization).

This implementation is based on PyTorch using the Wide Contextual Residual Network [2].

### Run demo_keras.py
This implementation is based on Keras with TensorFlow backend using the Double-Branch Multi-Attention Mechanism Network [3].

For this demo, the dafault network is DBMA. By changing the parameter - patch, which controls the window size of each sample, other networks will be applied.

#### Patch and the corresponding network
- patch==5: WCRN
- patch==7: DBMA
- patch==9: ResNet99_avg

## References
  [1] Liu, S., Qi, Z., Li, X. and Yeh, A.G.O., 2019. Integration of Convolutional Neural Networks and Object-Based Post-Classification
Refinement for Land Use and Land Cover Mapping with Optical and SAR Data. Remote Sens., 11(6), p.690. 

  [2] Liu, S., Luo, H., Tu, Y., He, Z. and Li, J., 2018, July. Wide Contextual Residual Network with Active Learning for Remote
Sensing Image Classification. In IGARSS 2018, pp. 7145-7148.

  [3] Ma, W.; Yang, Q.; Wu, Y.; Zhao, W.; Zhang, X. Double-Branch Multi-Attention Mechanism Network for Hyperspectral Image Classification. Remote Sens. 2019, 11, 1307.
  
  [4] Liu, S., and Shi, Q., 2019. Multitask Deep Learning with Spectral Knowledge for Hyperspectral Image Classification. arXiv preprint arXiv:1905.04535v3. 

