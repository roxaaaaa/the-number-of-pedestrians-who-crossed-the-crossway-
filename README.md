# the-number-of-pedestrians-who-crossed-the-crossway-

Course Name: BSc (Hons) in Computer Science 

Module Name: Computer Vision 	  

Proposed working title of assignment:  Counting the number of pedestrians who crossed the crossway 

1.	Why have you chosen your particular topic? 

I chose this topic because my first assignment was about Automatic Number Plate Recognition (ANPR). That project helped me learn how to detect vehicles  and define the plate number using computer vision. Now, I want to use similar ideas to track people crossing a crosswalk. This is a new challenge, but it still uses detection and tracking, which I already started learning. 

I think this application could be useful for smart cities. It can help count how many people cross the street and when. This information can be used to improve traffic lights, make streets safer, and plan better walkways. It is a practical use of computer vision that can help people in real life. 

 

2.	What Computer Vision techniques do you propose to use in your assignment? 

In my assignment, I will use object detection to find pedestrians in each video frame. This technique helps the computer recognize people by drawing boxes around them. I will use a model like YOLO (You Only Look Once), which is fast and works well in real-time. It can detect many people at once and tell where they are in the image. 

Next, I will use object tracking to follow each pedestrian as they move across the video. This means the system will give each person a number and keep track of them from frame to frame. I will use a method like Deep SORT, which combines detection with tracking. This helps avoid counting the same person twice and makes sure we only count people who cross the crosswalk. 

Finally, I will define a virtual line/region over the crosswalk area. When a tracked person crosses this line, the system will count them. This part uses logic and coordinates to check movement direction. By combining detection, tracking, and counting, the system gives a total number of pedestrians who crossed the street. 

 

 

3.	Do you have any experience relevant to your proposed assignment?  

I don’t have any relevant experience except computer vision practicals. 

 

4.	In thinking/reading about this assignment identify a primary source and some secondary sources (e.g.: a peer reviewed paper and/or book)? References required here. 

  

Primary: 

G, S., E, S. and M, D. (2024). YOLOv8 for Pedestrian Detection: A Comparative Study for Pedestrian Detection. 2024 Third International Conference on Electrical, Electronics, Information and Communication Technologies (ICEEICT), [online] pp.1–7. doi:https://doi.org/10.1109/iceeict61591.2024.10718372. 

Razzok, M., Badri, A., El Mourabit, I., Ruichek, Y. and Sahel, A. (2023). Pedestrian Detection and Tracking System Based on Deep-SORT, YOLOv5, and New Data Association Metrics. Information, [online] 14(4), p.218. doi:https://doi.org/10.3390/info14040218.  

Ultralytics (2025). Bounding Box - Learn how bounding boxes enable object detection, AI, and machine learning systems. Explore their role in computer vision applications! [online] Ultralytics.com. Available at: https://www.ultralytics.com/glossary/bounding-box. 

 

Secondary: 

Sanyam (2022). Understanding Multiple Object Tracking using DeepSORT. [online] LearnOpenCV. Available at: https://learnopencv.com/understanding-multiple-object-tracking-using-deepsort/. 

roboflow.com. (n.d.). YOLOv8: A New State-of-the-Art Computer Vision Model. [online] Available at: https://yolov8.com/. 

Roboflow (2025). DeepSORT - Trackers. [online] Roboflow.com. Available at: https://trackers.roboflow.com/develop/trackers/core/deepsort/tracker/. 

Secondary resources were used for personal better understanding of the topic. 

 

5.	Please include a 500-word draft assignment proposal here.  

Indicate clearly what your assignment application is going to be.  

(Include: how you will measure the success of your application; The expected results) 

YOLOv8 is used to detect pedestrians in each frame of the video. It is a fast and accurate detection model that draws boxes around every detected person and gives a confidence score showing how sure it is that the object is a pedestrian. For each frame, the output will include the box coordinates, the class label “person,” and the confidence score . (G, E and M, 2024). Th detentions will be top-left coordinates with width and height (x, y, w, h). (Ultralytics, 2025) 

The detections from YOLOv8 will be then passed to DeepSORT, which tracks each pedestrian across the video. DeepSORT gives every person a unique ID and keeps following them even if they are briefly hidden or look slightly different in the next frame. It uses a Kalman filter to predict where each pedestrian will move next (Razzok et al., 2023).After that, it tries to match new YOLOv8 detections with existing tracks based on two things: how close the new detection is to the predicted position (motion similarity) and how similar the person’s appearance looks compared to before (appearance similarity). DeepSORT uses a deep learning model to extract special features from each person’s appearance, which helps keep the same ID even when people overlap or are partly hidden. When a new detection matches an existing track, the Kalman filter updates the person’s position and speed (Razzok et al., 2023). If a detection does not match any existing track, a new one is created. When a tracked person disappears for several frames, their track is marked as lost and later removed. 

To count how many pedestrians cross the road, the system will use virtual lines/zones drawn on the video. One line marks the start of the crossing area, and another marks the end. The system follows each pedestrian’s movement using their DeepSORT ID. A pedestrian is counted as having crossed when their ID first passes the entry line or zone from one side and then passes the exit line or zone in the correct direction. To prevent counting the same person twice, once an ID triggers a count, it is marked as “counted.” If the same person crosses again later, they must complete another full crossing to be counted again. 

The expected result is a working prototype that can process video input, detect and track pedestrians, and output an accurate count of how many people cross the crosswalk. For measurng success, I will count manually people who crossed and compare the results with application count for the same video footage. I will define accuracy. I will define the system successful if it reaches 85% accuracy. 

 


6.	Please indicate clearly what data/dataset your assignment application is going to use.  


https://youtu.be/gWA7O3Uz7Lc?si=UvmTRmChTtWi7t3N 

 

 

 
