# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : DEVADARSHAN A S
Register Number : 212222110007
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('SF23.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('SF23.jpg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
### Output

### Original Image

![Screenshot 2024-04-23 105312](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/ae1995f9-b63c-4df5-8113-d88d45b96125)

### Global Thresholding
![Screenshot 2024-04-23 105319](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/db3a5816-a297-437d-ab89-9972c3d9e4e3)
![Screenshot 2024-04-23 105327](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/b447bbd4-de73-4235-87b2-7317e10f55e6)
![Screenshot 2024-04-23 105333](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/7f57e2f2-9465-490c-8815-62454363d545)
![Screenshot 2024-04-23 105344](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/ca913d16-b39d-47cb-83ba-c5491e24398f)
![Screenshot 2024-04-23 105349](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/8d93209b-ae35-4701-8e40-b4c9749e6af2)






### Adaptive Thresholding
![Screenshot 2024-04-23 105400](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/37f586e2-5eb1-42f7-b561-c9a0d355ab87)
![Screenshot 2024-04-23 105407](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/d1d53e11-3a43-49c5-8ee5-71c257989fe3)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-23 105413](https://github.com/DEVADARSHAN2/Thresholdingg/assets/119432150/5db89216-960d-45c5-b832-f968e47670c3)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
