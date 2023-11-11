# Pedestrian Detection Using Histograms of Oriented Gradients (HOG)

## Overview
This project implements a pedestrian detection system using the Histogram of Oriented Gradients (HOG) method combined with a Support Vector Machine (SVM) for classification. The approach is rooted in computer vision and is highly effective for human detection tasks.

## Project Description
Pedestrian detection is a fundamental aspect of computer vision. This project focuses on demonstrating the efficiency and implementation of the Histogram of Oriented Gradients (HOG) technique for detecting pedestrians, particularly those who are completely visible and standing up. 

### Understanding Histogram of Oriented Gradients (HOG)
HOG is a feature descriptor used extensively in computer vision for object detection, especially effective in human detection. The HOG descriptor involves several mathematical operations:

- **Gradient in Images**: The gradient components $G_x$ and $G_y$ at each pixel are calculated using convolution with Sobel kernels. For $G_x$ (horizontal edges), a kernel of
$$\begin{Bmatrix}
  -1&0&1 \\
  -2&0&2 \\
  -1&0&1
\end{Bmatrix}$$

  is used, and for $G_y$ (vertical edges), a kernel of

$$\begin{Bmatrix}
  -1&-2&-1 \\
   0&0& 0 \\
   1&2&1
\end{Bmatrix}$$

  is applied. Here, $I$ represents the intensity of the image.

- **Histograms of Gradients**: For each pixel, the gradient magnitude $G$ and orientation $\Theta$ are computed:
  $$G = \sqrt{G_x^2 + G_y^2}$$
  $$\Theta = \arctan\left(\frac{G_y}{G_x}\right)$$
  These are used to populate histograms for small regions (cells) in the image.

- **Detection Using HOG**: The histograms of all cells within a detection window are combined to form a feature vector. This vector is used in a machine learning model, like SVM, for classification.

### Support Vector Machine (SVM)
SVM, a supervised machine learning model, is employed for classification tasks in this project. It functions by finding an optimal hyperplane that maximizes the margin between different classes. The decision function for a linear SVM is:
$$f(x) = \text{sign}(w^T x + b)$$
where $w$ is the weight vector, $x$ is the feature vector, and $b$ is the bias. In non-linear cases, SVM utilizes kernel functions like linear, polynomial, or radial basis function (RBF) to transform the input space for classification.

In our pedestrian detection system, SVM classifies the extracted HOG features into two categories: pedestrian and non-pedestrian.


## Technological Overview
This project utilizes several key technologies and libraries, which are integral to its implementation:

1. **Python**: The primary programming language used for implementing the project.
2. **OpenCV (Open Source Computer Vision Library)**: A powerful library used for various image processing and computer vision tasks, including the implementation of HOG.
3. **NumPy**: A fundamental package for scientific computing with Python, used for efficient operations on multi-dimensional arrays.
4. **Matplotlib**: A plotting library for Python and its numerical mathematics extension NumPy. It provides an object-oriented API for embedding plots into applications.

## Project Workflow
The workflow of the project is structured as follows:

1. **Initial Setup**: Importing necessary libraries like OpenCV, NumPy, and Matplotlib.
2. **Data Visualization**: Utilizing Matplotlib to plot histograms and visualize data, aiding in understanding the distribution of features.
3. **Image Processing for HOG**: Preparing images and using the Sobel operator to calculate gradients. This is essential for understanding the orientation and magnitude of image gradients.
4. **HOG Descriptor Initialization**: Setting up the HOG descriptor, which is crucial for extracting features from images.
5. **SVM Detector Setup**: Initializing the SVM detector with the HOG descriptor for pedestrian detection.
6. **Video Processing**: Loading a video stream and processing it frame by frame to detect pedestrians.
7. **Pedestrian Detection**: Applying the HOG descriptor and SVM to each frame for detecting pedestrians.
8. **Result Visualization**: Drawing bounding boxes around detected pedestrians and displaying the results using Matplotlib.
9. **Video Analysis Conclusion**: Releasing video resources post-analysis.

## Code Overview
The codebase is structured into several key sections, each fulfilling a specific role in the pedestrian detection pipeline:

- **Library Imports**: Importing essential libraries (OpenCV, NumPy, Matplotlib) necessary for the project.
- **Data Visualization**: Utilizing Matplotlib for plotting histograms and visualizing data, which is crucial in understanding feature distributions.
- **Feature Calculation and HOG Preparation**: Implementing gradient calculations using the Sobel operator and preparing for HOG feature extraction.
- **HOG Descriptor and SVM Detector**: Initializing the HOG descriptor for feature extraction and the SVM detector for pedestrian classification.
- **Video Frame Processing**: Loading and processing video frames to apply pedestrian detection.
- **Detection and Result Visualization**: Applying HOG and SVM to detect pedestrians in video frames and visualizing the results with bounding boxes.

## Usage
To run this project, follow these steps:

1. Clone the repository to your local machine.
2. Ensure that Python and all the required libraries (OpenCV, NumPy, Matplotlib) are installed.
3. Navigate to the project directory and open the Jupyter Notebook (`Pedestrian_Detection_Using_HOG.ipynb`).
4. Run the Jupyter Notebook cells in sequence to execute the pedestrian detection process.


$$\begin{Bmatrix}
1&2&3\\
4 & 6 & 8
\end{Bmatrix} \times \begin{Bmatrix}
8 & 5 \\
7 & 3 \\
1 & 8 
\end{Bmatrix}$$
