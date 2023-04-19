# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary Packages

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.
Display the image.


## Program:
```

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("img3.jpeg",0)
Gimg = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(Gimg)
plt.show()


# Find the edges in the image using canny detector and display
edge = cv2.Canny(Gimg,40,40)
plt.imshow(edge,cmap='gray')
plt.title('Edge image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines = cv2.HoughLinesP(edge,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)

# Display the result
plt.imshow(edge)
plt.axis('off')
plt.show()

```
## Output

### Input image and grayscale image
<img width="392" alt="image" src="https://user-images.githubusercontent.com/93427376/232981986-6c443a1f-ef0a-423a-91e6-0506325887db.png">


### Canny Edge detector output
<img width="396" alt="image" src="https://user-images.githubusercontent.com/93427376/232982062-f5d2ac20-b74d-403a-b7a5-89c494df9eae.png">



### Display the result of Hough transform
<img width="382" alt="image" src="https://user-images.githubusercontent.com/93427376/232982602-f0448981-c1aa-4521-a5ac-532696ee5080.png">





## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
