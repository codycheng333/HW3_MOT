# HW3_MOT
kalman filter motion prediction based on Yolo3 detection for ball Movement

Original videos are "Ball.mp4", '2Ball.avi'

Part1:

  what am i doing here is using yolo3 to detect the ball and put bbox on that
  hard coding on only showing the ball detection (code will still detect every classes in MS COCO dataset but only shows ball detection
  result here)using NMSBoxes to eliminating multiple bounding boxes
  so that store the Bbox center inforamtion into the query, im detecting/ storing the information per frame so as the kalman filter for
  input taking. 

  and after getting the center of the detected ball here, putting a tracking id on that and store the correspond center 
  as we calculate the distance of current center and center of last frame to determine where or not it's the same object 
  (The closer the points are, the greater the probability that we are tracking the same object)
  if distance is lower than a centain threshold here, it is same object and using same tracking id. otherwise update tracking id. 

  now i have deteced object with id, using Kalman filter to predict the location of the detected object, storing that inforamtion


  tracking_objects[object_id] = {[detect_centerx], [detect_centery], [kalman_centerx], [kalman_centery]}
  cv2 showing the detection box and kalman predicted location


Part2 generated videos are 'One_Ball_Detect', 'Two_Ball_Detect'

Part3 generated videos are 'One_Ball_Kalman', 'Two_Ball_Kalman'
