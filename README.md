# Automatic latent fingerprint identification system using scale and rotation invariant minutiae features



By Uttam U. Deshpande et al.,

To solve the problems of low minutiae features in the latent fingerprint regions, we generate minutiae invariants to uniqely identify the fingerprint. To address this, we propose two algorithms based on the minutiae neighborhood. To solve the geometrical constraints between the pairs of nearest points around a minutia, we propose the latent minutiae similarity (LMS) algorithm. Based on geometrical arrangements on the set of latent minutiae patterns around a minutia, we propose a clustered latent minutiae pattern (CLMP) algorithm.
* To understand the implementation details, refer to the following paper, https://doi.org/10.1007/s42979-021-00615-7 


## Introduction
LMS and CLMP algorithm use local minutiae neighborhoods arrangements and are invariant to minutiae deformations, rotations, and scale. This method eliminates the need for singular point detection which is required to align fingerprints. The feature vectors for the gallery fingerprints and query fingerprints are obtained after extracting minutiae features. Feature vectors of query fingerprints are compared with feature vectors of gallery fingerprints to perform matching. 

## Latent fingerprint minutiae feature extraction
We use NIST’s open-source minutiae detection software FpMV minutiae viewer to extract minutiae features. The software performs minutiae detection based on the MINDTCT application. The block diagrams shown in Figs. 2 and 3 describe the steps followed to extract minutiae features from FVC2004 and NIST SD27 databases respectively.
Query image from FVC2004 is sent to the FpMV tool for minutiae extraction. The obtained minutiae are stored as x, y coordinates and further sent for matching. 

![image](https://user-images.githubusercontent.com/107185323/197676125-29e0a2fc-01fb-4b82-843b-5abac30635a0.png)

Similarly, a query image from NIST SD27 is pre-processed [12] and filtered to obtain the skeleton images. The skeleton image is further enhanced before extracting features using Gabor filters. Later, it is sent for matching. 

![image](https://user-images.githubusercontent.com/107185323/197676160-006ebfa3-6399-462b-a472-4df7d81789f0.png)
