
## Overview

In this project, I have implemented a classifier using deep neural networks, convolutional neural networks  and transfer learning to classify traffic signs. I have trained a model so that it can decode traffic signs from natural images by using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). After the model is trained, I have tested my model program on new images of traffic signs collected from the web and captured images of traffic sign locally collected from a friend.

## Dataset

1. [Download the dataset](https://d17h27t6h515a5.cloudfront.net/topher/2016/November/581faac4_traffic-signs-data/traffic-signs-data.zip). This is a pickled dataset in which we've already resized the images to 32x32.

#**Test Results**
Follow the keras version `traffic-sign-classification-with-keras.ipynb` for updated results
###Validation accuracy 99.31 %
###Test accuracy 95.44 %


#Model architecture

| Layer (type)                    |  Output Shape       | Param #    | Connected to                 |
| ------------------------------- |:-------------------:| ----------:| ----------------------------:|
| convolution2d_11 (Convolution2D)| (None, 28, 28, 6)   | 456        | convolution2d_input_9[0][0]  |
| maxpooling2d_10 (MaxPooling2D)  | (None, 14, 14, 6)   | 0          | convolution2d_11[0][0]       |
| activation_10 (Activation)      | (None, 14, 14, 6)   | 0          | maxpooling2d_10[0][0]        |
| convolution2d_12 (Convolution2D)| (None, 10, 10, 16)  | 2416       | activation_10[0][0]          |
| maxpooling2d_11 (MaxPooling2D)  | (None, 5, 5, 16)    | 0          | convolution2d_12[0][0]       |
| activation_11 (Activation)      | (None, 5, 5, 16)    | 0          | maxpooling2d_11[0][0]        |
| flatten_7 (Flatten)             | (None, 400)         | 0          | activation_11[0][0]          |
| dense_15 (Dense)                | (None, 128)         | 51328      | flatten_7[0][0]              |
| dropout_11 (Dropout)            | (None, 128)         | 0          | dense_15[0][0]               |
| activation_12 (Activation)      | (None, 128)         | 0          | dropout_11[0][0]             |
| dense_16 (Dense)                | (None, 43)          | 5547       | activation_12[0][0]          |
**Total params: 59747**

**Trained on 26270 samples, validated on 12939 samples**
                                                                                    
