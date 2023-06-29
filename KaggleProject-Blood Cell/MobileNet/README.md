# :pushpin: Kaggle - Blood Cell
- Fine-Tuning the MobileNet Model Using the 'Blood Cells' Dataset

</br>

## 1. 소스코드(Colab)
[KaggleProject-Blood Cell.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. MobileNet 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-5
![](./graph/1.png)
- Train : [loss: 0.3532, acc: 080559239]
- Validation : [loss: 0.0372, val_acc: 0.9950]
- Test : [loss: 0.0428 - acc: 0.9920]
- Learning Time :  0:20:39.368073

</br>

### 2.2. Change dense value to 16
- Model Architecture: MobileNet - F - D(16)
- Learning Rate: 1e-5
![](./graph/2.png)
- Train : [loss: 0.0974, acc: 0.9550]
- Validation : [loss: 0.0225, val_acc: 0.9920]
- Test : [loss: 0.0230 - acc: 0.9904]
- Learning Time :  0:19:32.322051

</br>

### 2.3. Change dense value to 32
- Model Architecture: MobileNet - F - D(32)
- Learning Rate: 1e-5
![](./graph/3.png)
- Train : [loss: 0.0205, acc: 0.9948]
- Validation : [loss: 0.0174, val_acc: 0.9960]
- Test : [loss: 0.0278 - acc: 0.9900]
- Learning Time :  0:20:48.259764

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: MobileNet - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./graph/4.png)
- Train : [loss: 1.0668, acc: 0.5576]
- Validation : [loss: 0.8729, val_acc: 0.7760]
- Test : [loss: 0.8782 - acc: 0.7804]
- Learning Time :  0:20:51.236816

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: MobileNet - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./graph/5.png)
- Train : [loss: 1.3084, acc: 0.3528]
- Validation : [loss: 0.2070, val_acc: 0.4835]
- Test : [loss: 1.1995 - acc: 0.4764]
- Learning Time :  0:19:52.120732

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 5e-5
![](./graph/6.png)
- Train : [loss: 0.3148, acc: 0.8298]
- Validation : [loss: 0.0276, val_acc: 0.9960]
- Test : [loss: 0.0492 - acc: 0.9936]
- Learning Time :  0:25:30.702825

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-4
![](./graph/7.png)
- Train : [loss: 0.2533, acc: 0.8445]
- Validation : [loss: 0.0672, val_acc: 0.9845]
- Test : [loss: 0.0721 - acc: 0.9836]
- Learning Time :  0:12:19.493237

</br>

## 3. The result of MobileNet fine-tuning

![](./graph/compared_model_graph.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | **99.20%** | 368073 |
|  |  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 99.04% | 322051 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 99.00% | 259764 |
|  |  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 78.04% | 236816 |
| **mn_resultset5** | **3** | 8 | 1e-5 | **47.64%** | 120732 |
|  |  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **1e-5** | **99.36%** | **702825** |
| **mn_resultset7** | 1 | 8 | **1e-5** | 78.36% | **493237** |


</br>

## 6. 회고 / 느낀점
-

</br>
