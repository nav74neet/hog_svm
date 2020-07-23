# Histogram Of Oriented Gradients (HOG) for Face morphing detection
HOG method is one of the famous techniques for object recognition and edge detection. This method has been proposed by N. Dalal and B. Triggs in their research paper - "Histograms of Oriented Gradients for Human Detection, CVPR, 2005". 

## Getting Started - Feature Extraction Using HOG
The parameters used to compute the HoG are as per the de-fault detector used by N. Dalal and B. Triggs in "Histograms of Oriented Gradients for Human Detection, CVPR, 2005", as these give optimal performance.The image size used is 240*240 pixels and is divided into 8* 8 cells and a histogram is computed for each cell. A binsize of 9 is used for the orientation as it is proven to improveperformance significantly, hence each histogram results ina 9 * 1 vector. Block normalization is done by dividing theimage into blocks of 16 * 16 each of which contains four 8 * 8pixel cells so each 16 * 16 block contains 4 histograms, whichgives a 36 * 1 vector for each block. As cell size is 8, hence240/8 - 1 gives the number of blocks for each axis. The totalnumber of blocks is 29 * 29. Hence the size of one featurevector is 29 * 29 * 3 which is a vector of size 30276 * 1.


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

### Training

#### Dataset preparation:

First run the code - 'prepare_data.py'; for this, create the data as needed in the folder - 'raw_train_data', in current folder. The main 'raw_data_folder', must contain sub-folders of classes (say "Real Images" or "Morphed Images"). The data for training will be saved in the 'new_train_data'

Note: The default paths can be changed in the beginning of each code.

#### For training data :
```
train.py train
```
When prompted for Linear SVM MulitClass classification : enter 'SVM'

### Classification
For classifying based on folder names in the 'new_train_data' :
```
train.py classify
```
Note: When prompted for Linear SVM MulitClass classification : enter 'SVM'
