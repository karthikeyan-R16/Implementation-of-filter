# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

1.Import the required libraries.

2.Convert the image from BGR to RGB.

3.Apply the required filters for the image separately.

4.Plot the original and filtered image by using matplotlib.pyplot.

5.End of Program

## Program:
### Developed By   : Karthikeyan R
### Register Number: 212222240045
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()



```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/52b632f1-0e0e-4b62-a367-1247cf422104)


ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()





```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/7603b83a-4bcf-4a6b-bc1b-3e596250500d)


iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()




```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/e1288e3a-0743-47a5-8ae5-e4bfb92e3b93)


iv)Using Median Filter
```Python
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()





```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/607bdfb1-4beb-479f-9816-2f23ca52d468)


### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()


```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/228b5532-7661-40f3-ae5f-cc264abd1a4f)


ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()




```
<h2>OUTPUT</h2>

![image](https://github.com/user-attachments/assets/ab706b33-251e-4466-b954-23bf5610c257)

</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
