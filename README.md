# EXP-2-Record-Image-Acquisition-using-Web-Camera


# Aim:
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file

Display the video

Display the video by resizing the window

Rotate and display the video

# Software Used :
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

# Algorithm:
Step 1: Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2: Capture frames continuously from the webcam.

Step 3: Save a frame as a JPG image using cv2.imwrite().

Step 4: Display the live video stream using cv2.imshow().

Step 5: Resize the frame and rotate it using OpenCV functions, then display the processed frames.

# Program:
Developed By: Name: T GOSHANRAJAN

Register No:212225040098

i) Write the frame as JPG image
```
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
ii) Display the video
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
iii) Display the video by resizing the window
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
iv) Rotate and display the video
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
# Output:

<img width="512" height="410" alt="image" src="https://github.com/user-attachments/assets/d7602f8b-0232-49a2-9481-7c22ebd0027c" />

<img width="512" height="389" alt="image" src="https://github.com/user-attachments/assets/b803a309-4edc-472c-9a8b-c3b0a074d3dd" />


<img width="266" height="389" alt="image" src="https://github.com/user-attachments/assets/90c95a7a-b0bd-4b4e-a8e4-e2dcd44ee31e" />

<img width="297" height="389" alt="image" src="https://github.com/user-attachments/assets/2827056d-c998-428a-a102-252d9e630661" />



# Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
