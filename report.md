**Finding Lane Lines on the Road** 

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

** Reflection

The pipeline consisted of 5 steps. 

1. Read the images and convert them into grayscale images. 
2. Apply Gaussian smoothing (the kernel size is found experimentally)
3. Canny edge detector is applied to the images (again the parameters are found based on the edge detection quiz in the lecture.)
4. We assume that we are driving in the lane. By using this assumption, we define a trapezoid area and mask the rest of the edge image.
5. Hough transform are appled on masked edge-detected images.
6. Line segment are classified as left and right based on their slope by modifying the draw_line() function
7. Lines are extrapolated using the intersection point of right and left dominant line.
8. Finally, line image with original image are combined.

** Shortcomings

Our system is limited to the straight roads due to the line model and our manually defined mask area.
