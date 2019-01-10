# Computer Vision Engineer Test (C++/OpenCV)

## Task
Build an application in C++ with OpenCV which aims to, given a soccer video, find the players in it and extract their position in meters with reference to the center of the field as an output CSV file.

Specifically, the application should:
 * Read the given video file sequentially frame-by-frame.
 * For each frame:
   * Run a Background substraction algorithm in it.
   * Denoise the mask.
   * Identify players in the mask.
   * Given the projection matrix, extract the position of the identified players in 3D wrt the center of the field instead of pixels.
 * Generate a CSV file with a line per frame with the position in 3D of the players with the structure:
 ``` csv
 Frame#100 (x1, y1) (x2, y2) (x3, y3) // add as many as identified players in frame 100
 Frame#101 (x1, y1) (x2, y2) (x3, y3) // add as many as identified players in frame 101
 ```

## Given data
* **Video file** videos/sample1.mp4
* **Projection matrix** translates points from field (in meters) to pixels in a fullHD image like the input video file.
``` 
[2407.94, 890.965, -101.618, 74068.1]
[25.132, -335.994, -2359.5, 35865.7]
[0.0265481, 0.989646, -0.141051, 80.7746]
```

## Examples
![alt text](https://github.com/AutomaticTV/test-cv-developer/blob/master/images/exampleFrame234.PNG "Frame 234")
 ``` csv
Frame#234 (5.026569, -28.868330) (-7.621775, -28.008006) (0.192799, -15.723140) (7.352249, -15.524058) (-20.815596, -14.535495) (-4.103672, -9.449386) (-6.760802, -10.125898) (-26.455059, -3.987375) (7.647601, -1.304849) (-10.148156, -0.992817) (33.658962, 1.330726) (1.353115, 1.296049) (-26.451813, 1.654616) (-3.691337, 3.294527) (-15.410912, 7.802898) (7.396994, 4.306624) (-2.419737, 10.011163) (-10.288056, 18.414242) (-9.780995, 27.849729) (-25.415960, 21.871750) (-1.606033, 26.081640) (-5.602272, 28.551764) 
```
![alt text](https://github.com/AutomaticTV/test-cv-developer/blob/master/images/exampleFrame524.PNG "Frame 524")
``` csv
Frame#524 (1.242287, -28.034293) (-11.898251, -20.872074) (-2.800320, -18.416169) (2.510203, -17.100453) (-9.081305, -13.058719) (-23.740287, -9.526338) (-22.707648, -7.517313) (-10.247547, -6.656217) (-6.774091, -7.132234) (-8.271173, 5.636226) (-26.540825, 7.438519) (2.303503, -0.579134) (-6.817145, 9.132527) (-32.162833, 9.080199) (-11.222285, 10.602587) (-15.764693, 17.953701) (2.086494, 21.006964) (-0.992776, 23.619043) (-19.734702, 24.271418) 
```


