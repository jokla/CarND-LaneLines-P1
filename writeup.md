#**Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---
## Overview:

The goal of this project is to make a pipeline that finds lane lines on the road using Python and OpenCV. See an example:

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />    <img src="laneLines_thirdPass.jpg" width="360" alt="Combined Image" />


---

## Reflection

###1. Describe your pipeline.

I will use the following pictures to show you all the steps:  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Extract pixel with bright component using a filter  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />

* Convert the color image in grayscale  

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" /> 

* Apply Gaussian smoothing   

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
