# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### Step6:
Display the image and end the program.


## Program:
```
Developed by : Adhithya.S
Register no : 212222240003
# Read image and convert it to grayscale image
import numpy as np
import matplotlib.pyplot as plt
import cv2



# Find the edges in the image using canny detector and display
image = cv2.imread("lion.jpeg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()


# Detect points that form a line using HoughLinesP
image = cv2.imread("lion.jpeg",0)
edge = cv2.Canny(image,100,200)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Draw lines on the image
edge = cv2.Canny(image,100,200)
lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)

# Display the result
plt.imshow(edge)
plt.title('Hough transform')
plt.axis('off')
plt.show()



```
## Output

### Input image and grayscale image
![Screenshot 2023-10-18 113521](https://github.com/s-adhithya/EDGE--LINKING-HOUGH-TRANSFORM/assets/113497423/4b251852-4fc3-4113-9fb5-8da2dcd24013)


### Canny Edge detector output
![Screenshot 2023-10-18 113542](https://github.com/s-adhithya/EDGE--LINKING-HOUGH-TRANSFORM/assets/113497423/a491eaa1-c0e6-443c-8a7b-398b091887dd)



### Display the result of Hough transform
![Screenshot 2023-10-18 113557](https://github.com/s-adhithya/EDGE--LINKING-HOUGH-TRANSFORM/assets/113497423/0526cd1b-c7f5-45ee-9c37-bdd4a7c58d02)




## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
