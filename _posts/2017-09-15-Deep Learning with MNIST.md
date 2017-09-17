---
layout: post
title: Deep Learning  on MNIST Datasets

---

Deep Learning is the sublte extraction of machine learning into domains of feature extraction via a more deep stack of neural network.Machine Learning is science of learning the essence of data given extracted features but the method seems to be less computationally feasible as the number of features increase dramatically,like in images.eg, a 28*28 image would have a total of 784 features,i.e. the 784 pixel values.So we try to train models that learn the important features of the datasets themselves,rather than hogging on the entire feature space.

<div class="divider"></div>

Convolutional Neural Nets are the state-of-the-art techniques to learn from large feature space type datasets. They work extremely well with Images,and can be used for a variety of tasks such as Classification,Image localization and detection.They are primarily inspired by the mammalian Visual Cortex after the experiments performed by hubel and weasel!
[here](https://www.google.co.in/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwinue3B-azWAhWBO48KHULCB_4QtwIIKDAA&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DFTr3n7uBIuE&usg=AFQjCNGd5-mWM-mKXPQ_dRYnYPq5oqBTEA) is a great resource to learn about ConvNets!

<div class="divider"></div>

I trained a Convolutional Neural Net using keras on my local machine to classify handwritten digits.Side by Side I trained a multi-layered perceptron on the image datasets! I had lesser patience in training my convnet so I restriced the training to 1000/60000 samples on 100 epochs.Surprisingly, the network gave an accuracy of 95% on the test datasets of 10000 samples and was trained in under five minutes! 

The model summary looked something like:

Layer (type)     |            Output Shape   |           Param #   
=================================================================
conv2d_1 (Conv2D)           | (None, 28, 28, 20) |       200       
_________________________________________________________________
max_pooling2d_1 (MaxPooling2 |(None, 14, 14, 20)  |      0         
_________________________________________________________________
conv2d_2 (Conv2D)            |(None, 14, 14, 32)   |     5792      
_________________________________________________________________
max_pooling2d_2 (MaxPooling2 |(None, 7, 7, 32)      |    0         
_________________________________________________________________
dropout_1 (Dropout)         | (None, 7, 7, 32)      |    0         
_________________________________________________________________
flatten_1 (Flatten)         | (None, 1568)         |     0         
_________________________________________________________________
dense_1 (Dense)             | (None, 80)           |     125520    
_________________________________________________________________
dropout_2 (Dropout)        |  (None, 80)           |     0         
_________________________________________________________________
dense_2 (Dense)           |   (None, 10)           |     810       
=================================================================
Total params: 132,322
Trainable params: 132,322
Non-trainable params: 0

Details of Multi-layered perceptron:

Hidden layers=2
Hidden layer size=900 units
Input size=784 units
Dropout rate=0.5
Optimizer='adam'
Loss function='categorical_crossentropy'



The multi-layered perceptron after training for two hours on 2 hours on the datasets could only go upto 94%. Behold the power of deep learning!

Check out the source code [here]()!