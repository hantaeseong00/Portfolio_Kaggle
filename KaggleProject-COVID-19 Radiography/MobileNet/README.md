# :pushpin: Kaggle - COVID-19
- Fine-Tuning the MobileNet Model Using the 'COVID-19' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-COVID-19.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. MobileNet 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
-Train: [loss: 0.4529, acc: 0.7923]
-Validation: [loss: 0.2231, val_acc: 0.9391]
-Test: [loss: 0.2353, acc: 0.9350]
-Learning Time: 0:19:15.666449

</br>

### 2.2. Change dense value to 16
- Model Architecture: MobileNet - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
-Train: [loss: 0.2010, acc: 0.9191]
-Validation: [loss: 0.1893, val_acc: 0.9391]
-Test: [loss: 0.1922, acc: 0.9390]
-Learning Time: 0:19:07.612430

</br>

### 2.3. Change dense value to 32
- Model Architecture: MobileNet - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
-Train: [loss: 0.1431, acc: 0.9475]
-Validation: [loss: 0.1888, val_acc: 0.9403]
-Test: [loss: 0.1949, acc: 0.9383]
-Learning Time: 0:19:16.932243

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: MobileNet - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
-Train: [loss: 1.0404, acc: 0.5298]
-Validation: [loss: 0.7146, val_acc: 0.9019]
-Test: [loss: 0.7014, acc: 0.8986]
-Learning Time: 0:18:32.903349

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: MobileNet - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
-Train: [loss: 1.2018, acc: 0.6381]
-Validation: [loss: 1.0490, val_acc: 0.8945]
-Test: [loss: 1.0459, acc: 0.9017]
-Learning Time: 0:19:13.645992

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
-Train: [loss: 0.3129, acc: 0.8529]
-Validation: [loss: 0.2870, val_acc: 0.9226]
-Test: [loss: 0.2619, acc: 0.9293]
-Learning Time: 0:18:01.514205

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
-Train: [loss: 0.2746, acc: 0.8603]
-Validation: [loss: 0.4404, val_acc: 0.9303]
-Test: [loss: 0.4301, acc: 0.9260]
-Learning Time: 0:17:19.916322

</br>

## 3. The result of MobileNet fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 93.50% | 1175666 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | **93.90%** | 1147612 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 93.83% | **1176932** |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 89.86% | 1112903 |
| **mn_resultset5** | **3** | 8 | 1e-5 | **90.17%** | 1153645 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 92.93% | 1081514 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 92.60% | **1039916** |

</br>

## 6. 회고 / 느낀점
-

</br>
