# Cell Nucleus Detection Images Segmentation with U-Net

## 1.Objective
The objective of this project is to identify the range of nuclei in biomedical images in order to automate the process of identifying the nuclei.It will improve the efficiency of drug testing and shorten the time for a new drug launch in the market.Since the nuclei had various of shape and size.Therefore, the semantic segmentation would be the best approach for this project.The nuclues dataset was provided in this [link](https://www.kaggle.com/competitions/data-science-bowl-2018/overview/description).

## 2.IDE and Framework
Jupyter is the main IDE in this project.Besides, the main framework such as Numpy,Matplotlib,Opencv2 and TensorFlow were implemented in this project.

## 3.Methodology 
Image segmentation methodology was inspired from this documentation.You can refer to this [link](https://www.tensorflow.org/tutorials/images/segmentation) for more explanation.


### 3.1 Input Pipeline
Dataset contain test and train folder, it consist of 67 images and masks and 603 images and masks respectively(train-test with a ratio of 90:10).The input shape of each image were reshaped and modified the channel to 128x128 with RGB channel.While the masks images were converted to the grayscale image.Apart from that, all the label of the masks preprocessed to pixel of values of 1 or 0.Besides, the images pixel value was preprocessed into range of [0,1].Next,data augmentation was implemented where the images and masks were flipped horizontally.



### 3.2 Model Pipeline
The simplified version of this architecture of the model was shown in the figure below.A U-Net consists of encoder and decoder where the encoder was construct by using pretrained model MobileNet V2 as feature extractor.The layer of pretrained model was assigned as non-trainable.While the decoder, is to upsample the image size and the images would be concantenated with the pooling layer of pretrained model to restore back the information and to generate the pixel-wise output.



![image](https://user-images.githubusercontent.com/109932205/181675790-c5d978b9-4eb3-4833-88af-1c6e454dc031.png)
Hyperparameter of the model such as batch size and epoch were set as 8 and 10 respectively.The trainig result was shown in the table below and the graph of training loss and validation loss against epoch was shown in the figure below.

|             | Training | Validation |
| ----------- | -------- | ---------- |
| Loss        | 0.0770   | 0.0766     |
| Accuracy(%) | 96.90    | 96.85      |

![image](https://user-images.githubusercontent.com/109932205/181683347-0efe4168-bcb5-467e-8405-7678a09128e0.png)

Besides, the graph show the  convergence sign of training process.
## 4.Result

Figure below show a couple of predictions made by using test data.

![image](https://user-images.githubusercontent.com/109932205/181683398-04777c88-73d7-4930-84b3-945587e2e2f2.png)







 
