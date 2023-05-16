# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Improt the packages.



### Step2:
convert to grayscale.

### Step3:
Use global thresholding techniques.

### Step4:
Use adaptive thresholding and otsu's method.



### Step5:
Display the results using loop.

## Program

```

# Load the necessary packages
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the Image and convert to grayscale
img=cv2.imread("water-lilly")
img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
plt.imshow(img1)
plt.title("Original Image")
plt.show()
gray1=cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
plt.imshow(gray1)
plt.imshow(gray1,cmap="gray")
plt.title("Gray image")
plt.show()




# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(gray1,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray1,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray1,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray1,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray1,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(gray1,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray1,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)



# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(gray1,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[gray1,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(img1)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image
![output](https://github.com/jhansi21005096/Thresholding/blob/main/out1.png)
### Global Thresholding
![output](https://github.com/jhansi21005096/Thresholding/blob/main/out2.png)
### Adaptive Thresholding
![output](https://github.com/jhansi21005096/Thresholding/blob/main/out3.png)
### Optimum Global Thesholding using Otsu's Method
![output](https://github.com/jhansi21005096/Thresholding/blob/main/out4.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

