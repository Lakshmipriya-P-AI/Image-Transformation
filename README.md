# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step 2:
Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step 3:
Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step 4:
Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

### Step 5:
Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

### Step 6:
Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step 7:
Crop the image using cropped_img=input_img[20:150,60:230]

### Step 8:
Display all the Transformed images and end the program.

## Program:
```
Developed By: Lakshmi priya
Register Number: 212221230053

import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("cat.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim = input_image.shape

### i)Image Translation

M = np.float32([[1,0,100],
               [0,1,200],
               [0,0,1]])
translated_image = cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()

### ii) Image Scaling

M = np.float32([[1.5,0,0],
               [0,1.8,0],
               [0,0,1]])
scaled_image = cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_image)
plt.show()

### iii)Image shearing

M_x = np.float32([[1,0.5,0],
                 [0,1,0],
                 [0,0,1]])
M_y = np.float32([[1,0,0],
                 [0.5,1,0],
                 [0,0,1]])
sheared_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_xaxis)
plt.show()
plt.axis('off')
plt.imshow(sheared_yaxis)
plt.show()

### iv)Image Reflection

M_x = np.float32([[1,0,0],
                 [0,-1,rows],
                 [0,0,1]])
M_y = np.float32([[-1,0,cols],
                 [0,1,0],
                 [0,0,1]])
reflected_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols),int(rows)))
reflected_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(reflected_xaxis)
plt.show()
plt.axis('off')
plt.imshow(reflected_yaxis)
plt.show()

### v)Image Rotation

angle = np.radians(30)
M = np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotated_image = cv2.warpPerspective(input_image,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_image)
plt.show()

### vi)Image Cropping

cropped_image = input_image[100:300,100:300]
plt.axis('off')
plt.imshow(cropped_image)
plt.show()
```
## Output:

![op](https://user-images.githubusercontent.com/93427923/166110045-12ff7315-b0e9-4a69-8507-3192ddb5a4ac.png)

### i)Image Translation

![op1](https://user-images.githubusercontent.com/93427923/166110052-1accb5b7-faf1-41f1-b472-1b3c6f85000d.png)

### ii) Image Scaling

![op2](https://user-images.githubusercontent.com/93427923/166110225-81af6520-9d65-45dd-9a13-cc713be121bc.png)

### iii)Image shearing

![op3 1](https://user-images.githubusercontent.com/93427923/166110850-e6befb94-b40e-4906-a851-5745cac555ce.png)
![op3 2](https://user-images.githubusercontent.com/93427923/166110861-b83ea066-1a1a-4a07-a5a1-5a11fa23cf7e.png)

### iv)Image Reflection

![op4 1](https://user-images.githubusercontent.com/93427923/166110874-09f5c1cb-67ee-4183-ac3f-ae58b2cd0dac.png)
![op4 2](https://user-images.githubusercontent.com/93427923/166110881-980b02fa-43d4-4ea2-b1cb-8db7347575ef.png)

### v)Image Rotation

![op5](https://user-images.githubusercontent.com/93427923/166110320-e0208d30-328b-46ba-8018-c08d37a445f3.png)

### vi)Image Cropping

![op6](https://user-images.githubusercontent.com/93427923/166110349-5f00bc2f-740b-4bbc-839b-169671283560.png)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
