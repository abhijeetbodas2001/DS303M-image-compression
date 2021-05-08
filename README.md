# Image_Compression

This repository contains various approaches for *Image Compression* 

Image compression is a type of data compression applied to digital images, to reduce their cost for storage or transmission. Algorithms may take advantage of visual perception and the statistical properties of image data to provide superior results compared with generic data compression methods which are used for other digital data. We will focus on lossy image compression

We Implemented 3 different techniques:

1. K-means
2. PCA
3. Deep Learning 

The .ipynb for K-means and PCA are in the respective folder

The DL folder includes various codes required for the Deep Learning Model. The weight can be downloaded from [link](https://drive.google.com/file/d/1YniZmdgYN4Lf0ZaERlD_CCn33w_ybF0G/view?usp=sharing) 

`compress.py` will compress generic images using some specified model. This performs a forward pass through the model to yield the quantized latent representation, which is losslessly compressed using a vectorized ANS entropy coder and saved to disk in binary format. As the model architecture is fully convolutional, this will work with images of arbitrary size/resolution (subject to memory constraints).

```
python3 compress.py -i path/to/image/dir -ckpt path/to/trained/model --reconstruct
```
