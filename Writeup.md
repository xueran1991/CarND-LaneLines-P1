# **Self-Driving Car Engineer** Nanodegree
## Project: Finding Lane Lines on the Road 
## Writeup

The goal of the project is to final lane line in road pictures and videos with basic computer vison.

## Reflection

1. #### Structure of my pipline.
There are 6 main steps in my pipline. First, I converted the input RGB image data into grayscale, then smoothed the grayscale image with Gaussian blur. After the smoothing I used the Canny edge detect algorithm to get edges in the image. With the edges and a Hough line algotithm, lines in the image were got. The lines are line segments. I merged and extended the line segments into a line in each side lane of the road. The final step was to combine the original image with the final lane lines.

The slope of left lane line is roughly betweent -0.8 to -0.5. The slope of right lanline is roughly between 0.5 to 0.8. So the line segments were seprated into left and right through slope. And also some line segments with much larger or samller slopes were abanded. Then I calculated the coordinate of middle point of the line segments respectively in each side. With the slope and a point and the boundary of the interset region, the end points of the final line were calculated.

I run the pipline with test images and videos. The are servel key parameters to tune in the pipline: the low and high threshold in Canny, the threshold and min_line_length and max_line_gap in Hough line algorithm.


2. #### Potential shortcomings with the current pipline
The interest region is based on the lane postion in the images and videos. And the region selecting was hard coded. With images or videos in different resolution, or the lane region changed, the pipline won't work well.

3. #### Possible importments
The interest region selecting could be self-adapted in images or videos with differnt resolution. 



