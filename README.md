# BostonImageStyleTransfer

# Table of Contents  
1. [About](#About)
2. [Example2](#example2)





## About
This project uses pictures I took at Boston area and perform neural style transfer on them to create artwork.\
![image](https://user-images.githubusercontent.com/84426364/148294570-957a2aec-ca12-4519-a33c-1e6ba294973e.png)
![image](https://user-images.githubusercontent.com/84426364/148294594-86d53fcf-930f-4c56-857c-ba0dbfaf4f8d.png)


The essential idea of neural style transfer is to define two distance function named d1 and d2\
d1 is responsible for describing how different the contenets of two images are.\
d2 is responsible for describing the difference between two images in terms of their style.\
Then, we take a content image and style image and transform content image by minimizing content and style distance with backpropagation










[Actknowledgement](#actknowledgement)
<a id="Actknowledgement"></a>
## Credit to https://www.linkedin.com/in/soumya044/ for his public notebook on Kaggle
and author https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf

https://medium.com/tensorflow/neural-style-transfer-creating-art-with-deep-learning-using-tf-keras-and-eager-execution-7d541ac31398
