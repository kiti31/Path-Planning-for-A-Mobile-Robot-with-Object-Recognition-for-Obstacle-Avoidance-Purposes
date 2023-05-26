# Abstract
This project presents a comprehensive approach for mobile robot navigation in simulated environments, utilizing both MATLAB for object detection and classification, and CoppeliaSim with Lua for path planning, obstacle avoidance, and localization. The Pioneer P3DX robot is used as a test platform to evaluate the performance of the proposed system, which aims to enhance the robot's navigation capabilities in both static and dynamic environments. The proposed method combines image segmentation techniques, such as Edge Detection and Otsu thresholding in MATLAB, with advanced control algorithms in CoppeliaSim, including Proportional-Integral-Derivative (PID) controller algorithm for line following, Potential Field Algorithm for obstacle avoidance, and Simultaneous Localisation and Mapping (SLAM) technique for localization. The goal is to develop a navigation system that can handle both static and dynamic environments.

# MATLAB 
## Algorithm and Techniques 
### Image Pre-processing 
Image pre-processing is a crucial step in many image analysis tasks, and it involves a series of operations applied to an image to enhance its visual quality or make it more suitable for further analysis. One of the most important aspects of image pre-processing is noise reduction. Noise can significantly degrade the quality of an image, and it can also affect the accuracy of further analysis. Median and Gaussian filters are commonly used for noise reduction, as they are able to effectively remove noise while preserving important image features. 

Another important aspect of image pre-processing is image enhancement. This includes operations such as histogram equalization and unsharp mask filter which are used to improve the visual appearance of the image. Histogram equalization is a technique that stretches the intensity range of an image, making it more visually pleasing, while unsharp mask filter is used to sharpen the image. These techniques can help to bring out important details in the image and make it more suitable for further analysis.

### Image Segmentation 
Image segmentation is the process of partitioning an image into multiple regions, each corresponding to a different object or background. There are many different techniques that can be used for image segmentation, and two common methods are edge-based thresholding and Otsu thresholding. 
Edge-based thresholding is a technique that involves first detecting edges in an image using an edge detection algorithm such as Sobel or Canny. The edge image is then thresholded using a threshold value that is determined based on the histogram of the edge image. This thresholded image is used as a mask to segment the original image into different regions. 

Otsu thresholding, on the other hand, is a method of automatic thresholding that uses the statistical properties of the image's histogram to determine the optimal threshold value. This technique is based on the idea that the image contains two classes of pixels, the object pixels and the background pixels, and the optimal threshold value is chosen to minimize the intra-class variance of these two classes. This method can be used to separate the object from the background in an image. 

### Classification 
Image detection and classification are important tasks in the field of computer vision, and there are many different techniques and algorithms that can be used to accomplish them. One of the most popular and widely used algorithms for image detection and classification is YOLO (You Only Look Once). 
YOLO is a real-time object detection algorithm that uses a single neural network to predict bounding boxes and class probabilities for objects in an image. It divides the input image into a grid of cells and predicts the bounding boxes and class probabilities for each cell. This allows it to detect multiple objects in an image in a single pass, making it much faster than traditional methods such as R-CNN and Faster R-CNN. 

YOLO also uses anchor boxes, which are pre-defined bounding boxes, to help improve the accuracy of object detection. It also uses a technique called non-maximum suppression (NMS) to remove overlapping bounding boxes, resulting in a more precise detection. 

YOLO has been shown to achieve state-of-the-art results on several benchmark datasets and it has been widely adopted in many real-world applications such as surveillance, self-driving cars and video analysis. 

![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/c51f0922-359a-475e-9b89-d4d41bfb8518)

### Distance
In MATLAB, there are a variety of algorithms and techniques that can be used to calculate the distance of an object from a robot. One common method is using stereo vision, which involves taking two images of the same scene from slightly different perspectives and using the disparity between the images to calculate the distance to the object. Another popular method is using time-of-flight (ToF) sensors, which measure the time it takes for a pulse of light to travel to an object and back, providing a precise distance measurement. Lidar sensors, which use laser beams to measure the distance, can also be used in combination with MATLAB's Robotics System Toolbox for distance calculation. Additionally, ultrasonic sensors, which use high-frequency sound waves, can also be utilized to calculate the distance to an object. These are just a few examples of the various techniques and algorithms that can be used to calculate the distance of an object from a robot in MATLAB, depending on the application, the range, precision, and the environment the robot is operating, different methods may suit better.

## Implementation
### Image Pre-processing
Before any image segmentation task, image pre-processing is a crucial step that occurs to improve the quality of the image and make it more suitable for further analysis. In MATLAB, image pre-processing involves a series of operations that are applied to the image. Figure 4.3 below shows the original unprocessed images.
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/0bde9d32-0357-4c41-9c49-151bf8a53ef9)
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/ddd4ce62-1b0c-4393-9da0-22db5ae503f6)
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/08469c33-e120-41e1-9bae-0d22b4c6c574)

### Image Segmentation
Once the image has been pre-processed, it is ready for image segmentation. Two common techniques that are used for image segmentation are edge detection and Otsu thresholding.
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/0b92dd07-6e9b-449f-ad99-b00331840cf7)
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/c6b69a69-8fa4-4752-86e6-964af36d89bb)
![image](https://github.com/kiti31/Path-Planning-for-A-Mobile-Robot-with-Object-Recognition-for-Obstacle-Avoidance-Purposes/assets/93535936/8e20a958-59e0-4fd4-a698-024c858c72cd)

These image segmentation techniques, Edge detection and Otsu thresholding, can be used to extract meaningful regions from the image and provide valuable information for further image analysis such as object recognition or image classification. The combination of these techniques can be useful to extract meaningful regions from an image, but the choice of the method may depend on the image and the goal of the analysis.

It's worth mentioning that, the outputs of these techniques can be used in combination with other techniques like blob analysis, connected component analysis, or region growing to improve the accuracy and the robustness of the segmentation.

In addition, it is important to note that the parameters used in these techniques such as the threshold value, the kernel size, and the sigma value in the Gaussian filter can affect the results, and they may need to be adjusted depending on the image and the desired results.

