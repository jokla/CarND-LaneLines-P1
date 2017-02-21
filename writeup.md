#**Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---
## Overview:

The goal of this project is to make a pipeline that finds lane lines on the road using Python and OpenCV. See an example:

<img src="./test_images/solidWhiteRight.jpg" width="360" alt="Combined Image" />    <img src="laneLines_thirdPass.jpg" width="360" alt="Combined Image" />

The pipeline will be tested on some images and videos provided by Udacity. The following assumptions are made:
* The camera always has the same position with respect to the road
* There is always a visible white or yellow line on the road
* We don't have any vehicle in front of us 
* We consider highway scenario with good weather conditions.

---

## Reflection

###1. Describe your pipeline.

I will use the following picture to show you all the steps:  

<img src="./img_doc/original.png" width="360" alt="Combined Image" />

#### Color selection   
At this step the pixels that were above the thresholds have been retained, and pixels below the threshold have been blacked out. This color filtering allows to suppress non-yellow and non-white colors. This is the result:

<img src="./img_doc/mask_color.png" width="360" alt="Combined Image" />

I will keep aside this mask and use it later.

#### Convert the color image in grayscale  
The original image is converted in grayscale. In this way we have only one channel:

<img src="./img_doc/gray.png" width="360" alt="Combined Image" />

#### Apply Gaussian smoothing:  
Before running Canny, I applyied a [Gaussian smoothing](http://docs.opencv.org/2.4/modules/imgproc/doc/filtering.html?highlight=gaussianblur#gaussianblur) which is essentially a way of suppressing noise and spurious gradients by averaging.   

<img src="./img_doc/gray.png" width="360" alt="Combined Image" />

#### Use Canny for edge detection   
The Canny allows to detect the edges in the images:

<img src="./img_doc/canny.png" width="360" alt="Combined Image" />

To improve the result, I also used the opencv function `dilate` and `erode`.

### Merge Canny and Color Selection
In some cases the Canny edge detector fails to find the lines. For example, when there is not enough constrast between the ashalt and the line, as in the challenge video. The color selection, on the other hand, doesn't have this problem. For this reason I decided to merge the result of Canny and color detector:   

<img src="./img_doc/merge.png" width="360" alt="Combined Image" />

#### Region of Interest Mask
I defined a left and right Region Of Interest (ROI) based on the image size. Since that the front facing camera is mounted in a fix position, we supposed here that the lane lines will always appear in the same general region of the image. 
 
<img src="./img_doc/roi.png" width="360" alt="Combined Image" />

#### Run Hough transform to detect lines  
Thanks to the Hough transform, it is possible to detect lines in the images. At this step, I only considered the line with a slope between 20 and 90 degrees. In this way I can get rid of horizontal lines. This is the result applyed to the original image:
<img src="./img_doc/hough.png" width="360" alt="Combined Image" />


#### Compute lines
Now I need to average/extrapolate the result of the hough transorm and draw the two lines onto the image. For this I used the function  `fitLine`, after having extrapolated the points  from the previuos result with the opencv function `findNonZero`. I did this two times, once for the right line and another time for the left line. As result I had the slope of the lines, and I could draw them onto the original picture:   

<img src="./img_doc/final.png" width="360" alt="Combined Image" />

## Results:

### Pictures
Here some results on test images provided by Udacity:   
<img src="./img_doc/final.png" width="360" alt="Combined Image" /> <img src="./img_doc/result1.png" width="340" alt="Combined Image" />    
<img src="./img_doc/result2.png" width="360" alt="Combined Image" /> <img src="./img_doc/result3.png" width="360" alt="Combined Image" />   
<img src="./img_doc/result4.png" width="360" alt="Combined Image" />     <img src="./img_doc/result5.png" width="360" alt="Combined Image" />        

### Videos
![](./img_doc/white.gif) 
![](./img_doc/yellow.gif)



###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
