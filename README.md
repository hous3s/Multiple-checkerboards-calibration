# Multiple-checkerboards-calibration
Repository for obtaining the lens distortion parameters of a camera by using an image with several checkerboards.<br>
It first generates an objectpoint matrix for the 3d points in the world space for the different checkerboards. For each of the different checkerboard sizes it starts detecting them, saves the corners into an array and then draws a rectangle between the the upper-left corner and the lower-right corner in order to hide the checkerboard and detect another one. Once it is unable to find more checkerboards it moves on to the next image. Once it finishes going trough all of the images it calculates the lens distortion vector, the camera matrix, the new camera matrix and the roi, this parameters are saved for later use by using the cv2.undistort function.

It is used by calling the function __obtain_calib_parameters(img_path, calib_path, cb_matrix, margin=0)__ .<br>
  - img_pad: path of the folder containing the image(s).<br>
  - calib_pad: path of the folder containing the calibration parameters.<br>
  - cb_matrix: array containing the the different sizes of the checkerboards f.e [(10,8),(7,5),(6,5)]*<br>
  - margin: int containing the external margin for the rectangles drawn to hide the checkerboards.
  
*It is generaly recommended to input the sizes from bigger to smaller so that the algorith doesn't obstrude bigger checkerboards with rectangles
