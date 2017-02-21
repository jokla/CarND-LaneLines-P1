#**Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---
## Overview:

The goal of this project is to make a pipeline that finds lane lines on the road using Python and OpenCV. See an example:

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />    <img src="laneLines_thirdPass.jpg" width="360" alt="Combined Image" />

The pipeline will be tested on some images and videos.
---

## Reflection

###1. Describe your pipeline.

I will use the following picture to show you all the steps:  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Color selection
 The pixels that were above the thresholds have been retained, and pixels below the threshold have been blacked out. This help to find the lines in the images, that usually have a brigter color than the road.

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Convert the color image in grayscale  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" /> 

* Apply Gaussian smoothing:
We'll also include Gaussian smoothing, before running Canny, which is essentially a way of suppressing noise and spurious gradients by averaging   

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Use Canny for edge detection   

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Define ROI to consider only the road   

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" /> 

* Run Hough transform to detect lines  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />




###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
