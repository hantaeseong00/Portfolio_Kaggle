# :pushpin: Kaggle - COVID-19
- Fine-Tuning the Xception Model Using the 'COVID-19' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-COVID-19.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. Xception 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: Xception - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
-Train: [loss: 0.3257, acc: 0.8494]
-Validation: [loss: 0.3536, val_acc: 0.9439]
-Test: [loss: 0.4474, acc: 0.9301]
-Learning Time: 1:01:47.232429

</br>

### 2.2. Change dense value to 16
- Model Architecture: Xception - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
-Train: [loss: 0.2441, acc: 0.8961]
-Validation: [loss: 0.3563, val_acc: 0.9353]
-Test: [loss: 0.4365, acc: 0.9263]
-Learning Time: 1:01:46.800844

</br>

### 2.3. Change dense value to 32
- Model Architecture: Xception - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
-Train: [loss: 0.0288, acc: 0.9933]
-Validation: [loss: 0.2789, val_acc: 0.9400]
-Test: [loss: 0.3700, acc: 0.9334]
-Learning Time: 1:02:37.174406

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: Xception - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
-Train: [loss: 0.7063, acc: 0.7138]
-Validation: [loss: 0.4301, val_acc: 0.8786]
-Test: [loss: 0.4518, acc: 0.8750]
-Learning Time: 1:04:09.529668

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: Xception - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
-Train: [loss: 1.2585, acc: 0.4751]
-Validation: [loss: 1.1512, val_acc: 0.5288]
-Test: [loss: 1.1533, acc: 0.5402]
-Learning Time: 1:03:32.569916

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: Xception - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
-Train: [loss: 0.2596, acc: 0.9125]
-Validation: [loss: 0.2413, val_acc: 0.9498]
-Test: [loss: 0.3105, acc: 0.9367]
-Learning Time: 1:02:40.027671

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: Xception - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
-Train: [loss: 0.2489, acc: 0.8963]
-Validation: [loss: 0.2849, val_acc: 0.9498]
-Test: [loss: 0.3455, acc: 0.9402]
-Learning Time: 1:01:07.383946

</br>

## 3. The result of Xception fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 93.01% | 3707232 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 92.63% | 3706800 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 93.34% | 3754174 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 87.50% | **3849529** |
| **mn_resultset5** | **3** | 8 | 1e-5 | **54.02%** | 3812059 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 93.67% | 3760027 |
| **mn_resultset7** | 1 | 8 | **1e-4** | **94.02%** | **3667383** |

<br>

## 6. 회고 / 느낀점
-

</br>
