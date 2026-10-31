# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** Pradeep.M  
- **Register Number:** 212225220071

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('KISHORE.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 2. Print the image width, height & Channel.
```python

image = cv2.imread('KISHORE.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```

#### 3. Display the image using matplotlib imshow().
```python

plt.imshow(img_rgb, cmap='viridis') 
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
image = cv2.imread('KISHORE.jpg') 
img = cv2.imread('KISHORE.png',image)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img = cv2.imread('KISHORE.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
crop = img_rgb[0:600,200:550] 
plt.imshow(crop[:,:,::-1])
plt.title("Cropped Region")
plt.axis("off")
plt.show()
crop.shape
```

#### 8. Resize the image up by a factor of 2x.
```python
image = cv2.imread('KISHORE.jpg')
resized_image = cv2.resize(image, (1600// 2, 1200 // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 9. Flip the cropped/resized image horizontally.
```python

image = cv2.imread('KISHORE.jpg')
flipped_horizontally = cv2.flip(image, 1)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
img=cv2.imread('Apollo-11-launch.jpg',cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
text = cv2.putText(img_rgb, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("New image")
plt.show()  

```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = magenta
rect_color = (255,0,255)
cv2.rectangle(img_rgb, (400, 100), (800, 650), rect_color, 3)  
```

#### 13. Display the final annotated image.
```python
plt.title("Annotated image")
plt.imshow(img_rgb)
plt.show()
```

#### 14. Read the image ('Boy.jpg').
img =cv2.imread('boy.jpg',cv2.IMREAD_COLOR)
img_rgb= cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 
```

#### 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)
# matrix_ones = 
n = np.ones(img_rgb.shape, dtype="uint8") * 50
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python

```

#### 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
matrix1 = np.ones(img_rgb.shape, dtype="float32") * 1.1
matrix2 = np.ones(img_rgb.shape, dtype="float32") * 1.2
img_higher1 = cv2.multiply(img.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img.astype("float32"), matrix2).clip(0,255).astype("uint8")
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
plt.figure(figsize=(10,5))
plt.subplot(1,3,1), plt.imshow(img), plt.title("Original Image"), plt.axis("off")
plt.subplot(1,3,2), plt.imshow(img_higher1), plt.title("Higher Contrast (1.1x)"), plt.axis("off")
plt.subplot(1,3,3), plt.imshow(img_higher2), plt.title("Higher Contrast (1.2x)"), plt.axis("off")
plt.show()
```

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

#### 21. Merged the R, G, B , displays along with the original image
```python
image = cv2.imread('KISHORE.jpg')
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.cvtColor(img, cv2.COLOR_HSV2RGB)
combined = np.concatenate((img_rgb, merged_hsv), axis=1)
plt.figure(figsize=(10, 5))
plt.imshow(combined)
plt.title("Original Image  &  Merged HSV Image")
plt.axis("off")
plt.show()
```

## Output:
<img width="315" height="415" alt="Screenshot 2026-10-30 214235" src="https://github.com/user-attachments/assets/c05cb0d6-f245-4f02-9e77-9591085c623f" />
<img width="317" height="416" alt="Screenshot 2026-10-30 214242" src="https://github.com/user-attachments/assets/0c91d393-7d49-442c-9d2f-c8662f454b95" />
<img width="317" height="417" alt="Screenshot 2026-10-30 214247" src="https://github.com/user-attachments/assets/04a33178-7195-480c-a32f-23eae22ba9e4" />
<img width="316" height="411" alt="Screenshot 2026-10-30 214254" src="https://github.com/user-attachments/assets/46a5a030-e2f3-4ca3-8693-6ff33bde0df9" />
<img width="317" height="412" alt="Screenshot 2026-10-30 214311" src="https://github.com/user-attachments/assets/72c84cbd-7a42-4b06-a159-0a4c039c2024" /

<img width="311" height="410" alt="Screenshot 2026-10-30 214317" src="https://github.com/user-attachments/assets/3b07fd24-84d8-47ff-a154-e99ec63e1e93" />

<img width="326" height="410" alt="Screenshot 2026-10-30 214322" src="https://github.com/user-attachments/assets/0bf1a52b-59fe-4474-9412-762fdba6ad6d" />

<img width="320" height="447" alt="Screenshot 2026-10-30 214327" src="https://github.com/user-attachments/assets/be021653-437e-4880-8e1d-19dfc7d3920d" />

<img width="312" height="412" alt="Screenshot 2026-10-30 214333" src="https://github.com/user-attachments/assets/401b68f7-cc9f-4ff6-b17f-00259b8d4fde" />

<img width="523" height="412" alt="Screenshot 2026-10-30 214338" src="https://github.com/user-attachments/assets/3b1ee85e-8527-4c44-ae4a-1acbed6814ed" />

<img width="415" height="407" alt="Screenshot 2026-10-30 214343" src="https://github.com/user-attachments/assets/66bfa4c8-cac6-4f9c-b2df-180485ab1725" />

<img width="320" height="427" alt="Screenshot 2026-10-30 214349" src="https://github.com/user-attachments/assets/416b3af6-33bc-4843-9bfc-ad1a2ee300a2" />

<img width="316" height="415" alt="Screenshot 2026-10-30 214354" src="https://github.com/user-attachments/assets/8f31227e-202d-4de0-aa7d-6e4ee6362b70" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
