# CameraResolutionTesting

### MTF is a measure of image sharpness and is commonly used in the field of image analysis and photography. The script is written in Python and uses the NumPy library for array operations. ###

The script begins by importing the necessary libraries and defining some helper functions. The first helper function, "deriv1," calculates the first derivative of an image by subtracting the value of each pixel from the value of the pixel to its right. The second helper function, "find_centroid," finds the centroid of the image by averaging the coordinates of all non-zero pixels.

The main function, srfmat3, takes an image as input and performs the following steps:

1.Line fitting: The image is first processed using the deriv1 function to get the first derivative of the image. The find_centroid function is then used to find the centroid of the image, and the fit_line function is used to fit a line to the centroid. The angle of the line is then computed using the compute_angle function.


2.Edge Spread Function (ESF) computation: The ESF is computed using the compute_esf function, which takes the image and the line obtained in the previous step as inputs.


3.Line Spread Function (LSF) computation: The LSF is computed using the get_lsf function, which takes the ESF as input.


4.MTF computation: The MTF is computed using the get_mtf function, which takes the recentered LSF and the line obtained in the first step as inputs.


5.Plotting: The MTF is plotted as a function of spatial frequency using matplotlib.

The script then defines a function called "fit_line," which fits a line to the image using the centroid and the first derivative. This line is used to compute the angle of the edge that is being analyzed.

The next function defined is "compute_esf," which computes the Edge Spread Function (ESF) of the image using the line fit and the angle computed earlier. The function "get_lsf" is used to compute the Line Spread Function (LSF) from the ESF.

The function "get_mtf" is used to compute the MTF from the LSF by taking the Fourier Transform of the LSF and normalizing it. The function "recenter" is used to recenter the LSF so that it is ready for the Fourier Transform.

The script then defines two more helper functions, "mtf50" and "mtf50p", which compute the MTF50 and MTF50P, respectively. MTF50 is the frequency where the MTF is 50% of its low frequency value, and MTF50P is the frequency where the MTF is 50% of its peak value. Both of these values are important in defining image sharpness.

The script then loads an image and splits it into its Red, Green, Blue, and Luminance channels. For each channel, the script applies the previously defined functions in sequence to compute the MTF, MTF50, and MTF50P. The MTF is then plotted for each channel, and the MTF50 and MTF50P for the Luminance channel are displayed on the plot.

In conclusion, the script provides a comprehensive way to analyze the sharpness of an image by computing the MTF, MTF50, and MTF50P for each channel of the image. It also provides a way to visualize the results of the analysis by plotting the MTF for each channel.
