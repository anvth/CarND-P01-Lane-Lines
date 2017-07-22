# **Finding Lane Lines on the Road** 

## By Anvith Shivakumara

### This is a brief write up on the first project I submitted as a part of the Udacity SDC Nano Degree Program. 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road in the provided images
* Extend the same pipeline so that it accepts video input and returns an annotated version of the input
* Both the left and right lane lines are accurately annotated by solid lines throughout most of the video


[//]: # (Image References)

[Result1]: ./test_images_output/solidWhiteCurve.jpg "Result1"

---

### Reflection

### 1. The pipeline

My pipeline consisted of 5 steps. 
* The first step is to convert the color image into a grayscale one. 
* The next step is to smooth out the edges by adding some gaussian noise. 
* The next step is to detect the edges by applying Canny Edge algorithm. However, this would return all the edges that were detected in the image, but the part of the image that interets me is very little. 
* So in the next step, I mark my region of interest and fill the rest of the image with black. 
* This resultant image consists of pixels that needs to be mapped onto Hough Space, where they would become lines. Now based on the kinda lanes that are present, the markings in the hough space may not consist of full length straight lines. This step consists of another sub-step that involves calculation of end-points for the lines to be drawn.
* The final step is to overlay the final image with the initial one. This would let us visually compare how well the pipeline works.
![alt text][Result1]


### 2. Identify potential shortcomings with your current pipeline

* The first assumption this Pipeline makes is, all images/videos supplied to it have fixed shape. We see that, this assumption leads to unexpected lane markings in the challenge video.

* The draw line function also needs some improvement

* There is a significant amount of jitter in videos


### 3. Suggest possible improvements to your pipeline

* Look for certain avalible libraries that would help draw_line() improve it's efficiency
* Apply temporal smoothing for reduce jitter
* Pre-process the image to standardise it's shape
* Improve code documentation


