# Skin Disease Classification

 This model classifies skin conditions from images. It aims to differentiate between:
-Acne
-Benign Tumors
-Eczema
-Infestations and bites
-Moles
-Skin cancer
-Sun damage
-Warts
And clear skin. This model can be helpful to people who are curious about what is on their skin. It can help people detect the early stages of skin cancer, which is best treated as early as possible. It also deals with less serious conditions like acne and eczema so people can figure out what kind of medications would best help treat it.

## The Algorithm

The ResNet-18 model was created using Jetson Nano and was trained on a dataset of skin conditions. It runs on a imagenet.py program.

## Running this project

Install Python3 and the Jetson Inference Library on the Nano beforehand. Download resnet18.onnx and model_best.pth.tar. 
Download the resnet18.onnx and model_best.pth.tar. 
resnet18.onnx - (https://drive.google.com/file/d/14lsZiDZLUtoeu9hASyWPzN8mf32Ivmvd/view?usp=sharing)

model_best.pth.tar - (https://drive.google.com/file/d/1z7sbuV0in_uVGoX4jZQJyxKnzwsM3g9R/view?usp=sharing)

Download the data folder of images here: (https://drive.google.com/drive/folders/1L6r-kaU-LQEejztZtTQkJZ-iJnsnTZMj?usp=sharing)

Open the terminal and navigate to the classification directory:
   `$ cd jetson-inference/python/training/classification`
   
Set the net and data variables as shown below:

   `$ NET=models/DiseaseModel`
   
   `$ DATASET=data/SkinDisease`
   
Use this command to process an image:
   imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt data/SkinDisease// (put test or train or val here) / (type) / (picture you want to check) (what you want it to be named).jpeg
ex: 

imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt data/SkinDisease//test/Unknown_Normal/0_0_anhu_0216.jpeg normal.jpeg

https://drive.google.com/file/d/1ZgRLV8yPxs6DLWi0-xYtOhdTVPOGEEEY/view?usp=sharing

If you want to add your own image, add it do a directory under the test directory and use the command above, replacing the names with the directories and the name of your image.

Then look at the image output for a classification and confidence percentage in the corner.

[View a video explanation here](https://drive.google.com/file/d/1ZgRLV8yPxs6DLWi0-xYtOhdTVPOGEEEY/view?usp=sharing)



The Algorithm
The ResNet-18 model was created using Jetson Nano and was trained on a dataset of skin conditions. It runs on a imagenet.py program.

Running This Project
Install Python3 and the Jetson Inference Library on the Nano beforehand. Download resnet18.onnx and model_best.pth.tar. 
Download the resnet18.onnx and model_best.pth.tar. [Download the data folder of images here] (https://drive.google.com/drive/folders/1L6r-kaU-LQEejztZtTQkJZ-iJnsnTZMj?usp=sharing)

Open the terminal and navigate to the classification directory:
   $ cd jetson-inference/python/training/classification
Set the net and data variables as shown below:
   $ NET=models/DiseaseModel
   $ DATASET=data/SkinDisease
Use this command to process an image:
   imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt data/SkinDisease// (put test or train or val here) / (type) / (picture you want to check) (what you want it to be named).jpeg
ex: 

imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt data/SkinDisease//test/Unknown_Normal/0_0_anhu_0216.jpeg normal.jpeg

https://drive.google.com/file/d/1ZgRLV8yPxs6DLWi0-xYtOhdTVPOGEEEY/view?usp=sharing

If you want to add your own image, add it do a directory under the test directory and use the command above, replacing the names with the directories and the name of your image.

Then look at the image output for a classification and confidence percentage in the corner.
