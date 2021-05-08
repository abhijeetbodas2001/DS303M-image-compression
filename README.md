# Image_Compression

This repository contains various approaches for *Image Compression* 

Image compression is a type of data compression applied to digital images, to reduce their cost for storage or transmission. Algorithms may take advantage of visual perception and the statistical properties of image data to provide superior results compared with generic data compression methods which are used for other digital data. We will focus on lossy image compression

We Implemented 3 different techniques:

1. K-means
2. PCA
3. Deep Learning 

The .ipynb for K-means and PCA are in the respective folder

The DL folder includes various codes required for the Deep Learning Model. The weights for the model can be downloaded from [link](https://drive.google.com/file/d/1YniZmdgYN4Lf0ZaERlD_CCn33w_ybF0G/view?usp=sharing) 

`compress.py` will compress generic images using some specified model. This performs a forward pass through the model to yield the quantized latent representation, which is losslessly compressed using a vectorized ANS entropy coder and saved to disk in binary format. As the model architecture is fully convolutional, this will work with images of arbitrary size/resolution (subject to memory constraints).

```
python3 compress.py -i path/to/image/dir -ckpt path/to/trained/model --reconstruct
```

# Examples

Results for an input image:

![image](https://user-images.githubusercontent.com/62425457/117535228-68422f80-b012-11eb-9dbb-5995cf91002e.png)

1. K-means

Only 16 colours are present in the final image. It's PSNR value is 35.38

![image](https://user-images.githubusercontent.com/62425457/117535241-7c862c80-b012-11eb-9f18-3be96db672c3.png)

2. PCA

Only 150 prinicpal components are used. It's PSNR value is 36.65

![image](https://user-images.githubusercontent.com/62425457/117535309-d981e280-b012-11eb-917f-a6425c4abb6a.png)

3. Deep Leaening

The compressed size is just 12 KB and it gives a PSNR value of 34.26

![image](https://user-images.githubusercontent.com/62425457/117535371-164dd980-b013-11eb-8975-49bea4400d80.png)

The difference in the input image and Resultant image is subtle for Human eyes in Case of Deep Learning Methods. If observed closely around the bottom left part of image, the difference is visible.


