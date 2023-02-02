# AutoLaneDetection
Personal Project on Lane Autodetection:
Using OpenCV in Python for lane detection, computer vision can help us automate many things and the biggest examples are Auto driving cars, face recognition, Object detection and recognition.

By getting inspired from all these Projects I did this project of auto lane detection, for detecting lanes we generally use edge detection technique, which means whenever there is a sharp change in intensity and sharp change in colour for which we will first have to read the image as a matrix of pixels, so in pixels, the intensity of images vary from 0 to 255, 0 being lowest intensity, 255 means the highest intensity.

Gradient: Measure the change in brightness over adjacent pixels.

Step 1: Changing to grayscale :
Calculating gradient helps us in detecting edges using intensity change in pixels. we will be converting the normal image or video to the gradient image, which means we will be only seeing the edges where there is a change in intensity.

For this project I'm using a road video, this video is in RGB (3 Channel) format that is coloured and I first converted this into a grayscale video (1 channel) for applying gradient edge detection technique.

Step 2: Gaussian Blur (Reducing noise):
By applying the Gaussian filter we can remove the noise from the image or video, example for removing the noise we can take the image as a matrix of pixels and apply averaging method, which means making all the values of all the pixels equal to the average value.

Step 3: Applying the canny method to identify edges:
Where there is a sharp change in intensity or shape of an image, as we know that an image is a matrix of pixels i.e. some values so it has x and y axis, so what canny method does is, it calculates the derivative for the function of x and y, which will calculate the change in intensity wrt to the adjacent pixel, the small derivative is a small change in intensity and big change is a big change. This helps us to isolate the edges with a sharp change in gradient. After applying this method we will get all the edges with the most rapid change in brightness.

Step 4: Finding the area of interest(lanes)
Now we will use matplotlib library to get our image in x-y axis. Using the image in axis we can tell the actual points to the compute that this is our area of interest. We will make a filter using matplotlib and impose this filter on our actual image using and operation which will give us the area of interest.

Step 5: Hough Transformation (for finding straight lines of lanes):
Using hough space we will drop many points in the space with the help of famous y = mx + c but for hough space i.e plotting points with the different value angular versions of m and c with the same line. We can define the threshold value for getting a perfect point.
After getting the lane lines we will blend the actual image and the lines created using hough transformation, doing this will highlight the lanes.
