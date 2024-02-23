# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image
```
### Developed By: Divakar R
### Register Number:212222240026
```
## Program:
### i) Read and display the image
```python
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(300,300))
cv2.imshow('DISPLAY',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
<br>![Screenshot 2024-02-15 223654](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/653c2908-00e7-462d-abcb-2fa9d0dae888)

<br>

### ii)Write the image
```python
image=cv2.imread('image.jpg',0)
cv2.imwrite('Photo.jpg',image)
```
<br>![Screenshot 2024-02-15 223748](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/c62d0d94-af4d-40c3-ac2c-364e50fe4485)

<br>

### iii)Shape of the Image
```python
import cv2
image=cv2.imread('image.jpg',1)
print(image.shape)
```
<br>![Screenshot 2024-02-15 223802](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/2e63b7e6-1f97-406b-8da9-502db7ff052d)

<br>

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)]
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

<br>![Screenshot 2024-02-15 223546](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/ddf9a031-d7a9-4530-8a89-2295b8a4ea40)

<br>

### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 223859](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/99b172c1-1811-438e-9a94-6b5fc2599603)

<br>

### vi) BGR and RGB to HSV and GRAY
```python
    import cv2
    img = cv2.imread('image.jpg',1)
    img = cv2.resize(img,(300,200))
    cv2.imshow('Original Image',img)

    hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
    cv2.imshow('BGR2HSV',hsv1)

    hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
    cv2.imshow('RGB2HSV',hsv2)

    gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    cv2.imshow('BGR2GRAY',gray1)

    gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
    cv2.imshow('RGB2GRAY',gray2)

    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 224114](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/38345644-f609-4703-9756-bc56b0517e3c)

<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 224451](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/7ddf1c9f-010f-4773-a6a6-f0e1ba69800e)

<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 224552](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/78284cd8-fc42-446b-b5ab-da3afa0c4a23)

<br>

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 224734](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/d8e470d4-29f9-4099-8e27-cf2300acb251)

<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("image.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>![Screenshot 2024-02-15 224840](https://github.com/Vasanthamukilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119559694/790e7686-c9af-488a-be6a-7fd3f72aae99)

<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
