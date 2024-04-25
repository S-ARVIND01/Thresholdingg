## THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm

#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.

### Program
```python
DEVELOPED BY: ARVIND S
REGISTER NO: 212222240012
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("dogncat.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dogncat.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```
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
#### Original Image
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/48fa713e-d843-4101-a1de-c519d616cfa2)

#### Global Thresholding
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/e18a29f5-3108-4623-8356-f1eb14510f15)
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/9900b20f-99e6-4c69-b130-10dc30ddd032)
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/6152eac4-7fff-4fb0-b621-74964e7068e0)
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/41bc52e6-12d9-4319-8b0c-fe3e5e6b5b0f)
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/e6382428-f0ca-42b1-a75a-587080a681b5)

#### Adaptive Thresholding
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/735e0a82-d35e-406e-86ff-63182df61e6c)
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/5adf0f1f-2830-4e0f-8b1b-4bc176759808)

#### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/S-ARVIND01/Thresholdingg/assets/118707337/f7a9bc6f-6551-4fb8-b465-9f6bb7edd50e)

### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
