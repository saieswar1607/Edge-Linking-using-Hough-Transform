# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:


Import the required modules.
<br>

### Step2:

Import the image to operate on.
<br>

### Step3:

Convert the imported image from BGR to GRAYSCALE.
<br>

### Step4:

Find the edges using canny edge detector and display the image.
<br>

### Step5:

Detect the points that form a line using hough transform.
<br>

### Step6:

Draw the lines on the image
<br>

### Step7:

Display the output
<br>

### Step8:

End the program.
<br>


## Program:
```Python
# Devleoped by:- Sai Eswar Kandukuri
# Registration number:- 212221240020
# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)

# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(smoothImage,(x1, y1),(x2, y2),(255, 0, 0),3)

# Display the result

plt.title("Hough Transform")
plt.imshow(cannyEdges)
plt.show()

```
## Output

### Input image and grayscale image

![1](output1.jpeg)
![2](output2.jpeg)


### Canny Edge detector output
![3](output3.jpeg)

### Display the result of Hough transform
![4](output4.jpeg)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
