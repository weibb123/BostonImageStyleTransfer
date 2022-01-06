# BostonImageStyleTransfer

# Table of Contents  
1. [About](#About)
2. [Content](#Content)
3. [Actknowledgement](#Actknowledgement)





## About
This project uses pictures I took at Boston area and perform neural style transfer on them to create artwork.\
This picture is taken at Boston Seaport Fan Pier Park 
![image](https://user-images.githubusercontent.com/84426364/148294570-957a2aec-ca12-4519-a33c-1e6ba294973e.png)
![image](https://user-images.githubusercontent.com/84426364/148294594-86d53fcf-930f-4c56-857c-ba0dbfaf4f8d.png)

This picture is taken from my dorm window at Boston University
![image](https://user-images.githubusercontent.com/84426364/148294899-bb81b967-8dcc-443b-9f74-720c74ec150d.png)
![image](https://user-images.githubusercontent.com/84426364/148295007-3d508575-f702-4c28-9758-edb8ecb19fa8.png)

This picture is taken at Boston University bridge capturing the night view
![image](https://user-images.githubusercontent.com/84426364/148295485-c5bdc437-0885-4a23-95aa-6cd5f5991310.png)
![image](https://user-images.githubusercontent.com/84426364/148295503-a1469f7f-d62d-429f-b23c-acc4bd6ffec1.png)




## Content
The essential idea of neural style transfer is to define two distance function named d1 and d2\
d1 is responsible for describing how different the contenets of two images are.\
d2 is responsible for describing the difference between two images in terms of their style.\
Then, we take a content image and style image and transform content image by minimizing content and style distance with backpropagation\

### Why we use layers of Convolutional network?
Intermediate Layers within pretrained image classifcation network are useful.\
<b> Why? </b> In order for network to perform image classification, it needs to understand the image. The process of understanding the image involves taking raw images as input pixels and building internal representation through transformations of features present within the image.\
We will choose VGG19 pretrained model's layers for this style transfer task since VGG19 is a relative simpler model compared with ResNet, Inception and etc.\
The feature maps works better than for style transfer as the paper suggested.\











## Actknowledgement
Credit to https://www.linkedin.com/in/soumya044/ for his public notebook on Kaggle\
author for the Neural Style Transfer paper, https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf \
Medium Post, https://medium.com/tensorflow/neural-style-transfer-creating-art-with-deep-learning-using-tf-keras-and-eager-execution-7d541ac31398
