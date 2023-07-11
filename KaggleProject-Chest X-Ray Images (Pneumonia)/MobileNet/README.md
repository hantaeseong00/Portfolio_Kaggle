# :pushpin: Kaggle - Chest X-Ray
- Fine-Tuning the MobileNet Model Using the 'Chest X-Rays' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Chest X-Ray.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

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
- Train: [loss: 0.0648, acc: 0.9699]
- Validation: [loss: 0.0793, val_acc: 0.9754]
- Test: [loss: 0.0854, acc: 0.9726]
- Learning Time: 0:38:35.143337

</br>

### 2.2. Change dense value to 16
- Model Architecture: MobileNet - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.0298, acc: 0.9867]
- Validation: [loss: 0.0945, val_acc: 0.9754]
- Test: [loss: 0.0652, acc: 0.9838]
- Learning Time: 0:28:23.514364

</br>

### 2.3. Change dense value to 32
- Model Architecture: MobileNet - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train: [loss: 0.0126, acc: 0.9968]
- Validation: [loss: 0.0992, val_acc: 0.9712]
- Test: [loss: 0.0774, acc: 0.9795]
- Learning Time: 0:28:42.609628

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: MobileNet - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train: [loss: 0.4389, acc: 0.9040]
- Validation: [loss: 0.1930, val_acc: 0.9658]
- Test: [loss: 0.1761, acc: 0.9803]
- Learning Time: 0:30:19.743447

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: MobileNet - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train: [loss: 0.5294, acc: 0.7480]
- Validation: [loss: 0.3263, val_acc: 0.9444]
- Test: [loss: 0.3138, acc: 0.9650]
- Learning Time: 0:28:12.711821

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 5e-5
![](./graph/6.png)
- Train: [loss: 0.0573, acc: 0.9848]
- Validation: [loss: 0.1070, val_acc: 0.9722]
- Test: [loss: 0.0864, acc: 0.9821]
- Learning Time: 0:26:47.903135

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train: [loss: 0.0997, acc: 0.9893]
- Validation: [loss: 0.1916, val_acc: 0.9712]
- Test: [loss: 0.1152, acc: 0.9786]
- Learning Time: 0:26:22.636220

</br>

## 3. The result of MobileNet fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 97.26% | **2315143** |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | **98.38%** | 1703514 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 97.95% | 1722609 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 98.03% | 1819743 |
| **mn_resultset5** | **3** | 8 | 1e-5 | **96.50%** | 1699331 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 98.21% | 1607903 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 97.86% | **1582636** |

</br>

## 6. 회고 / 느낀점
-

</br>