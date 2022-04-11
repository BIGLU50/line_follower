# LINE FOLLOWER 

linefollow.py commands a robot to move itself towards the computed center of a detected range of colors. Using the provided linemission.launch file, the robot starts on a yellow line and follows it.

Notable lines of code that warrant explanation include:
Lines 22-26
- Line 22 converts the image generated from line 19 (which uses the data read from image_raw) from a BGR color standard to HSV.
- Lines 23-24 designate the color range that the robot will detect and NOT ignore in its mask
- Lines 25-26 create the mask by filtering out all other HSV colors except for ones within the specified range.

Lines 29-34
This section commands the robot to only track a splice of the mask (in this case, the bottom 20 pixels). This helps the robot to easily track the line below it, and helps it avoid noise.

Lines 37-44
Creates a centroid for the user to better understand the robot's perceived "center"

Lines 49-52
A PID controller. The error was adjusted based on the returned image size. 

