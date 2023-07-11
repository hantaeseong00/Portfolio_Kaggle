# :pushpin: Kaggle - Blood Cell
- Fine-Tuning the InceptionV3 Model Using the 'Blood Cells' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Blood Cell.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. InceptionV3 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
- Train: [loss: 0.3059, acc: 0.8248]
- Validation: [loss: 0.0316, val_acc: 0.9935]
- Test: [loss: 0.0309, acc: 0.9944]
- Learning Time: 0:53:20.448415


</br>

### 2.2. Change dense value to 16
- Model Architecture: InceptionV3 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.1335, acc: 0.9514]
- Validation: [loss: 0.0219, val_acc: 0.9930]
- Test: [loss: 0.0227, acc: 0.9948]
- Learning Time: 0:50:05.980897

</br>

### 2.3. Change dense value to 32
- Model Architecture: InceptionV3 - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train: [loss: 0.0145, acc: 0.9959]
- Validation: [loss: 0.0319, val_acc: 0.9910]
- Test: [loss: 0.0239, acc: 0.9944]
- Learning Time: 0:47:13.427400

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: InceptionV3 - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train: [loss: 0.9951, acc: 0.5164]
- Validation: [loss: 0.6088, val_acc: 0.9900]
- Test: [loss: 0.6134, acc: 0.9916]
- Learning Time: 0:54:24.468800

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: InceptionV3 - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train: [loss: 1.1591, acc: 0.4356]
- Validation: [loss: 1.0270, val_acc: 0.5010]
- Test: [loss: 1.0250, acc: 0.5008]
- Learning Time: 0:48:10.646637

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 5e-5
![](./graph/6.png)
- Train: [loss: 0.2926, acc: 0.8252]
- Validation: [loss: 0.0194, val_acc: 0.9970]
- Test: [loss: 0.0071, acc: 0.9984]
- Learning Time: 0:41:58.517229

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train: [loss: 0.2757, acc: 0.8615]
- Validation: [loss: 0.7322, val_acc: 0.8970]
- Test: [loss: 0.7722, acc: 0.8956]
- Learning Time: 0:41:14.884448

</br>

## 3. The result of InceptionV3 fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 99.44% | 3200044.415 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 99.48% | 3005980.897 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 99.00% | 2833427.4 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 99.44% | **3264468.8** |
| **mn_resultset5** | **3** | 8 | 1e-5 | **50.08%** | 2890646.637 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | **99.84%** | 2518517.229 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 89.56% | **2474884.448** |

</br>

## 6. 회고 / 느낀점
-

</br>
