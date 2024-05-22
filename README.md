# YOLOv7-Pose-on-Custom-Dataset for Grocery Products:

## Keypoint detection on a custom dataset of grocery products with 8 keypoints. In this tutorial, we will train our YOLOv7 model to detect these 8 custom keypoints on grocery products.

Roboflow: data set:
https://app.roboflow.com/lamar-university-venef/retail-products-vem9o/2

<img width="190" alt="Screenshot 2024-05-22 at 2 43 40 PM" src="https://github.com/sam02425/YOLOv7-POSE-on-Custom-Dataset/assets/31678223/f5cdcf41-942f-4171-8bba-ae7e03f66bfe">
<img width="358" alt="Screenshot 2024-05-22 at 2 44 38 PM" src="https://github.com/sam02425/YOLOv7-POSE-on-Custom-Dataset/assets/31678223/1d0d4c3c-1c91-40aa-876b-b7fa8d16403a">



# Data Prepration:

Install Docker on your system if you haven't already. You can download it from the official website: https://www.docker.com/get-started

Now,Installing coco-annotator using docker:

    git clone https://github.com/jsbroks/coco-annotator.git 

    cd coco-annotator 

    docker-compose up

    http://localhost:5000/

    Learn how to annotate: https://www.youtube.com/watch?v=OMJRcjnMMok&t=1s  


### Next step is to convert json format annotations into YOLO format. 

    Refernce for conversion:  https://github.com/WongKinYiu/yolov7/issues/1103
    

### Now, Dataset is ready. Clone this github repo: 

        git clone https://github.com/sam02425/YOLOv7-POSE-on-Custom-Dataset

        cd YOLOv7-POSE-on-Custom-Dataset

        pip install -r requirements.txt
        
        Place your dataset folder in this repo.
        
### Make all the changes which are mentioned in this video: https://youtu.be/OP-oiDsEVzc
        
For Training: 

      python train.py --data data/data.yaml --cfg cfg/yolov7-w6-pose_custom.yaml --hyp data/hyp.pose.yaml --device 0 --kpt-label --epochs 60
            
For Keypoint Detection: 

     python detect.py --weights runs/train/exp3/weights/best.pt --kpt-label --source 1.jpg --conf 0.030 --iou 0.30



Reference: 

        https://github.com/WongKinYiu/yolov7/tree/pose
        https://github.com/ruiz-manuel/yolov7-pose-custom   
        https://github.com/AarohiSingla/YOLOv7-POSE-on-Custom-Dataset
