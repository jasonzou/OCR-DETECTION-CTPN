# OCR-DETECTION-CTPN
  
  
CNN+LSTM (CTPN) for image text detection

  
### example results
  
![detect_test_results](https://github.com/Li-Ming-Fan/OCR-DETECTION-CTPN/blob/master/detect_test_result/5000_bkgd_1_0_generated_0.png?raw=true)
  
### Installation

#### install minicoda python 3.6 - x64 on Linux
```bash
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod +x Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
```

#### Install Anaconda python 3.6 - x64 on Linux
```bash
wget https://repo.continuum.io/archive/Anaconda3-5.1.0-Linux-x86_64.sh
chmod +x Anaconda3-5.1.0-Linux-x86_64.sh
./Anaconda3-5.1.0-Linux-x86_64.sh
```
#### Create a conda env
```bash
conda create -n ocr python=2.7 pip PIL scipy numpy jupyter
conda update conda
pip update pip

```
  
### description
  
To run this repo:
  
1, python data_base_normalize.py    &nbsp; &nbsp; &nbsp;   # to normalize the pre-normalized background images
  
2, python data_generator.py 0    &nbsp; &nbsp; &nbsp;  # to generate validation data
  
3, python data_generator.py 1     &nbsp; &nbsp; &nbsp;  # to generate training data
  
4, python script_detect.py    &nbsp; &nbsp; &nbsp;  # to train and validate
 
</br>
  
By 1, the pre-normalized images will firstly be rescaled if not of size 800x600, then 800x600 rects will be cropped from the rescaled images. The 800x600 images will be stored in a newly-maked directory, images_base/.
  
By 2 and 3, validation data and training data will be generated. These will be store in the newly-maked directories, data_test/ and data_generated/, respectively.
  
By 4, the model will be trained and validated. The validation results will be stored in data_test/results/. The ckpt files will be stored in a newly-maked directory, model_detect/.



### detection model
  
The model is mainly based on the method described in the article:
  
Detecting Text in Natural Image with Connectionist Text Proposal Network
  
Zhi Tian, Weilin Huang, Tong He, Pan He, Yu Qiao
  
https://arxiv.org/abs/1609.03605




