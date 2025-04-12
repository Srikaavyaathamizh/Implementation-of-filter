# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>
Import the required libraries.


</br> 

### Step2
</br>
Convert the image from BGR to RGB.


</br> 

### Step3
</br>
Apply the required filters for the image separately.


</br> 

### Step4
</br>
Plot the original and filtered image by using matplotlib.pyplot.


</br> 

### Step5
</br>
End the program.


</br> 

### Developed By   : SRIKAAVYAA T
### Register Number: 212223230214
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

plt.imshow(image, cmap='gray')

plt.imshow(image, cmap='gray')
plt.title("Original Image")
plt.axis('off')
```
# Output
![image](https://github.com/user-attachments/assets/48f5c401-edb4-4722-8e4f-564434daadbb)

ii) Using Weighted Averaging Filter
```
weighted_kernel = np.array([[1, 2, 1], 
                            [2, 4, 2], 
                            [1, 2, 1]], np.float32)

weighted_kernel = weighted_kernel / weighted_kernel.sum()
weighted_image = cv2.filter2D(image, -1, weighted_kernel)

plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')



```
# Output
![image](https://github.com/user-attachments/assets/769738c0-3829-4bde-bc64-51abdbeda19f)

iii) Using Gaussian Filter
```
gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)

plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')

```

# Output
![image](https://github.com/user-attachments/assets/b3d7264b-6da2-400b-bbcc-f584e926e8cb)

iv)Using Median Filter
```
median_image = cv2.medianBlur(image, 3)

plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')

```
# Output
![image](https://github.com/user-attachments/assets/8bf863be-73ec-443b-a836-4e7bcf3074a1)


### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)
sharpened_laplacian_image = cv2.add(image, laplacian_image) 


plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')


```
# Output
![image](https://github.com/user-attachments/assets/388824e0-f8dd-43f7-b155-efed6ed2fa7e)

ii) Using Laplacian Operator
```
# ii) Laplacian Operator (Using OpenCV)
laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F)  # Laplacian operator
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image)  # Convert to absolute values
sharpened_operator_image = cv2.add(image, laplacian_operator_image)  # Sharpen the image

plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')

```
# Output
![image](https://github.com/user-attachments/assets/a7c79be1-d5ca-48e8-ac8e-4cf0d701dd8b)




## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
