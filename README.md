# Gesture Volume Control Using OpenCV and MediaPipe

This project utilizes OpenCV and MediaPipe to control the system volume using hand gestures detected via a webcam. When no fingers are shown (all fingers folded), the system volume is muted.

## Features

- Detect hand and finger positions using MediaPipe.
- Mute the system volume when all fingers are folded.
- Display the frame rate (FPS) on the video feed.

## Requirements

- Python 3.9
- OpenCV 4.10.0.84
- MediaPipe
- Pycaw 20240210
- Pygame 2.6.0

## Installation

1. Clone this repository to your local machine:

    ```sh
    git clone []
    ```

2. Navigate to the project directory:

    ```sh
    cd gesture-volume-control-using-CV
    ```

3. Create a virtual environment: This is highly recommended as opencv caused problem in installation with other modules causing version conflicts

    ```sh
    python -m venv opencv_env 
    ```

4. Activate the virtual environment:

    - On Windows:

      ```sh
      opencv_env\Scripts\activate
      ```

    - On macOS and Linux:

      ```sh
      source opencv_env/bin/activate
      ```

5. Install the required dependencies:

    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. Ensure your webcam is connected and working.

2. Run the `main.py` script:

    ```sh
    python main.py
    ```

3. The script will open a window showing the webcam feed. If you fold all your fingers (show no fingers), the system volume will be muted. (You need to change the cv.videoCapture(this value) to 1 if you have an external camera attached)

4. Press 'q' to exit the program.

## Hand Detector Class present in HandTrackingModule.py 

The `HandDetector` class encapsulates the functionality for detecting hands and fingers using MediaPipe.

### Methods

- `__init__(self, mode=False, max_hands=2, detection_confidence=0.5, tracking_confidence=0.5)`: Initializes the hand detector with the specified parameters.
- `find_hands(self, img, draw=True)`: Processes the input image to detect hands and draw landmarks.
- `findPosition(self, img, handNo=0, draw=True)`: Finds the positions of hand landmarks and returns a list of positions and the bounding box.
- `fingersUp(self)`: Returns a list indicating which fingers are up.
- `findDistance(self, p1, p2, img, draw=True)`: Finds the distance between two specified landmarks.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [MediaPipe](https://mediapipe.dev) for providing the hand tracking solution.
- [OpenCV](https://opencv.org) for the computer vision library.
- [Pycaw](https://github.com/AndreMiras/pycaw) for the audio control library.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or new features.

## Contact

For any questions or inquiries, please contact [sajeevysingh@gmail.com](mailto:sajeevysingh@gmail.com).
