# Kaggle-Global-Wheat-Detection
In this project, a competition problem on Kaggle has been worked out. Yolo version 5 is used here to detect the wheat heads.


# Competition Link
https://www.kaggle.com/c/global-wheat-detection


# Data
This project is built on google colab. Follow these steps to get the data availble on the colab notebook.
- Download the kaggle.json file form you kaggle account setting.
- Use the following code snippets for uploading and saving the kaggle.json file on colab
<pre>
    <code>
        from google.colab import files
        files.upload() #upload kaggle.json file here
        ! mkdir ~/.kaggle
        ! cp kaggle.json ~/.kaggle/
        !chmod 600 ~/.kaggle/kaggle.json
        !kaggle datasets list
    </code>
  </pre>
- Use the following command to download and unzip the data.
  <pre>
    <code>
        !kaggle competitions download -c global-wheat-detection
        !unzip global-wheat-detection.zip -d wheat_detection
    </code>
  </pre>
      
 To get the yolov5 model clone the ultralytics repository using following command.
 <pre>
  <code>
    !git clone  https://github.com/ultralytics/yolov5
  </code>
</pre>


# Files and Directories
Use to following command to create some directories
<pre>
  <code>
     !mkdir wheat_data
     !mkdir /content/wheat_data/images
     !mkdir /content/wheat_data/labels
     !mkdir /content/wheat_data/labels/train
     !mkdir /content/wheat_data/labels/validation
     !mkdir /content/wheat_data/images/train
     !mkdir /content/wheat_data/images/validation
  </code>
</pre>

Create a .yaml file with data paths and classes and save it in /content

Lastly, run the following to start model training
<pre>
  <code>
    !python3 /content/yolov5/train.py --img 1024 --batch n --epochs n1 --data /content/wheat.yaml --cfg /content/yolov5/models/yolov5s.yaml --name wheat_detector_model
  </code>
</pre>


# Result:
![alt text](https://github.com/Dilpreet047/Kaggle-problems/blob/master/download%20(1).png)
