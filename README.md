# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read two images, Color image and Gray Scale image.

### Step2:
Calculate the Histogram of Gray scale image and any one channel of the color image.

### Step3:
Display the histograms of gray and colour image.

### Step4:
Equalize the gray scale image.

### Step5:
Finally display the equalized image.

## Program:
```python
# Developed By: Shakthi kumar S
# Register Number:212222110043
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
import cv2
import matplotlib.pyplot as plt
gray_img=cv2.imread("DIP04-2.jpg",0)
color_img=cv2.imread("DIP04.jpg",-1)
gray_img=cv2.cvtColor(gray_img,cv2.COLOR_BGR2RGB)
color_img=cv2.cvtColor(color_img,cv2.COLOR_BGR2RGB)
plt.title("Color Image")
plt.axis("off")
plt.imshow(color_img)
plt.show()
plt.title("Gray Scale Image")
plt.axis("off")
plt.imshow(gray_img)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image
#Histogram of gray scale image
import cv2
hist=cv2.calcHist([gray_img],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("grayscale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

#Histogram of colour image
import cv2
hist=cv2.calcHist([color_img],[0],None,[256],[0,256])
plt.title("Histogram of Color Image:Red Channel")
plt.xlabel("Intensity value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Write the code to perform histogram equalization of the image. 
import cv2
Gray_image=cv2.imread('DIP04-2.jpg',0)
equalize=cv2.equalizeHist(Gray_image)
#resizing image 
Gray_image= cv2.resize(Gray_image, (150,120))
equalize= cv2.resize(equalize, (150,120))
#output
cv2.imshow('GRAY IMAGE',Gray_image)
cv2.imshow('EQUALIZED IMAGE',equalize)
cv2.waitKey(0)![DIP04-1](https://user-images.githubusercontent.com/121041644/229365106-a8d31c03-1ed2-4e86-a8b9-0a04db94c7fe.png)

cv2.destroyAllWindows()
```

## Output:
### Input Grayscale Image and Color Image
![DIP04-1](https://user-images.githubusercontent.com/121041644/229365151-4bf1a993-68fd-4715-b024-1fc29d5d52bd.png)

### Histogram of Grayscale Image and any channel of Color Image
![DIP04-2](https://user-images.githubusercontent.com/121041644/229365162-27a44878-2c7f-484c-9b6a-cf0354deb819.png)
![DIP04-3](https://user-images.githubusercontent.com/121041644/229365183-333ecb35-b105-4a5a-85e3-2d37347c580e.png)


### Histogram Equalization of Grayscale Image
![DIP04-4](https://user-images.githubusercontent.com/121041644/229365195-fe7ce7e1-f1d3-447e-bd88-07307dc1cfd7.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
