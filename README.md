# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step1:
Load the necessary packages.

Step2:
Read the Image and convert to grayscale.

Step3:
Use Global thresholding to segment the image.

Step4:
Use Adaptive thresholding to segment the image.

Step5:
Use Otsu's method to segment the image and display the results

## Program

# Load the necessary packages

```
import cv2
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale

```
image=cv2.imread("c1.jpg")
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```

```
plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

```
_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

```


# Use Global thresholding to segment the image

```
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

```


# Use Adaptive thresholding to segment the image

```
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

```

# Use Otsu's method to segment the image 

```
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

```

# Display the results


## Output

### Original Image

<img width="152" height="225" alt="Screenshot 2025-11-12 103602" src="https://github.com/user-attachments/assets/4a913be6-e6a9-4338-b6cf-44872d9d5ab1" />



### Global Thresholding

<img width="198" height="234" alt="Screenshot 2025-11-12 103650" src="https://github.com/user-attachments/assets/5bf12794-1b73-47bb-9012-c0d7f5c4261d" />



### Adaptive Thresholding

<img width="230" height="240" alt="image" src="https://github.com/user-attachments/assets/6fe58d83-5e55-4054-b9e5-876c75047900" />



### Optimum Global Thesholding using Otsu's Method

<img width="152" height="226" alt="image" src="https://github.com/user-attachments/assets/771c9007-50ac-4af9-906d-534245514a3a" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
