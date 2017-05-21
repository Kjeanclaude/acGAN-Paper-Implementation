=================================

## acGAN PAPER IMPLEMENTATION (from the FAST AI courses, Part2)

Here is our implementation of the acGAN Paper. 

[Gidi Shperber](https://github.com/shgidi) and [Me](https://github.com/Kjeanclaude) are ***International Fellows*** from the [Group 8](https://docs.google.com/spreadsheets/d/1KDk38DUlYpMxnZY8HW6e0NzZz9Tp1ngXCx-wpjWYnjI/edit#gid=311141924) of the [FAST AI courses, Part2](http://www.fast.ai/).

This course encourages team works, as one of their requirements is to do ***at least one project in a team***. One more valuable particularity of this course is that **Professor Jeremy** shows to its students hints on ***how to convert research papers into projects***.

The original paper we used is listed below :

-	**Face Aging With Conditional Generative Adversarial Networks** | Grigory Antipov, Moez Baccouche, Jean-Luc Dugelay : [Available here](http://arxiv.org/abs/1702.01983)

We plan to implement it with respect to some modifications as our contribution.

**OBJECTIVE :** With this job, our goal is to do some experimentations using GANs (Generative Adversarial Networks). Perhaps this job could be done using other networks such as CNN, but we would like to work on GANs. And there are several types of GANs : **Vanilla GAN, Conditional GAN, InfoGAN, Wasserstein GAN, Mode Regularized GAN, Coupled GAN, Auxiliary Classifier GAN, Least Squares GAN, Boundary Seeking GAN, Energy Based GAN, f-GAN, Context-Conditional GAN(CC-GAN), Semi-Supervised Learning GAN(SSL-GAN), etc.**
We should use here at least Conditional GAN.

=================================
## GANs ARCHITECTURES

![alt tag](https://github.com/Kjeanclaude/Fast-AI-Courses/blob/master/Part-2/acGAN%20Paper%20Implementation/Comparison-of-different-GAN-variant.jpg)
![alt tag](https://github.com/Kjeanclaude/Fast-AI-Courses/blob/master/Part-2/acGAN%20Paper%20Implementation/Stack-EB-gan2.png)

=================================

## THE PROCEDURES

The acGAN model proposed in the [acGAN Paper](http://arxiv.org/abs/1702.01983) uses :

1- The same design for the generator G and the discriminator D as in [[15]](https://arxiv.org/abs/1511.06434). 

2- Following [[12]](https://arxiv.org/abs/1611.06355), we inject the conditional information at the input of G and at the first convolutional layer of D. (Code available at https://github.com/Guim3/IcGAN)

3- acGAN is optimized using the ADAM algorithm [[16]](https://arxiv.org/abs/1412.6980) during **100 epochs** which ***takes about one day on a modern GPU*** (to be trained). 

4- In order to encode person’s age, we have defined six age categories: 0- 18, 19-29, 30-39, 40-49, 50-59 and 60+ years old. They have been selected so that the training dataset (cf. Subsection 3.1) contains at least 5, 000 examples in each age category. 
Thus, the conditions of acGAN are six-dimensional one-hot vectors.

5- Our acGAN has been trained on the IMDB-Wiki cleaned dataset [[20]](http://www.eurecom.fr/en/publication/4908/download/sec-publi-4908.pdf)

6- 


=================================

## OUR PERSPECTIVES

- We should introduce **two conditions (age and gender) on the WGAN** 

- We should use the [Age and Gender Classification Dataset](http://www.openu.ac.il/home/hassner/Adience/data.html) of the [***Open University of Israel***](http://www.openu.ac.il/en/pages/default.aspx) (Face Image Project), instead of the ***private IMDB-Wiki cleaned Dataset*** of the paper.

- We should follow the procedures above, extracted from the [acGAN Paper](http://arxiv.org/abs/1702.01983) and bring our innovation where needed (the conditions, the dimensions of the one-hot vectors, etc.).


=================================

## OUR CHALLENGES

- 1- **Extract the Age and Gender classes** from the `Age and Gender Classification Dataset` and make them available through suitable variables.
- 2- **Match the eight (08) age classes and two (02) gender classes** of the dataset **with the conditions placeholders** of our `agcGAN (Age-Gender Conditional Generative Adversarial Networks)`.
- 3- **Fine-tune**, optimize to produce the best results as possible.
- 4- **Reproduce the results in video-streaming** with accurate labels.
- 5- As professor Jeremy said: [there hasn't been any conditional WGANs yet](http://forums.fast.ai/t/conditional-gans/1951). So after the challenges above implemented, we could try to turn them into **conditional WGANs**, as a new contribution.

+++++++++++++++++++++++++++++++++

## SOME REFERENCES
-	**Age and gender classification using convolutional neural networks** (The research paper) | Gil Levi, Tal Hassner
[Available here](http://www.openu.ac.il/home/hassner/projects/cnn_agegender/CNN_AgeGenderEstimation.pdf)

-	**Age and gender Data Preparation Code in Python** | Gil Levi
[Available here](https://github.com/GilLevi/AgeGenderDeepLearning)

-	**Age and gender classification using convolutional neural networks Notebook Demo with a pre-trained Caffe Model** | Gil Levi, Tal Hassner
[Available here](http://nbviewer.jupyter.org/url/www.openu.ac.il/home/hassner/projects/cnn_agegender/cnn_age_gender_demo.ipynb)

-	**Age and gender ALL DOWNLOADS LINKS** | Gil Levi, Tal Hassner
[Available here](http://www.openu.ac.il/home/hassner/projects/cnn_agegender/)

-	**Conditional Generative Adversarial Nets (GAN) in TensorFlow** | Kristiadi Agustinus
[Available here](http://wiseodd.github.io/techblog/2016/12/24/conditional-gan-tensorflow/)

-	**Conditional Generative Adversarial Networks (GAN) in Pytorch** | Kristiadi Agustinus
[Available here](http://wiseodd.github.io/techblog/2017/01/20/gan-pytorch/)
