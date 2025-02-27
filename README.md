# Face-Detection-Virtual-Camera

This project utilizes OpenCV for real-time face detection and streams the processed video through a virtual camera. 

The virtual camera output can be used by any application that supports video input, such as video conferencing or streaming software.

You can use this to draw a box over your face in OBS studio webcam, or even ZOOM meetings and discord calls.


## Requirements

- Python 3.x
- OpenCV (cv2), numpy, and pyvirtualcam libraries
```
pip install opencv-python numpy pyvirtualcam
```

## Usage

1. Ensure your webcam is connected and functional.
2. Run the script, which will start a virtual camera with face detection enabled.
3. The script will display the video stream with a green rectangle drawn around detected faces.
4. The processed video feed will also be sent to a virtual camera, which can be used in video conferencing or other applications that support webcam input.
To stop the script, simply press the q key.

## How it works

1. Capture Video Stream: The script captures the video stream from your webcam using OpenCV.
2. Face Detection: It uses a pre-trained Haar Cascade Classifier to detect faces in each frame of the video.
3. Virtual Camera: The processed video (with detected faces highlighted by rectangles) is sent to a virtual camera using the pyvirtualcam library, allowing you to use the video feed in other applications as if it were a webcam.
4. Real-Time Display: The video feed with detected faces is shown on your screen as well.


## Script Walkthrough

- Face Cascade Classifier: This uses OpenCV's pre-trained model to detect faces in each frame.
- Video Capture: Captures the video stream from the default camera (0).
- Virtual Camera: Creates a virtual camera to send the processed frames to.
- Frame Processing: For each frame:
  - Converts the frame to grayscale.
  - Detects faces in the frame.
  - Draws rectangles around detected faces.
- Converts the frame back to RGB (as required by pyvirtualcam).
- Exit: The script runs in a loop, continuously processing frames, until the user presses the q key to exit.

## Troubleshooting
- Virtual Camera Not Recognized: Ensure pyvirtualcam is properly installed and supported by your system.
- Face Detection Issues: The accuracy of face detection can vary based on lighting conditions and the quality of the webcam.
