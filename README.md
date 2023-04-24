# Multiple-checkerboards-calibration
Repository for obtaining the lens distortion parameters of a camera by using an image with several checkerboards.\n
It is used by calling the function obtain_calib_parameters(img_path,calib_path,cb_matrix,margin=0).
  img_pad: path of the folder containing the image(s).
  calib_pad: path of the folder containing the calibration parameters.
  cb_matrix: array containing the the different sizes of the checkerboards f.e [(10,8),(7,5),(6,5)]
    It is generaly recommended to input the sizes from bigger to smaller so that the algorith doesent 
