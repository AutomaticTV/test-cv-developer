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
