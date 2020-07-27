# CarND-Finding-LaneLines-P1

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  
Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful 
tools for analyzing images.  

In below technical steps - First step takes raw image as input from then each step takes input from output of previous step.

Technical steps
---
1. Convert color image to gray scale image -- CV2.cvtColor
  - This step reduces number of pixels to process from 3*(256) to 1*(256)
  
  
2. Blur the image using Gaussian blur method -- CV2.GaussianBlur
  - Blur method is used to reduce the noise here
  
3. Selecting only Regions of interest on image -- CV2.fillPoly
  - While driving there are many distractions but one needs to concentrate on driving path.
  - Same is used here by selecting region of interest to find lane lines

4. Blur the image again using Gaussian blur methond -- CV2.GaussianBlur
  - Blur method is used to sharpen the edges here
 
5. Identify lines using Hough Lines -- CV2.HoughLinesP
  - Hough Lines identify lines in Canny image
 
6. Final Image using Weighted Image -- CV2.addWeighted
  - This step used to display both Hough Lines and Image combined.
