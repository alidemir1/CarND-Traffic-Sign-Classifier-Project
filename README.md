## Project: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

## Design and Test a Model Architecture

### Preprocessing
As preprocessing steps;
* Normalization is applied by (pixel_values - 127.0 / 128.0)

### Model Architecture
LeNet-V5 is used as the model architecture. It has been made some modifications on the network. Number of filters are increased from 6 to 12 and dropout layers are added after convolutional layers.

### Model Training and Solution Approach
In order to get >=0.93 accuracy on the validation set;
* Keep_probability for dropout layers is set to 0.4 to prevent overfitting on training data. Because it is observed in first few trials.
* Learning Rate is set to 0.003 initially.
* Learning rate is decreased in each epoch (after 5th Epoch) by factor of 1.04 in order to keep learning alive and not to stuck in some worse local minima in the parameter space.
* Training is stop once >0.930 accuracy is observed on validation set.
* After training is completed, evaluation on the test set is performed. Accuracy of the test set is reported as 0.918. 

### Test a Model on New Images

[image1]: ./german_signs/road_sign1.jpeg "1"
[image2]: ./german_signs/road_sign2.jpeg "2"
[image3]: ./german_signs/road_sign3.jpg "3"
[image4]: ./german_signs/road_sign4.jpeg "4"
[image5]: ./german_signs/road_sign5.jpg "5"

5 different images are gathered from web. Prediction is performed on these images, accuracy of prediction on these 5 images is 0.60.
Prediction for each image is illustrated below. Top - 5 prediction can be seen on [Traffic_Sign_Classifier.html](./Traffic_Sign_Classifier.html)

Priority Road     |Right-of-way at the next Intersection        |   Wild Animals Crossing            |  Speed Limit (50km/h)        |  Wild Animals Crossing 
:----------------:|:-------------------------:|:------------------------:|:-------------------------:|:-------------------------:
![1][image1]      |  ![2][image2]             |    ![3][image3]          |  ![4][image4]             |  ![5][image5]

### Discussion 
According top - 5 predictions on new images gathered from the web;
* According to top - 5 predictions accuracy of the network is 0.8
* Network seems to be confused on animal and human figures. More samples (data) might be helpful for network to better generalize.
* Predictions of speed limit 50 image, 4 predictions belong to the different speed limits and just one of the prediction says no vehicle. Network performed good results on this image and I think if I put it on different trials on the speed limits, it will generalize nicely.

### Dependencies
This lab requires:

* [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit)

The lab environment can be created with CarND Term1 Starter Kit. Click [here](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) for the details.


