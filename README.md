# Face-to-Music: Emotion-Based Music Recommendation System

This project is a web application that recommends music based on the user's facial emotions. It uses a computer vision model to detect the user's emotion and then suggests a playlist of songs that match that emotion.

## How it Works

The application uses the Flask web framework to create the user interface. The user's webcam feed is captured and processed in real-time. A pre-trained deep learning model analyzes the user's face to detect their emotion. Based on the detected emotion, the application fetches a corresponding playlist of songs and displays them to the user.

### Key Components:

* **`app.py`**: The main Flask application file that handles the web interface and video streaming.
* **`camera.py`**: This script contains the code for capturing video from the webcam, detecting faces, and predicting emotions using a pre-trained Keras model (`model.h5`). It also includes the logic for recommending music based on the detected emotion.
* **`train.py`**: This file contains the code for training the emotion detection model. It uses the Keras library with a TensorFlow backend to build and train a convolutional neural network (CNN).
* **`Spotipy.py`**: This script appears to be an initial prototype for interacting with the Spotify API to fetch track information.
* **`songs/`**: This directory contains CSV files with lists of songs for different emotions (e.g., `happy.csv`, `sad.csv`).

## Features

* **Real-time Emotion Detection**: The application uses a Haar Cascade classifier to detect faces in the webcam feed and a pre-trained CNN to classify emotions into one of seven categories: Angry, Disgusted, Fearful, Happy, Neutral, Sad, or Surprised.
* **Emotion-Based Music Recommendations**: For each detected emotion, the application recommends a playlist of 15 songs.
* **Web-Based Interface**: The application provides a simple web interface to display the webcam feed and the music recommendations.

## Setup and Usage

### Prerequisites

* Python 3
* The Python packages listed in `requirements.txt`. You can install them using pip:

    ```bash
    pip install -r requirements.txt
    ```

### Running the Application

1.  Make sure you have all the required files and directories in the same folder.
2.  Run the Flask application:

    ```bash
    python app.py
    ```
3.  Open your web browser and go to `http://127.0.0.1:5000/` to view the application.

## Model Training

The emotion detection model was trained on a dataset of facial images. The training script (`train.py`) uses a CNN with several convolutional, max-pooling, and dropout layers. The model is compiled with the Adam optimizer and trained for 75 epochs. The trained model weights are saved in the `model.h5` file.
