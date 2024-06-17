# YOLO-V9 for Animal Life Detection

This repository contains a Jupyter Notebook that demonstrates how to use the YOLO-V9 (You Only Look Once, Version 9) model for detecting wildlife in images. The notebook includes steps to set up the environment, download necessary datasets and model weights, and perform inference and training using YOLO-V9.

Ensure that you have access to a GPU for faster processing. You can verify GPU access using the `nvidia-smi` command. If needed, navigate to `Edit` -> `Notebook settings` -> `Hardware accelerator`, set it to `GPU`, and click `Save`.


`!nvidia-smi`
Clone the YOLO-V9 repository and install the necessary dependencies. Note that we are using a forked version of the repository due to a bug in the original.
```python
import os
HOME = os.getcwd()
print(HOME)

!git clone https://github.com/SkalskiP/yolov9.git
%cd yolov9
!pip install -r requirements.txt -q
!pip install -q roboflow

