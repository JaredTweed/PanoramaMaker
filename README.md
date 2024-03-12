# Assignment Description

# Scroll to the bottom for output results.

## 1: Take 4 sets of 2 photographs to be stitched together to create a panorama
You need to take photograph pairs to be stitched together, similar to the pair we talked about in our transformations lecture. Take each pair of images from different scenes. I would recommend taking many pairs of images and determining which ones to use after some experimentation with your implementation and results. Make sure to resize your images to get the longer dimension of the image (height or width) to be 750.

If you’d like to implement Part 5 for bonus points, at least two of your 4 image sets should contain 4 images to be stitched together.

**Submit your image pairs named as S1-im1.png, S1-im2.png, and so on.**

## 2: FAST feature detector (3 pts.)
Features from accelerated segment test, or FAST, is an efficient interest point detection method proposed by Rosten and Drummond. It works by comparing the brightness of a pixel with a ring surrounding it. You can find more detailed description in the FAST Wikipedia page.

You need to implement FAST including the high-speed test as a function named my_fast_detector. It’s on you to learn about how to define functions in MATLAB.

Hint: In MATLAB, using for loops is quite inefficient but using matrix operations are very efficient. You can do the pixel-wise comparisons by shifting the image for every pixel at once. For example, for the check if a pixel is brighter than their neighbor 3 pixels to the left, shift the image to the right by 3 pixels and compare against the original image in a single line!

**Save the visualization of the detected points in the first images of your 2 image sets as S1-fast.png and S2-fast.png**

## 2: Robust FAST using Harris Cornerness metric (1 pts.)
Compute the Harris cornerness measure for each detected FAST feature. Eliminate weak FAST points by defining a threshold for the Harris metric. This threshold must be fixed for every image you use. We will call these points FASTR points.

**Comment on which points were discarded after this thresholded by comparing your FAST and FASTR visualizations. Save the visualization of the detected points in the first images of your 2 image sets as S1-fastR.png and S2-fastR.png** Note down the average computation time of FAST and FASTR features (average of all the images you have) and comment on the difference.

## 3: Point description and matching (2 pts.)
Use an existing implementation of one of ORB, SURF, or FREAK feature decription methods to generate descriptors for your FAST and FASTR points. Note which decriptor you use in your report. Depending on the function you are using, you might need to put your keypoints in appropriate containers. Don’t forget to use MATLAB Help to get such definitions.

Match the features between the first two images in each photo set. **Save the visualization of the matched points between the two images of your first 2 image sets, using FAST and FASTR points, as S1-fastMatch.png, S1-fastRMatch.png, S2-fastMatch.png, and S2-fastRMatch.png** Comment on the performance differences if any.

## 4: RANSAC and Panoramas (4 pts.)
To compute the homography between each pair, you will use RANSAC. You can use an existing implementation such as matchFeatures function in MATLAB, but you need to be able experiment with the RANSAC parameters for the optimum result.

Find the homography between two images in all your image sets and stitch them together.

Experiment with RANSAC parameters and find a setup where you use minimum number of trials while still getting a satisfactory result for all your image sets. You’ll find 2 different sets of RANSAC parameters, one for FAST and one for FASTR. The RANSAC parameters you decide should be the same for the 4 image sets.

**Save the stitched images for all your image sets only using FASTR points, as S1-panorama.png, S2-panorama.png, S3-panorama.png, and S4-panorama.png** Comment on the difference between optimal RANSAC parameters for FAST and FASTR.

## 5: Bonus: Stitch 4 images instead of 2. (2 pts.)
Have 4 images in at least two of your image sets and present panoramas that result in stitching all 4 images. These 4 image can be all horizontally placed (in the panorama it would be [im1 im2 im3 im4] side by side) or placed as a grid (like [im1 im2 ; im3 im4], the last two images being ‘downstairs neighbors’ of the first two).

## 6: Report
The report template is here: HTML template

All you need to do is to save the images in the current folder as your html file, and fill in the required information and comments in the html file. Don’t edit the template further than needed.

You’ll submit your report as an html file in a .zip container together with all the results you have saved. You need to add the necessary comments asked in the question definitions.

## Below are my example results from completing the assignment
![S1-panorama](https://github.com/JaredTweed/MATLAB/assets/59375645/a6bd34bd-293b-4f25-8612-b27600fea883)
![S2-panorama](https://github.com/JaredTweed/MATLAB/assets/59375645/c30fc7c0-7c0b-4849-a18c-12c4369d171b)
![S3-panorama](https://github.com/JaredTweed/MATLAB/assets/59375645/73fcbaf0-a2e2-4577-a6f1-519a4c749058)
![S4-panorama](https://github.com/JaredTweed/MATLAB/assets/59375645/61f2c461-0e17-4ee0-94ed-c5a7d49a69d7)
![S4-panorama_2](https://github.com/JaredTweed/MATLAB/assets/59375645/5342ebb5-87d8-478d-b7aa-071af7d6ff2a)
