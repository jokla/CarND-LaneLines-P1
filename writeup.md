#**Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---
# Overview:

The goal of this project is to make a pipeline that finds lane lines on the road using Python and OpenCV.


![](./test_images/solidWhiteRight.jpg)

---

### Reflection

###1. Describe your pipeline.

![alt text][image1]

* Convert the color image in grayscale
* Apply Gaussian smoothing
* Use Canny for edge detection
* Define ROI to consider only the road
* Run Hough transform to detect lines




###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
