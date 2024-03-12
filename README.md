# Capturing and Transmitting Data Using Computer Vision

## Overview
This project utilizes computer vision techniques to capture data from a gauge and transmits it to a desired location using an HTTP request. It involves the detection and calibration of circular objects in an image, the measurement of the pointer position, and the conversion of the pointer position to a meaningful value within a defined range.

## Libraries Used
- **OpenCV**: A computer vision and machine learning library providing tools for image and video processing.
- **Numpy**: A Python library for working with multi-dimensional arrays and matrices, enabling efficient data manipulation.
- **Requests**: A Python library for making HTTP requests, facilitating communication with web servers and APIs.
- **JSON**: A built-in Python library for encoding and decoding JSON data, commonly used for exchanging data between a server and a web application.
- **Datetime**: A built-in Python library providing classes for manipulating dates and times.

## Method for Sending Data
The `send_value()` function retrieves the endpoint from environment variables and sends a POST request to the endpoint with the payload containing the temperature value and current time.

## Calibration and Measurement
- The `calibrate_gauge()` function detects circular objects in the image, computes the average values for the detected circles, and draws calibration markers.
- The `get_current_value()` function applies thresholding to the grayscale image, detects lines, and determines the angle at which the pointer is displayed. It then converts this angle to a value within the defined range.

## Main Method
The main method reads individual frames from a video file, calibrates the gauge, and determines the current value on the gauge for each frame. It prints the current value and sends it to the desired location using the `send_value()` function.

## Usage
To run the project, ensure you have the required libraries installed and replace the video file path in the `main()` method with the path to your video file or video stream. Use '0' for the built-in camera or '1' for an external camera. Then, execute the script.

```python
python main.py
