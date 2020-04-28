# Computer Aided Diagnostic System for Tuberculosis Identification and Segmentation from Chest X-rays:
Tuberculosis (TB) is a contagious disease designated as foremost source of death across the world. Although TB can be treated with high
change of cure, a large number of patients decrease for not getting timely and correct diagnosis, mainly due to insufficient radiography
and radiologists. If left misdiagnosed and untreated, every active TB (sputum positive) case can contaminate 10 to 15 individuals in a
single year. In 2016, about 10.4 million people infected with TB, resulted in 1.3 million deaths. Pakistan is 5th largest high-burden 
country in TB where about 510 million cases are reported yearly. Dealing with the TB challenge demands a diagnostic solution that is
inexpensive, fast, precise, and easy to implement in undeveloped TB dominant areas. Currently the high burden TB countries are mostly
relying on GeneXpertMTB-RIF (GXP) and sputum smear microscopy tests for TB diagnostics. Nevertheless, the expenses of a GXP test
and lower efficacy of the smear test have led the World Health Organization (WHO) to suggest the use of chest radiography or Chest X-Rays
CXRs for systematic diagnosis of TB. X-ray scans highlight irregularities in the lungs that can lead to diagnose TB. As digital X-ray
has low operational expenses and rapid outcomes, it makes TB diagnostic affordable and quick. However, the correct diagnosis of TB from
X-rays scans involves native expertise of radiology which is often defficient in TB occupied regions. Therefore, designing a CAD system for
screening TB can be very beneficial for early TB diagnosis and leads to deterrence of demises from TB. 

## Table of Contents
  + [Classification of Tuberculosis from Chest-X-rays](#classification-of-tuberculosis-from-chest-x-rays)
    + [Dataset Description and Preprocessing](#dataset-description-and-preprocessing)
    + [Classification using Transfer-Learning with Pretrained-VGG16](#classification-using-transfer-learning-with-pretrained-vgg16) 
      + Implementation
      + Statistical Results
      + Visualization
  + Segmentation (Pixel-level Detection)
    + Dataset Description ad Preprocessing
    + Segmentation with FCN-8 Architecture
    
### Classification of Tuberculosis from Chest-X-rays:

#### Dataset Description and Preprocessing:
These datasets contain de-identified chest X-Rays (CXRs) of normal and anomalous cases. The study is conducted on two datasets
including Shenzhen and Montgomery County (MC) and is publicaly available [Here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4256233/).
The Shenzhen dataset comprises of 662 CXRs where 326 are normal and 336 are anomalous (i.e. TB) CXRs. The dataset was collected from
People's Hospital, Guangdong Medical College, Shenzhen, China. The MC dataset consists of 138 CXRs including 80 normal and 58 anomalous
CXRs. Using 80:20 train/validation split I have split the total of 800 CXRs to 600 training set and 200 test/validation set. This splitted dataset can be downloaded at [Here](https://drive.google.com/drive/folders/1UTYz5Xn6Nfbn9yarqZo7SD5H37tW5PQ_?usp=sharing). I have also write a [script](https://github.com/zeeshannisar/Tuberculosis/blob/master/Classification/datasets/Read%20Images%20and%20Save%20to%20Numpy%20Files.ipynb) to further make the Numpy-Files for the data. These Numpy-Files can be downloaded at [Here](https://drive.google.com/drive/folders/1mzJYjQj42ulZUdfZ_vkWojGgU9Ywa72Q?usp=sharing). As the number of training instances are too less to train a good generalized model, That's why I have used some data-augmentation techniques with [ImageDataGenerator](https://www.tensorflow.org/api_docs/python/tf/keras/preprocessing/image/ImageDataGenerator).

#### Classification using Transfer-Learning with Pretrained-VGG16:
##### Implementation:
[Code:Google Colab Notebook]()
##### Statistical Results:
|![alt-text-1](https://github.com/zeeshannisar/Tuberculosis/blob/master/ReadMe%20Images/VGG16-cm.png "Confusion Matrix") | ![alt-text-2](https://github.com/zeeshannisar/Tuberculosis/blob/master/ReadMe%20Images/VGG16-roc.png "ROC Curve") |
|:---:|:---:|
| Confusion Matrix | Receiver Operating Characteristic (ROC) curve |
##### Visualization:
<p align="center">
    <img src="https://github.com/zeeshannisar/Tuberculosis/blob/master/ReadMe%20Images/heatmaps.png">
</p>


