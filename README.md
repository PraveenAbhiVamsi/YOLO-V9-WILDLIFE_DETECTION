YOLO-V9 for Animal Life Detection
This repository contains a Jupyter Notebook that demonstrates how to use the YOLO-V9 (You Only Look Once, Version 9) model for detecting wildlife in images. The notebook includes steps to set up the environment, download necessary datasets and model weights, and perform inference and training using YOLO-V9.

Table of Contents
Before You Start
Clone and Install
Download Model Weights
Download Example Data
Detection with Pre-trained COCO Model
Authenticate and Download the Dataset
Training the Model
Inference
Before You Start
Ensure that you have access to a GPU for faster processing. You can verify GPU access using the nvidia-smi command. If needed, navigate to Edit -> Notebook settings -> Hardware accelerator, set it to GPU, and click Save.

python
Copy code
!nvidia-smi
Clone and Install
Clone the YOLO-V9 repository and install the necessary dependencies. Note that we are using a forked version of the repository due to a bug in the original.

python
Copy code
import os
HOME = os.getcwd()
print(HOME)

!git clone https://github.com/SkalskiP/yolov9.git
%cd yolov9
!pip install -r requirements.txt -q
!pip install -q roboflow
Download Model Weights
Download the pre-trained model weights required for YOLO-V9.

python
Copy code
!wget -P {HOME}/weights -q https://github.com/WongKinYiu/yolov9/releases/download/v0.1/yolov9-c.pt
!wget -P {HOME}/weights -q https://github.com/WongKinYiu/yolov9/releases/download/v0.1/yolov9-e.pt
!wget -P {HOME}/weights -q https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-c.pt
!wget -P {HOME}/weights -q https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-e.pt
Download Example Data
If you want to run inference using your own file as input, upload the image to the notebook and update the SOURCE_IMAGE_PATH variable with the path to your file.

Detection with Pre-trained COCO Model
By default, the results of each inference session are saved in {HOME}/yolov9/runs/detect/, in directories named exp, exp2, exp3, etc. You can override this behavior using the --name parameter.

Authenticate and Download the Dataset
Authenticate with Roboflow to download the dataset. Ensure the dataset is saved inside the {HOME}/yolov9 directory for successful training. The example uses the football-players-detection dataset.

python
Copy code
from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_API_KEY")
project = rf.workspace("roboflow-jvuqo").project("football-players-detection-3zvbc")
dataset = project.version(1).download("yolov9")
Training the Model
Instructions and commands for training the YOLO-V9 model on the downloaded dataset will be provided in the notebook.

Inference
Run inference using the trained model and visualize the results.

