# Google Vision Security Camera
This is a security camera powered by AI that utilizes ESP32-CAM, Node.js, and Google Vision AI API.

This web application performs AI-based analysis on photos captured by an ESP32-CAM device. Users can instruct the connected ESP32-CAM to take photos through the web app. Once the images are received, Google's Vision AI API is employed for tasks such as recognizing objects and emotions in the photos.

ESP32-CAM can connect to wifi, so it displays the photos on a web server. We just created a separate NodeJS webserver that extracts those photos and puts them on its customized web application. Then using Google Vision API it analyzes the photos.

# Steps:
There were two sections for the setup of this project. The first section was hardware. I used C++ and the Arduino IDE to set up the ESP32-CAM. "Random Nerd Tutorial" provided with simple C++ source code which I modified to suit the needs of the project, you can also follow the steps of setting up your camera using this link: https://randomnerdtutorials.com/esp32-cam-video-streaming-web-server-camera-home-assistant/.

The second setup was setting up the web server with Node.js

# Camera Web Server

The web server folder contains the code for the web server that interacts with an ESP32-CAM module to capture and process images. The server is built using Node.js and Express, and it utilizes the Google Cloud Vision API for image analysis.

## File Description
The main file in this repository is `server.js`, which serves as the entry point for the web server. It includes routes for capturing images from the ESP32-CAM, performing object detection, and analyzing emotions in the captured images.

## Requirements:
Arduino IDE, ESP32-CAM, NodeJS, Google Vision AI API
The server relies on several Node.js packages, including:
- Express: for handling HTTP requests and serving static files
- Axios: for making HTTP requests to the ESP32-CAM
- @google-cloud/vision: for integrating with the Google Cloud Vision API

## Functionality
1. **Image Capture**: The `/capture` endpoint sends a capture command to the ESP32-CAM, retrieves the captured image, saves it locally, and performs label detection using the Google Cloud Vision API.

2. **Object Detection**: The `/objectscan` endpoint performs label detection on the captured image and returns the detected objects as JSON.

3. **Emotion Analysis**: The `/emotionscan` endpoint performs face detection and emotion analysis on the captured image, returning the likelihood of various emotions for each detected face.

## Configuration
The server requires a `credentials.json` file to authenticate with the Google Cloud Vision API, which you can get by creating an account. Additionally, the ESP32-CAM's IP address needs to be configured in the `server.js` file, which is provided when you upload your C++ code to the camera using the Arduino IDE.

## Usage
To run the server:
1. Copy the repository and download dependencies using `/npm install`
2. Run the server

<img width="1109" alt="Final" src="https://github.com/usaeedcs/GoogleVisionAPICamera/assets/85361194/4cd54b7d-a843-4362-a2a1-d2a7dc548819">
