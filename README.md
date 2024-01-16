# Camera Web Server

This repository contains the code for a web server that interacts with an ESP32-CAM module to capture and process images. The server is built using Node.js and Express, and it utilizes the Google Cloud Vision API for image analysis.

## File Description
The main file in this repository is `server.js`, which serves as the entry point for the web server. It includes routes for capturing images from the ESP32-CAM, performing object detection, and analyzing emotions in the captured images.

## Dependencies
The server relies on several Node.js packages, including:
- Express: for handling HTTP requests and serving static files
- Axios: for making HTTP requests to the ESP32-CAM
- @google-cloud/vision: for integrating with the Google Cloud Vision API

## Functionality
1. **Image Capture**: The `/capture` endpoint sends a capture command to the ESP32-CAM, retrieves the captured image, saves it locally, and performs label detection using the Google Cloud Vision API.

2. **Object Detection**: The `/objectscan` endpoint performs label detection on the captured image and returns the detected objects as JSON.

3. **Emotion Analysis**: The `/emotionscan` endpoint performs face detection and emotion analysis on the captured image, returning the likelihood of various emotions for each detected face.

## Configuration
The server requires a `credentials.json` file to authenticate with the Google Cloud Vision API. Additionally, the ESP32-CAM's IP address needs to be configured in the `server.js` file.

## Usage
To run the server, ensure that Node.js is installed, install the required dependencies using `npm install`, and then start the server using `node server.js`.

## Contributing
Contributions to this project are welcome. Feel free to submit issues or pull requests.
