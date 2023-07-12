# :pushpin: Kaggle - COVID-19
- Fine-Tuning the VGG16 Model Using the 'COVID-19' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-COVID-19.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. VGG16 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: VGG16 - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
-Train: [loss: 0.5168, acc: 0.7724]
-Validation: [loss: 0.2945, val_acc: 0.9427]
-Test: [loss: 0.3134, acc: 0.9364]
-Learning Time: 0:49:40.271250

</br>

### 2.2. Change dense value to 16
- Model Architecture: VGG16 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
-Train: [loss: 0.1736, acc: 0.9402]
-Validation: [loss: 0.1846, val_acc: 0.9445]
-Test: [loss: 0.2040, acc: 0.9381]
-Learning Time: 0:49:57.433406

</br>

### 2.3. Change dense value to 32
- Model Architecture: VGG16 - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
-Train: [loss: 0.1736, acc: 0.9402]
-Validation: [loss: 0.1846, val_acc: 0.9445]
-Test: [loss: 0.2040, acc: 0.9381]
-Learning Time: 0:49:57.433406

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: VGG16 - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
-Train: [loss: 1.1019, acc: 0.5639]
-Validation: [loss: 0.8545, val_acc: 0.9318]
-Test: [loss: 0.8581, acc: 0.9149]
-Learning Time: 0:49:31.326334

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: VGG16 - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
-Train: [loss: 1.1556, acc: 0.4359]
-Validation: [loss: 0.9527, val_acc: 0.4815]
-Test: [loss: 0.9515, acc: 0.4816]
-Learning Time: 0:48:39.805336

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: VGG16 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
-Train: [loss: 0.5653, acc: 0.8096]
-Validation: [loss: 0.3972, val_acc: 0.9223]
-Test: [loss: 0.3957, acc: 0.9296]
-Learning Time: 0:48:56.834425

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: VGG16 - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
-Train: [loss: 0.3950, acc: 0.8124]
-Validation: [loss: 0.2232, val_acc: 0.9312]
-Test: [loss: 0.3957, acc: 0.9296]
-Learning Time: 0:48:56.834425

</br>

## 3. The result of VGG16 fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 93.64% | 2980271 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | **93.81%** | **2997433** |
| **mn_resultset3** | 1 | **32** | 1e-5 | 93.81% | 2997433 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 91.49% | 2971326 |
| **mn_resultset5** | **3** | 8 | 1e-5 | **48.16%** | **2915805** |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 92.96% | 2936834 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 92.96% | 2936834 |

</br>

## 6. 회고 / 느낀점
-

</br>
