# Object Detection with the RaspberryPi
 This project is a continuation of my Security Camera github repo. I decided to use tensorflow's object detection api instead of Nanonets because Nanonets was slow so I couldn't get the livestream working.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Siddharth M | American Highschool | CS/AI | Incoming Freshman

# Second Milestone

For my second milestone, I made a second model that can determine if the face detected by the object detection model is me, or not. I used tensorflow's Sequential model to do this. The sequential model is a stack of linear layers. It's one of the simplest models that keras has, you can add different types of layers such as Convolutional Layers, MaxPooling Layers, Dense Layers, etc. Each layer has exactly 1 input and 1 output. I used transfer learning and used VGG16's architecure to train my model. VGG16 is a CNN architecture used to win the ILSVR competitoin in 2014. To get my dataset, I made a python script that takes 50 pictures of me. Then I used augmentation to generate even more images. 

![image](https://user-images.githubusercontent.com/56204136/128520933-c1e76610-6475-4fd8-9b80-c5cd0373da74.png)

  
# First Milestone

My first milestone was training a custom object detection mdoel using tensorflow's model garden. The model garden is a github repository created by tensorflow that has many different implementations for models and also modeling solutions. (https://github.com/tensorflow/models). To train my model I needed the model files which I can download at tensorflow's model zoo, the `tfrecord` file which contains dataset info, and a `label_map.pbtxt` file that contains the list of classes that I want my model to detect. The `pipeline.config` file allows me to configure the model and also set the path for the tfrecord and label map files. After I have this all setup, then I can run the `model_main_tf2.py` that comes in the model garden. This starts the training process and can take a while depending on your computer and the parameters in the pipeline.config file. 

![ssdMobilenetDiagram](https://user-images.githubusercontent.com/56204136/127869484-b90c7414-56ed-4a34-bf7c-f18747c7661f.png)

This diagram is a representation of how one of the models I am using (SSD MobileNet V2 FPNLite 640x640) works. Object detection is broken into two steps, object localization and image classification. Object localization is when you are trying to find objects inside an image. Image classification is when you are trying to find out what the image is, for example a dog or a cat. Object Detection uses both of these techniques to get a result. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/1QDDMfq4srM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

