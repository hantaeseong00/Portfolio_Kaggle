# :pushpin: Kaggle - Blood Cell
- Fine-Tuning the Xception Model Using the 'Blood Cells' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Blood Cell.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

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
- Train: [loss: 0.3409, acc: 0.8032]
- Validation: [loss: 0.0331, val_acc: 0.9910]
- Test: [loss: 0.0312, acc: 0.9920]
- Learning Time: 1:19:29.017577

</br>

### 2.2. Change dense value to 16
- Model Architecture: Xception - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.1011, acc: 0.9550]
- Validation: [loss: 0.0475, val_acc: 0.9880]
- Test: [loss: 0.0216, acc: 0.9932]
- Learning Time: 1:18:20.149439

</br>

### 2.3. Change dense value to 32
- Model Architecture: Xception - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train: [loss: 0.0136, acc: 0.9968]
- Validation: [loss: 0.0559, val_acc: 0.9850]
- Test: [loss: 0.0404, acc: 0.9884]
- Learning Time: 1:14:48.856020

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: Xception - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train: [loss: 0.9441, acc: 0.6242]
- Validation: [loss: 0.6074, val_acc: 0.9690]
- Test: [loss: 0.6097, acc: 0.9700]
- Learning Time: 1:23:35.576984

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: Xception - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train: [loss: 1.1745, acc: 0.4899]
- Validation: [loss: 0.9848, val_acc: 0.9345]
- Test: [loss: 0.9836, acc: 0.9472]
- Learning Time: 1:21:43.406829

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: Xception - F - D(8)
- Learning Rate: 5e-5
![](./graph/6.png)
- Train: [loss: 0.2317, acc: 0.8637]
- Validation: [loss: 0.0098, val_acc: 0.9970]
- Test: [loss: 0.0074, acc: 0.9976]
- Learning Time: 1:19:22.879675

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: Xception - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train: [loss: 0.2061, acc: 0.9083]
- Validation: [loss: 0.0052, val_acc: 0.9990]
- Test: [loss: 0.0068, acc: 0.9992]
- Learning Time: 1:14:44.084134

</br>

## 3. The result of Xception fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 99.20% | 4769017 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 99.32% | 4700149 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 98.84% | 4488856 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 97.00% | **5015576** |
| **mn_resultset5** | **3** | 8 | 1e-5 | **94.72%** | 4903406 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 99.76% | 4762879 |
| **mn_resultset7** | 1 | 8 | **1e-4** | **99.92%** | **4484084** |

</br>

## 6. 회고 / 느낀점
-

</br>
