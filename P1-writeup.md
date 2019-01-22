# **Finding Lane Lines on the Road**

### Reflection

### 1. Description of my pipeline

My pipeline consisted of the following 6 steps:
1. convert image to grayscale
2. apply gaussian blur with a kernel size of 3
3. run canny edge detection
4. mask image with a trapezoid
5. run hough transform to extract lines
6. overlay lines onto original image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first calculating all the slopes and midpoints of the lines. Then I split the slopes into 2 different lists depending on if it was positive or negative. Lastly, I averaged the midpoints and slopes extrapolated a single averaged line for both the positive and negative sloped lines.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the road is curved and does not have many straight lines that the hough transform can extract.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to do a quadratic/exponential fit instead of a linear one in order to account for the curves in the road.
