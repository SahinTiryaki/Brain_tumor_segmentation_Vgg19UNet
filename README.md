# Brain-tumor-segmentation-Vgg19UNet
:grinning:	This project is my first segmentation project :smile:	
## Task :writing_hand:
&ensp;&ensp;&ensp;&ensp; The dataset contains brain MR images together with manual FLAIR abnormality segmentation masks. The dataset has included 110 patients. The dataset has included 2556 no brain tumor images and 1373 brain tumor images. The task assigned identified the location of the brain tumor in the pictures. The goal of **Semantic image segmentation:white_check_mark:** is to label each pixel of an image with a corresponding class of what is being represented. Because we’re predicting for every pixel in the image, this task is commonly referred to as dense prediction. Image segmentation has various applications in industry, but particularly in the medical industry the possiblities for automated diagnoses and cheaper medical imaging programs motivate researchers to invest in producing robust image segmentation models for human tissue.<br>
**Dataset :ledger:	:** https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation <br>
a few images with mask
![datas](https://user-images.githubusercontent.com/59391291/117510076-15c22e00-af94-11eb-9e62-8b4d03b24ef2.png)
<br>
count of mask <br>
![miktar](https://user-images.githubusercontent.com/59391291/117510083-1955b500-af94-11eb-80e1-429ef788032e.png)

## UNet
![1_f7YOaE4TWubwaFF7Z1fzNw](https://user-images.githubusercontent.com/59391291/117498684-cc1d1780-af82-11eb-8d6f-b41779562bb7.png) <br>

&ensp;&ensp;&ensp;&ensp; U-net was first used for biomedical image segmentation. Its architecture can be broadly thought of as an encoder network followed by a decoder network. Unlike classification where the end result of the the deep network is the only important thing, semantic segmentation not only requires discrimination at pixel level but also a mechanism to project the discriminative features learnt at different stages of the encoder onto the pixel space. The encoder is the first half in the architecture diagram. It usually is a pre-trained classification network like VGG/ResNet where you apply convolution blocks followed by a maxpool downsampling to encode the input image into feature representations at multiple different levels. The decoder is the second half of the architecture. The goal is to semantically project the discriminative features (lower resolution) learnt by the encoder onto the pixel space (higher resolution) to get a dense classification. The decoder consists of upsampling and concatenation followed by regular convolution operations.<br>
**If you want to know more about UNet , you can look this article** https://arxiv.org/pdf/1505.04597.pdf
<br>
You can look model architecture by model.py file. <br>
You can look project notebook by brain-tumor-segmentation-vgg19-unet.ipynb <br>
download this model ( seg_model.h5 ) and use <br>

### About Model
**Callbacks function for fitting:**  ReduceLROnPlateau ( Reduce learning rate when a metric has stopped improving ), <br> ModelCheckpoint ( save best weigts), EarlyStopping (Stop training when a monitored metric has stopped improving)<br><br>
**epochs:** 60 <br><br>
**loss functions:** Focal Tversky loss (https://arxiv.org/abs/1810.07842)<br><br>
**metric:**  Tversky ( https://arxiv.org/abs/1706.05721 )<br><br>


![loss](https://user-images.githubusercontent.com/59391291/117513611-c29fa980-af9a-11eb-869b-d672d7939939.png)<br><br>
### a few prediction images
![predictions](https://user-images.githubusercontent.com/59391291/117513706-fb3f8300-af9a-11eb-9faf-154a7dfc5052.png)


