# GNR638 Project - Object Detection (FCOS vs YOLO)

Hello and welcome to our GNR 638 Project. Our Project is based on Object Detection.

Here you can find the project video as well as the various other files of the project- [GNR638 Project Final Submission](https://drive.google.com/drive/folders/1p4EQtOoU8ptlZ6LvsIDQmVMPRzVtn6Dz?usp=sharing)


Our project has 2 main components.
1.	We implement the YOLO model and also train it on a custom dataset. The results are shown in the code and the PPT.
2.	We compare the performance of anchor based object detection models with anchor free object detection models. Comparing various factors is done in the PPT and the video demo.

All files required for our code to train YOLO are present at [Project Code Drive Folder](https://drive.google.com/drive/folders/1A5CaI-oRcHNPkUG6zYG_My0_IdepS4hI?usp=sharing).

Link to the colab file: [Project Code IPYNB Notebook](https://colab.research.google.com/drive/16bZqCfuObdcLJWptxBvbTMXXF7ku2bmH?usp=sharing)


Instructions to download and test YOLOv3 from source for making other observations:-
Start from the <predictions> folder in the terminal and follow the following steps commands-

1.	 Install the Darknet53 

```
git clone https://github.com/pjreddie/darknet
cd darknet
make
```

2.	 Installing the weights

```
wget https://pjreddie.com/media/files/yolov3.weights
```

3.	To predict on some image with name <image name>

```
./darknet detect cfg/yolov3.cfg yolov3.weights ../<image name>
```

The result is stored as predictions.jpg in  the darknet directory


Instructions to download and install FCOS from source:-

1.	Install detectron2 as follows

```  
git clone https://github.com/facebookresearch/detectron2.git
python -m pip install -e detectron2
```

2.	Then Install FCOS as follows-

```
git clone https://github.com/aim-uofa/AdelaiDet.git
cd AdelaiDet
python setup.py build develop
```

3.	Run the model with the following command-

```
python demo/demo.py  --config-file configs/FCOS-Detection/R_50_1x.yaml --input <image_name>.jpg --opts MODEL.WEIGHTS fcos_R_50_1x.pth
```

We were stuck several times due to clashing conda and pip environments on our system. If you encounter a similar problem, please create a new virtual environment and try to run the code there. There might be clashes between different versions of libraries and it’s better to run all this on a fresh machine / new virtual environment. The current installation method depicted above worked best for us.
