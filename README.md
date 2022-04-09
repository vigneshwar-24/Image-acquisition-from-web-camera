# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
Step 1:
Use VideoCapture(0) to access web camera

Step 2:
Use imread to read the video or image

Step 3:
Use imwrite to save the image

Step 4:
Use imshow to show the video

Step 5:
End the program and close the output video windows by pressing 'q'.
## Program:
### Developed By: Vigneshwar S
### Register No: 212220230058

## i) Write the frame as JPG file


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("live.jpg",frame)
cap.release()
cv2.destroyAllWindows()


## ii) Display the video


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
## Output

### i) Write the frame as JPG image

<img width="487" alt="11" src="https://user-images.githubusercontent.com/77089276/162582804-65fa27d0-744a-4c44-995c-eb86cdae2c10.PNG">


### ii) Display the video

<img width="563" alt="22" src="https://user-images.githubusercontent.com/77089276/162582806-c923a3f4-c2a4-4cd2-8f6a-261c67edd3df.PNG">


### iii) Display the video by resizing the window


<img width="521" alt="33" src="https://user-images.githubusercontent.com/77089276/162582813-b9e31c6d-84ed-4d79-a748-e575e073b72b.PNG">


### iv) Rotate and display the video


<img width="513" alt="44" src="https://user-images.githubusercontent.com/77089276/162582822-de862dd0-38a0-47d0-bc96-1bcc26e76734.PNG">




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
