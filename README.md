# CatsnDogs_img_dataset

We have taken a subset of (manually chosen) images of different breeds of cats and dogs from the [Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/), made available under 
a  [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/), and manually created a raw dataset of images with a square aspect ratio. 
The images in the original dataset, as well as the square images in the folder Dataset_square have different pixel dimensions. We first downsize these images to uniform dimensions of 200x200 pixels using 
skimage (we haven't uploaded these intermediate set of images on to this repo). Thereafter we augment the dataset using rotations, translations (and flips), and further downsizing to obtain a dataset of square images with dimensions 160x160 pixels. The final images are saved 
in the folder Dataset_aug. data_process.ipynb is the jupyter notebook with the skimage transforms implemented on the images.  

The original raw dataset in the folder Dataset_square consists of 730 images while the final set in the folder Dataset_aug consists of 5110 images. This final dataset, although of better quality than the original dataset,
is probably not ideal to train a classifier as the augmentation procedure creates very similar images to the original so there are effectively (at least) 7 images of each pet which are only slightly different
from each other. We intend to use this dataset to train a generative model.
