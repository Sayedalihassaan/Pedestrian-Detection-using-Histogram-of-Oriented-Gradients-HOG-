## Pedestrian Detection using Histogram of Oriented Gradients (HOG)
This project implements a pedestrian detection system using the Histogram of Oriented Gradients (HOG) descriptor with OpenCV in Python. It aims to detect people in an image by applying the HOG descriptor and a pre-trained SVM detector, drawing bounding boxes around detected individuals. The project is a starting point for learning about HOG-based object detection in computer vision.
Note: The current code has issues (image loading error and missing imutils module) that need to be resolved for full functionality. See Known Issues for details.
## Table of Contents

Project Overview
Features
Requirements
Installation
Usage
Project Structure
Known Issues
Contributing
License
Acknowledgements

Project Overview
The Pedestrian Detection using HOG project uses OpenCV's HOGDescriptor to detect pedestrians in an image. It leverages a pre-trained SVM detector (HOGDescriptor_getDefaultPeopleDetector) to identify human figures and draws red bounding boxes around them. The project is intended for educational purposes to explore HOG-based object detection techniques.
Features

Pedestrian detection using HOG descriptor and SVM classifier.
Visualization of detected pedestrians with bounding boxes.
Configurable detection parameters (e.g., window stride, padding, scale).
Simple Python script using OpenCV for image processing.
Potential for non-maximum suppression (NMS) to refine detections (requires imutils).

Requirements
To run this project, you need the following:

Python 3.11 or higher
An input image file (e.g., pexels-photo-109919.jpeg)

Python Libraries

opencv-python
imutils (optional, for non-maximum suppression; currently missing in the code)

Installation
Follow these steps to set up the project locally:

Clone the Repository
git clone https://github.com/your-username/hog-pedestrian-detection.git
cd hog-pedestrian-detection


Set Up a Virtual Environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install Dependencies
pip install -r requirements.txt

The requirements.txt should include:
opencv-python
imutils


Prepare Input Image

Place an image file (e.g., pexels-photo-109919.jpeg) in the project directory or update the image path in the script.
Ensure the image path is correct to avoid loading errors.



Usage

Ensure the input image is available and the path in the script is correct.
Run the pedestrian detection script:python hog_pedestrian_detection.py


The script will:
Load and resize the input image to 800x600 pixels.
Apply the HOG descriptor with the pre-trained SVM detector.
Draw red bounding boxes around detected pedestrians.
Display the output image in a window.


Press any key to close the window and exit the application.

Example Output
The output window displays the input image with red rectangles around detected pedestrians. If non-maximum suppression is implemented (with imutils), overlapping boxes can be merged for cleaner results.
Project Structure
hog-pedestrian-detection/
├── images/
│   ├── pexels-photo-109919.jpeg # Input image file
├── hog_pedestrian_detection.py   # Main script for pedestrian detection
├── Histogram of Oriented Gradients (HOG).ipynb # Jupyter notebook with the code
├── requirements.txt             # List of Python dependencies
├── README.md                    # Project documentation

Known Issues
The current code has the following issues:

Image Loading Error:

The script fails with an OpenCV error: (-215:Assertion failed) !ssize.empty() in function 'cv::resize'.
This occurs if the image fails to load (e.g., incorrect path or corrupted file). Add error handling to check if the image is loaded correctly:img = cv2.imread("path/to/image.jpg")
if img is None:
    raise ValueError("Failed to load image. Check the file path.")




Missing imutils Module:

The code attempts to import imutils.object_detection.non_max_suppression but the module is not installed.
To fix, install imutils (pip install imutils) and integrate non-maximum suppression to reduce overlapping bounding boxes.


Code Execution:

The main() function is defined but the error in image loading prevents it from running. Fix the image loading issue to test the HOG detection.



Contributions to resolve these issues are welcome! See Contributing.
Contributing
Contributions are welcome, especially to fix the known issues! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit (git commit -m "Add feature").
Push to the branch (git push origin feature-branch).
Open a Pull Request.

Please ensure your code follows the project's coding style and includes relevant tests.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgements

OpenCV for providing the HOGDescriptor and image processing utilities.
imutils for non-maximum suppression utilities (to be implemented).
Inspiration from computer vision tutorials on pedestrian detection.

For any questions or issues, please open an issue on the GitHub repository.
