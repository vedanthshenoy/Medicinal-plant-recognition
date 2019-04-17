# Medicinal-plant-recognition
This is a Support vector classifier model which can classify medicinal plants from non-medicinal plants and also obtain which species the medicinal plant belongs to.

Pull requests are encouraged always. Feel free to contact me on vedantshenoy1@gmail.com for any doubts and queries.

## Dependencies

- [sci-kit learn]()
- [Numpy]()
- [OpenCV]()
- [os]()
- [time]()
- [mahotas]()

## Installation Guide

- Installing Sci-kit learn for Python
```
pip install scikit-learn
```
- Installing Numpy for Python
```
pip install numpy
```
- Installing OpenCV for Python
```
pip install opencv-python
```
- Installing mahotas for Python
```
pip install mahotas
```
- Installing Sci-kit learn for Anaconda
```
conda install scikit-learn
```
- Installing OpenCV learn for Anaconda
```
conda install -c conda-forge opencv 
```
- Installing mahotas learn for Anaconda
```
conda install -c conda-forge mahotas 
```

- Numpy and Pandas come preinstalled in Anaconda package.


## Language/Fraework Used

- [Jupyter Notebook](https://jupyter.org/)

## Preprocessing 

Firstly, the main thing to be done whiile begining a image based classification task is to preprocess the images in such a way it becomes easy for computation.

When you get an image make sure it has a single channel(grayscale image) because working on single channel image is easier for computation since a coloured image will have three channels. 
Eventhough we are reducing the image down to single channel from three channels it is interesting to note that, the information we want to classify the image into it's species is not lost in the process.

Once we have a grayscale image next thing is to extract features from the image.

Here, i used the texture information in the leaf images since alone using the texture information resulted in a 91.7% accuracy which was very much desirable for experimental and/or research purposes.

Texture defines the consistency of patterns and colors in an object/image such as bricks, school uniforms, sand, rocks, grass etc. To classify objects in an image based on texture, we have to look for the consistent spread of patterns and colors in the object’s surface. Rough-Smooth, Hard-Soft, Fine-Coarse are some of the texture pairs one could think of, although there are many such pairs.

I used Haralick features to obtain the texture feature information from the preprocessed image. Haralick feature is a image processing technioque used to extract texture based information. If you want to know more about Haralick features click [here](http://shodhganga.inflibnet.ac.in/bitstream/10603/20682/14/14_chapter%205.pdf).

## SVC

Support Vector Machines are machine learning algorithms used as both classifier and regression algorithm. Here since classifying whether a patient has heart disease or not is a classification problem so we will be using Support Vector Classifier.

The basic purpose of a SVC is to split the target datapoints using a hyperplane. Having said that once the hyperplane is drawn then the datapoints are not important while classifying an unknown datapoint. This is achieved by drawing the hyperplane equidistant from the most closest datapoint on either side...well that's a mouthfull ;p

All it means is described in the image below.

![Support Vector Classifier](1-19SVM-2.jpg)

Here linear kernel is used. Linear kernel can be used when we have data which can be represented in a plane. Often we encounter data which are cannot be expressed in a plane, but the problem with SVM(or here SVC) is that it works only with linearly seperable data so we have to make the datapoints linearly seperable somehow, there we use different kernels. As shown in the below image.

[Making data linearly seperable by changing dimension](svmkernel.png)

[Seperating the transformed data using linear plane](svm_3d.png)

## Using sklearn in-built feature extractor

Since we were getting little overfitting issues with our dataset while using haralick features, i tried to use sklearn in-built feature extractor for images and see whether there is any change in the performance.

## References
- https://gogul09.github.io/software/texture-recognition
- http://shodhganga.inflibnet.ac.in/bitstream/10603/20682/14/14_chapter%205.pdf

## Image credits

- https://medium.com/@zachary.bedell/support-vector-machines-explained-73f4ec363f13
- https://quantdare.com/svm-versus-a-monkey/
