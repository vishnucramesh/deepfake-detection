
# Deepfake Image Detecton

A deep neural network based solution to detect fake/real images

## Data set

We are using the dataset from the Kaggle challenge [here](https://www.kaggle.com/xhlulu/140k-real-and-fake-faces)

#### Sample images in dataset
![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/dataset.png?raw=true)
## How to run


I suggest you to use [Google Colab](https://colab.research.google.com/) to make use of free GPU, but sometime colab will be very slow and runtime will close once window is closed or when computer sleeps. In that case run notebook and run directly on system kernel.

In my case colab was very slow, I started notbook in my machine and connected local run time in colab. [Refer here to setup local runtime.](https://research.google.com/colaboratory/local-runtimes.html) 

To Download dataset directly from kaggle to googe drive you can use following code snippet.

```python
"""
Step 1: Upload the API key file provided by kaggle to a location in google drive
Step 2: Set the config file as the environemnt variable
Step 5: Change working directory
Step 3: Get kaggle download link from kaggle 
"""

import os

# set kaggle config file directory
os.environ['KAGGLE_CONFIG_DIR'] = "/content/drive/MyDrive/Kaggle"

%cd /content/drive/MyDrive/Kaggle/

!kaggle datasets download -d xhlulu/140k-real-and-fake-faces --unzip
```
## Result

#### 88% accuracy on test sets

![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/accuracy.png?raw=true)

### Resnet50 - Tranfer Learning

#### Baseline Model

![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/resnet_tf_acc.png?raw=true)
![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/resnet_tf_loss.png?raw=true)

#### Fine Tuned Model

![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/resnet_tf_ft_acc.png?raw=true)
![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/resnet_tf_ft_loss.png?raw=true)


### Densenet - Tranfer Learning

#### Baseline Model

![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/densenet_tf_acc.png?raw=true)
![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/densenet_tf_loss.png?raw=true)


#### Fine Tuned Model

![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/densenet_tf_ft_Acc.png?raw=true)
![alt text](https://github.com/vishnucramesh/deepfake-detection/blob/master/images/result/densenet_tf_ft_loss.png?raw=true)
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
