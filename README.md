# EXP-2-Record-Image-Acquisition-using-Web-Camera


### Developed By:

**Name:** Dharshini J

**Register Number:** 212224240036
## Aim

To write a Python program using OpenCV to capture an image from a web camera and perform the following operations:

1. Capture and save an image from the web camera.
2. Read and display the captured image.
3. Display the live video stream.
4. Display the video by resizing the frames.
5. Rotate and display the video.

---

## Software Used

- Python
- OpenCV (`cv2`)
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

---

##  Algorithm

### Step 1: Import Required Libraries

Import OpenCV, Matplotlib, and other required libraries for image acquisition and display.

### Step 2: Capture an Image Using Web Camera

1. Initialize the web camera using `cv2.VideoCapture(0)`.
2. Capture a frame using `cap.read()`.
3. Save the captured frame as a JPG image using `cv2.imwrite()`.
4. Release the camera using `cap.release()`.

### Step 3: Read and Display the Captured Image

1. Read the saved image using `cv2.imread()`.
2. Convert the image from BGR to RGB.
3. Display the captured image using Matplotlib.

### Step 4: Display the Video

1. Initialize the web camera.
2. Capture video frames continuously using a loop.
3. Convert each frame from BGR to RGB.
4. Display the frames using Matplotlib.
5. Use `clear_output(wait=True)` to update the displayed frames.
6. Release the camera after capturing the frames.

### Step 5: Display the Resized Video

1. Initialize the web camera.
2. Capture video frames.
3. Resize each frame using `cv2.resize()`.
4. Convert the resized frame from BGR to RGB.
5. Display the resized video using Matplotlib.

### Step 6: Rotate and Display the Video

1. Initialize the web camera.
2. Capture video frames.
3. Rotate each frame using `cv2.rotate()`.
4. Convert the rotated frame from BGR to RGB.
5. Display the rotated video using Matplotlib.

---

## 💻 Program


### 1. Capture an Image Using Web Camera

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

```python
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

```python
captured_image = cv2.imread('captured_frame.jpg')
```

```python
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

### 2. Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### 3. Display the Video by Resizing the Frame

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### 4. Rotate and Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

---

## Output

The following outputs are obtained:

### i) Captured Image Saved as JPG

<img width="581" height="427" alt="image" src="https://github.com/user-attachments/assets/07ee0c3f-35ba-4075-b4c8-5cc6cdb86a14" />


### ii) Display the Video

<img width="532" height="393" alt="image" src="https://github.com/user-attachments/assets/b99c5b62-c7c6-4fc0-a23a-ac858d9580d0" />


### iii) Display the Resized Video

<img width="318" height="412" alt="image" src="https://github.com/user-attachments/assets/bdbc65f0-d6fa-452d-9327-74d1874975a5" />


### iv) Rotate and Display the Video

<img width="338" height="393" alt="image" src="https://github.com/user-attachments/assets/b60ae5bd-5919-4de6-bd02-638b13d67a54" />


---

## Result

Thus, image acquisition using a web camera was successfully performed using Python and OpenCV. The captured image was saved in JPG format, and video processing operations such as displaying, resizing, and rotating the video frames were successfully demonstrated.

---
