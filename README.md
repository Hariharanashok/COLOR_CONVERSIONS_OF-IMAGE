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

##### Program:
### Developed By: J.NETHRAA
### Register Number: 212222100031

## Program:
### i) Read and display the image

```python
 import cv2
 image=cv2.imread('loke.jpg',1)
 cv2.imshow('Image Window', image)
 cv2.waitKey(0)
 cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/user-attachments/assets/ce6a177b-7387-48c5-a5e3-d0379a944435)

<br>
<br>

### ii)Write the image
```python
import cv2
image=cv2.imread('loke.jpg',0)
cv2.imwrite('loke.jpg',image)
```
## Output:
![image](https://github.com/user-attachments/assets/20c7ee10-1b73-4fe8-9128-abe3e78f5877)


<br>
<br>

## Program:
### iii)Shape of the Image
```python
   import cv2
    image=cv2.imread('passportsizeog.jpg',1)
    print(image.shape)
```
![3p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/f5b7a6aa-7cf6-4e1f-adcb-91e9ee591288)

<br>
<br>

### iv)Access rows and columns
```python
    import random
    import cv2
    image=cv2.imread('passportsizeog.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```

![4p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/307847bf-8fa4-4a61-bde0-253e0c835982)


![4](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/ff1c04dc-01a8-4d9d-9f61-74c13f44df18)


<br>
<br>

### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('passportsizeog.jpg',1)
image=cv2.resize(image,(300,300))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![5p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/8140bf83-acbf-4c6f-96ea-eb1f2721e9d1)

![5](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/dfa1bc81-99e3-46d0-8463-b8af9aa2ada3)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('passportsizeog.jpg',1)
img = cv2.resize(img,(200,200))
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

![6p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/954d9481-6780-4baf-8beb-0f42220cbe35)

![6](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/f57a06b5-2f8a-4c61-ab10-f15ce46343ce)
<br>
<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('passportsizeog.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![7p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/57e0dec4-fbf7-48a4-aca3-be7cc1834284)

![7](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/b80362bf-e3d8-42c1-80ef-76a5859fb100)
<br>
<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('passportsizeog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![8p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/85b704f3-9989-4b7f-8f6a-ed92f92cecee)

![8](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/82b082a4-f8a2-40cf-933e-d15dc4df737d)

<br>
<br>

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('passportsizeog.jpg',1)
img = cv2.resize(img,(200,200))

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
![9p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/5b6a792c-bc8a-43e3-9e63-8973cc35bacb)

![9](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/616c5bdd-561d-4357-a834-c3b400323311)
<br>
<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("passportsizeog.jpg",1)
img = cv2.resize(img,(200,200))
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
![10p](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/af52ebf6-bfcd-48b1-98ad-2c5519337ab5)

![10](https://github.com/Nethraa24/COLOR_CONVERSIONS_OF-IMAGE/assets/121215786/cb1d6613-665b-4b1b-92ab-824b41e52d74)
<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
