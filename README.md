# Histogram Of Oriented Gradients (HOG) for Face morphing detection
HOG method is one of the famous techniques for object recognition and edge detection. This method has been proposed by N. Dalal and B. Triggs in their research paper - "Histograms of Oriented Gradients for Human Detection, CVPR, 2005". 

## Getting Started - Feature Extraction Using HOG
The HOG descriptor's code uploaded here, is for classification of car logos.
Hog descriptor uses edge detection by gradient calculation and histograms of gradients, with magnitudes as weights.
The code uses [-1 0 -1] kernel for gradient magnitude and orientation calculation. Gradients are calculated in the range [0,180]. Histograms of 8 bins are calculated with magnitudes as weights. Each image is checked if its of 32X32 size, else its resized. The code reads images in greyscale.
The images are normalised for gamma, and then, for normal contrast. Each 32X32 image pixel matrix, is organised into 8X8 cells and then, histograms are calculated for each cell. Then, a 4X4 matrix with 8 bins in each cell is obtained. This matrix is organised as 2X2 blocks(with 50% overlap) and normalised, by dividing with the magnitude of histogram bins' vector. A total of 9 blocks X 4 cells X 8 bins  = 288 features


### Requirements
1) Python 3.5 : https://www.python.org/downloads/release/python-353/
2) Tensorflow : https://www.tensorflow.org/install/
3) Pillow : https://pillow.readthedocs.io/en/4.2.x/installation.html#basic-installation
4) Numpy : https://docs.scipy.org/doc/numpy-1.10.1/user/install.html
5) matplotlib : https://matplotlib.org/faq/installing_faq.html

## Browsing the folder
The folder contains a zip file called logos.zip, which contains the data set for training the HOG-SVM. This can be downloaded and extracted to the folder 'new_train_data' (make folder if not present...)

Use the code 'prepare_data.py' to prepare data (if data from logos.zip is not being used)
Use the code 'hog.py' to extract hog features.
Use the code 'train.py' to train Linear SVM.

### hog.py
Contains the required functions for extracting histograms from images after pre-processing. Run the following code:

```
hog.py
```

### train.py


Dataset preparation:

First run the code - 'prepare_data.py'; for this, create the data as needed in the folder - 'raw_train_data', in current folder. The main 'raw_data_folder', must contain sub-folders of classes (say "Real Images" or "Morphed Images"). The data for training will be saved in the 'new_train_data'

Note: The default paths can be changed in the beginning of each code.

Run the train.py code as follows:

1) For training data :
```
train.py train
```
When prompted for Linear SVM MulitClass classification : enter 'SVM'

2) For classifying based on folder names in the 'new_train_data' :
```
train.py classify
```
Note: When prompted for Linear SVM MulitClass classification : enter 'SVM'
