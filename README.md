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
d1 is responsible for describing how different the contents of two images are.\
d2 is responsible for describing the difference between two images in terms of their style.\
Then, we take a content image and style image and transform content image by minimizing content and style distance with backpropagation\

### Why we use layers of Convolutional network?
Intermediate Layers within pretrained image classifcation network are useful.\
<b> Why? </b> In order for network to perform image classification, it needs to understand the image. The process of understanding the image involves taking raw images as input pixels and building internal representation through transformations of features present within the image.\
We will choose VGG19 pretrained model's layers for this style transfer task since VGG19 is a relative simpler model compared with ResNet, Inception and etc.\
The feature maps works better than for style transfer as the paper suggested.\
Specifically, to reconstruct the style of the input image, we'll pull out <b> conv1-1, conv2-1, conv3-1, conv4-1, and conv5-1</b> from vgg19 model.\

### Loss function
#### Content loss
The definition of content loss is the euclidean distance between desired content image and base input image.\
where x is input image and p is content image\
Let Fˡᵢⱼ(x) and Pˡᵢⱼ(x) describes the intermediate feature at layer l.\
![image](https://user-images.githubusercontent.com/84426364/148332111-40e5c835-9800-442c-928e-38a8f071511d.png)\
Next, we take the partial derivative respect to activations in layer l to minimize content loss.\
![image](https://user-images.githubusercontent.com/84426364/148332415-c4a82e08-ce40-467e-8194-8d31432ef693.png)\

#### Style loss
To compute Style loss, we describe the style loss of the input image,x, and the style image, a, as the distance between the style representation(Gram matrices) of these images.

Gram Matrices is an inner product between vectorized feature map.
![image](https://user-images.githubusercontent.com/84426364/148335206-de2d48b3-1573-45b0-a14a-de1f2f0abbb6.png)\

Hence,  the contribution of each layer to the total style loss is..\
![image](https://user-images.githubusercontent.com/84426364/148347925-338a4761-18a4-4dd4-b69b-2e541fca03b9.png)
where G and A are respective style representation(Gram matrices) of input image,x, and the style image, a.\
N describes number of feature maps and M is height * width.

<br> Finally, the total style loss across each layer is </br>
![image](https://user-images.githubusercontent.com/84426364/148353754-b3fb50fa-f930-43c6-8e3a-6600d8867c5e.png)

we weight the contribution of each layer's loss by some factor wl.\
![image](https://user-images.githubusercontent.com/84426364/148617246-876f5902-0944-4d61-ad52-ca4fc054a8f4.png)


#### Total loss
![image](https://user-images.githubusercontent.com/84426364/148354026-db789881-5f1c-4bba-9846-621c4380d8f8.png)
where alpha and beta are weighting factors.\
For this notebook, alpha = 1, style_weight = 1e3





























## Actknowledgement
Credit to https://www.linkedin.com/in/soumya044/ for his public notebook on Kaggle\
author for the Neural Style Transfer paper, https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf \
Medium Post, https://medium.com/tensorflow/neural-style-transfer-creating-art-with-deep-learning-using-tf-keras-and-eager-execution-7d541ac31398
