## Project: Build a Traffic Sign Recognition Classifier for German Traffic Signs

Overview
-----

The project uses deep nueral network to classify traffic signs. [German traffic sign dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset) was used for training the nueral network. 

[Lenet-5](http://yann.lecun.com/exdb/lenet/) CNN model architecture was used for training the network. 

Dependencies
---
This lab requires:

* [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit)

Getting Started
---

You can set up the required python library as follows:
```
conda env create -f environments-gpu.yml  # with GPU
```
If you have no CUDA-enabled GPU, you can use the following:
```
conda env create -f environments.yml  # with CPU
```
You can start the notebook as follows:
```
jupyter notebook Traffic_Sign_Classifier.ipynb
```

Model Architecture
---

| Layer         		|     Description	        					| Input |Output| 
|:---------------------:|:---------------------------------------------:| :----:|:-----:|
| Convolution 5x5     	| 1x1 stride, valid padding, RELU activation 	|32x32x1|28x28x48|
| Max pooling			| 2x2 stride, 2x2 window						|28x28x48|14x14x48|
| Convolution 5x5 	    | 1x1 stride, valid padding, RELU activation 	|14x14x48|10x10x96|
| Max pooling			| 2x2 stride, 2x2 window	   					|10x10x96|5x5x96|
| Convolution 3x3 		| 1x1 stride, valid padding, RELU activation    |5x5x96|3x3x172|
| Max pooling			| 1x1 stride, 2x2 window        				|3x3x172|2x2x172|
| Flatten				| 3 dimensions -> 1 dimension					|2x2x172| 688|
| Fully Connected | connect every neuron from layer above			|688|84|
| Fully Connected | output = number of traffic signs in data set	|84|**43**|

