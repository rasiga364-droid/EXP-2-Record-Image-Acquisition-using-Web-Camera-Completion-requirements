# EXP-2-Record-Image-Acquisition-using-Web-Camera-Completion-requirements
# Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1.Write the frame as a JPG file

2.Display the video

3.Display the video by resizing the window

4.Rotate and display the video

# Software Used

• Anaconda – Python 3.7


• Jupyter Notebook / VS Code

• OpenCV (cv2)


# Algorithm

# Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

# Step 2:
Capture frames continuously from the webcam.

# Step 3:
Save a frame as a JPG image using cv2.imwrite().

# Step 4:
Display the live video stream using cv2.imshow().

# Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

# Program

Developed By: Rasiga S


Register No: 212225220081

# Output

# i) Write the frame as JPG image
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
<img width="465" height="457" alt="image" src="https://github.com/user-attachments/assets/e60f5252-8cd2-4960-afb3-ca3dff5250c1" />


# ii) Display the video
```
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

<img width="550" height="417" alt="image" src="https://github.com/user-attachments/assets/279201d3-6b9d-4869-993e-86a8ddefa59b" />



# iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```



<img width="273" height="413" alt="image" src="https://github.com/user-attachments/assets/b123839f-3003-4f4c-bf9e-6fe43932864e" />



# iv) Rotate and display the video
```
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

<img width="312" height="416" alt="image" src="https://github.com/user-attachments/assets/0929bd1f-2617-4698-9d1d-c946b072ab3a" />


# Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
