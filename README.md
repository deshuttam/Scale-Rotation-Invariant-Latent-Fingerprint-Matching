# Automatic latent fingerprint identification system using scale and rotation invariant minutiae features



By Uttam U. Deshpande et al.,

To solve the problems of low minutiae features in the latent fingerprint regions, we generate minutiae invariants to uniqely identify the fingerprint. To address this, we propose two algorithms based on the minutiae neighborhood. To solve the geometrical constraints between the pairs of nearest points around a minutia, we propose the latent minutiae similarity (LMS) algorithm. Based on geometrical arrangements on the set of latent minutiae patterns around a minutia, we propose a clustered latent minutiae pattern (CLMP) algorithm.
* To understand the implementation details, refer to the following paper, [Scale/Rotation Invariant Latent Fingerprint Matching](https://doi.org/10.1007/s42979-021-00615-7)


## Introduction
LMS and CLMP algorithm use local minutiae neighborhoods arrangements and are invariant to minutiae deformations, rotations, and scale. This method eliminates the need for singular point detection which is required to align fingerprints. The feature vectors for the gallery fingerprints and query fingerprints are obtained after extracting minutiae features. Feature vectors of query fingerprints are compared with feature vectors of gallery fingerprints to perform matching. 

## Latent fingerprint minutiae feature extraction
We use NIST’s open-source minutiae detection software FpMV minutiae viewer to extract minutiae features. The software performs minutiae detection based on the MINDTCT application. The block diagrams shown in Figs. 2 and 3 describe the steps followed to extract minutiae features from FVC2004 and NIST SD27 databases respectively.
Query image from FVC2004 is sent to the FpMV tool for minutiae extraction. The obtained minutiae are stored as x, y coordinates and further sent for matching. 

![image](https://user-images.githubusercontent.com/107185323/197676125-29e0a2fc-01fb-4b82-843b-5abac30635a0.png)

Similarly, a query image from NIST SD27 is pre-processed [12] and filtered to obtain the skeleton images. The skeleton image is further enhanced before extracting features using Gabor filters. Later, it is sent for matching. 

![image](https://user-images.githubusercontent.com/107185323/197676160-006ebfa3-6399-462b-a472-4df7d81789f0.png)

### Latent minutiae similarity (LMS) algorithm
A fixed-length distictive latent minutia descriptor is obtained from three minutiae neighbors.
![image](https://user-images.githubusercontent.com/107185323/197677197-5a910c84-4a64-4bc4-9b4e-25d72c4481fd.png)

### Clustered latent minutiae pattern (CLMP) algorithm
CLMP utilizes a fixed-length latent minutia descriptor based on its minutiae neighborhood similar to the LMS algorithm. This algorithm utilizes five minutiae points around a reference minutia to determine the fingerprint similarity. 
![image](https://user-images.githubusercontent.com/107185323/197677435-210ea71b-6f02-48b3-8eca-5dc5dceb744c.png)

### Fingerprint Hash-Table and Matching
Hash index is calculated using the ‘HTindex’ formula. Here, MAV is the one-dimensional minutiae arrangement vector of length mC4, ‘k ‘is the quantization level used to discretize the IAvg values, and ‘HTsize’ is the size of the hash table. The hash value is used to identify the query fingerprint and matching results are obtained.
![image](https://user-images.githubusercontent.com/107185323/197678143-df35567c-90ec-4e04-83b0-ac699ae908f1.png)


The repository includes:

* Source code for Fingerprint Preprocessing and Feature Extraction.
* Matlab code.
* Source code for Latent minutiae representation, Fingerprint Hash-Table Construction and Matching.
* Visual Studio code, C, C++, Shell Script codes.

### Citing
@ARTICLE{ 10.1007/s41870-020-00508-7, AUTHOR={Deshpande, Uttam U. et al.,},
TITLE={Automatic latent fingerprint identification system using scale and rotation invariant minutiae features},
JOURNAL={International Journal of Information Technology},
VOLUME={14},
YEAR={2020},
URL={ https://doi.org/10.1007/s41870-020-00508-7 }, DOI={ 10.1007/s41870-020-00508-7 }, ISSN={2511-2112}, 
}

Requirements: Software
* FpMV minutiae viewer
* `Python 2.7 Tensorflow 1.7.0 Keras 2.1.6`
* Visual Studio

## Preprocessing and Feature Extraction
* For FVC 2004 dataset, we utilize NIST’s `FpMV Minutiae Viewer` software. x, y minutiae coordinates are obtained and minutiae image is constructed.
* For NIST SD27 dataset, we use our previously developed `MINU-EXTRACTNET` framework for preprocessing operation (Refer: https://github.com/deshuttam/MINU-EXTRACTNET).   For extracting the minutiae points we use `FpMV Minutiae Viewer` software. 

## Installation
* Download `FpMV Minutiae Viewer` using this link [FpMV Minutiae Viewer](https://www.nist.gov/services-resources/software/fingerprint-minutiae-viewer-fpmv) . Run `FpMV.exe` from bin folder.
* Download `MINU-EXTRACTNET` framework from the link [MINU-EXTRACTNET](https://github.com/deshuttam/MINU-EXTRACTNET) .

Download models and put into Models folder.
* MINU-EXTRACTNET: [Googledrive](https://drive.google.com/file/d/1e-fvLhwvw8Sg1uVkM6oBT6QncWZgloap/view?usp=sharing)
* CoarseNet: [Googledrive](https://drive.google.com/file/d/1bU3T-XQRlKy6C77e5eD-DOD_QlNlAIjR/view?usp=sharing)
* FineNet: [Googledrive](https://drive.google.com/file/d/1rQw6hs-3hv_7WqJQ8ZYhJhi4laa-9qbY/view?usp=sharing)
