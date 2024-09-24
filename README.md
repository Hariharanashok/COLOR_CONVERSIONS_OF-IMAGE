# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: Hariharan A
### Register Number: 212222100012


## Output:

### i)Read and Display an Image

```
import cv2
# Read the image
image = cv2.imread('Lokesh.JPG')
# Display the image in a window
cv2.imshow('Image Window', image)
# Wait indefinitely for a key press
cv2.waitKey(0)
# Destroy all windows created by OpenCV
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/60780b34-6a32-45f2-a036-4569da419421)

<br>
<br>

### ii)Draw Shapes and Add Text

```python
import cv2

# Load the image
img = cv2.imread("Lokesh.JPG")

# Define parameters for the drawings
start = (0, 0)
stop = (500, 329)
color = (100, 255, 100)
thickness = 10

# 1. Draw a circle
circle_img = img.copy()  # Create a copy of the original image
cv2.circle(circle_img, (330, 225), 150, (255, 0, 0), 10)
cv2.imshow('Circle', circle_img)
cv2.imwrite('Circle_Image.jpg', circle_img)  # Save the image
cv2.waitKey(0)

# 2. Draw a rectangle
rectangle_img = img.copy()  # Create a copy of the original image
cv2.rectangle(rectangle_img, start, stop, color, thickness)
cv2.imshow('Rectangle', rectangle_img)
cv2.imwrite('Rectangle_Image.jpg', rectangle_img)  # Save the image
cv2.waitKey(0)

# 3. Draw a line
line_img = img.copy()  # Create a copy of the original image
cv2.line(line_img, (100, 200), (900, 100), (200, 100, 205), 10)
cv2.imshow('Line', line_img)
cv2.imwrite('Line_Image.jpg', line_img)  # Save the image
cv2.waitKey(0)

# 4. Add text to the image
text_img = img.copy()  # Create a copy of the original image
text = "OpenCV Drawing"
org = (10, 30)  # top-left corner of the text string
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
text_color = (255, 255, 255)  # White color
thickness = 2
cv2.putText(text_img, text, org, font, font_scale, text_color, thickness, cv2.LINE_AA)
cv2.imshow('Text', text_img)
cv2.imwrite('Text_Image.jpg', text_img)  # Save the image
cv2.waitKey(0)

# Clean up windows
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/737204dd-70fc-4d81-b73c-4441b4d7fc3f)

![image](https://github.com/user-attachments/assets/451165da-7f1f-436b-b713-044f2388f072)

![image](https://github.com/user-attachments/assets/0efd2596-8f27-4f9a-a633-7216f0ec6e07)

![image](https://github.com/user-attachments/assets/3290cf47-a4cb-4976-999b-553d1174c7c6)



<br>
<br>

### iii)Image Color Conversion

```
# Read the image
image = cv2.imread("Lokesh.JPG")

# Convert to HSV color space
img_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
# Convert to grayscale
img = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Display the HSV image
cv2.imshow('Image Window (HSV)', img_hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.waitKey(0)
```
### Convert the image from RGB to HSV and display it:
![image](https://github.com/user-attachments/assets/14f94f43-5d4b-4d42-81fd-1d9ec2e00982)



### Convert the image from RGB to GRAY and display it:

### Convert the image from RGB to YCrCb and display it:


### Convert the HSV image back to RGB and display it:


<br>
<br>

### iv)Access and Manipulate Image Pixels

```
# Step 4: Access and Manipulate Image Pixels
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the color of the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]
print(f"Modified pixel value at (200, 200): {image[200, 200]}")
```
![image](https://github.com/user-attachments/assets/66bf0b1a-3b5a-4da3-a159-90b507f5eeed)
<br>
<br>

### v)Image Resizing
```
# Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/56c20463-efc2-4869-b6a3-e50fda8cc4fa)

<br>
<br>

### vi)Image Cropping:

```
# Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/c9f1404f-7951-4326-bc1b-efa8acb57da6)

<br>
<br>

### vii)Image Flipping

```
# Flip the original image horizontally and display it
flipped_horizontally = cv2.flip(image, 1)
cv2.imshow('Horizontally Flipped Image', flipped_horizontally)
cv2.waitKey(0)

# Flip the original image vertically and display it
flipped_vertically = cv2.flip(image, 0)
cv2.imshow('Vertically Flipped Image', flipped_vertically)
cv2.waitKey(0)
```

### Flip the original image horizontally and display it:
![image](https://github.com/user-attachments/assets/afc3e98b-15ef-4188-a3c9-b281eeae8db6)

### Flip the original image vertically and display it:
![image](https://github.com/user-attachments/assets/07e2be4b-5245-4cc6-aa72-05e060659bc4)

<br>
<br>

### viii)Write and Save the Modified Image

```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
![image](https://github.com/user-attachments/assets/6067a52f-78b8-464b-a93c-b15960bb302d)
<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







