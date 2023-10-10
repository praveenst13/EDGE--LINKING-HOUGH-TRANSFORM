# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

# Algorithm:
### Step 1:
Import all the necessary modules for the program.
<br>

### Step 2:
Load a image using imread() from cv2 module.
<br>

### Step3:
Convert the image to grayscale.
<br>

### Step 4:
Using Canny operator from cv2,detect the edges of the image.
<br>

### Step 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
<br>


## Program:
name:praveen s
reg no : 212222240077
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('fade.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)

plt.imshow(image1,cmap='gray')
plt.title('Input Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)


# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)

# Display the result
plt.title('Hough Lines')
plt.imshow(edges1,'gray')

```
## Output

### Input image and grayscale image
<br>
<br>

![image](https://github.com/praveenst13/EDGE--LINKING-HOUGH-TRANSFORM/assets/118787793/b714cd26-4d30-40ac-9393-64608b74039f)

<br>
<br>

### Canny Edge detector output
<br>
<br>

![image](https://github.com/praveenst13/EDGE--LINKING-HOUGH-TRANSFORM/assets/118787793/753e258d-28be-4bf0-acc4-1571c770a12c)


<br>
<br>


### Display the result of Hough transform
<br>

![image](https://github.com/praveenst13/EDGE--LINKING-HOUGH-TRANSFORM/assets/118787793/ccb14793-93fc-4e00-8711-d27dea185815)

<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
