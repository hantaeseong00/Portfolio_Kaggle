# :pushpin: Kaggle - Chest X-Ray
- Fine-Tuning the InceptionV3 Model Using the 'Chest X-Ray' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Chest X-Ray.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

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
- Train: [loss: 0.0834, acc: 0.9773]
- Validation: [loss: 0.1125, val_acc: 0.9679]
- Test: [loss: 0.1191, acc: 0.9726]
- Learning Time: 0:43:58.176296


</br>

### 2.2. Change dense value to 16
- Model Architecture: InceptionV3 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.0172, acc: 0.9965]
- Validation: [loss: 0.1520, val_acc: 0.9647]
- Test: [loss: 0.1304, acc: 0.9726]
- Learning Time: 0:42:56.175761

</br>

### 2.3. Change dense value to 32
- Model Architecture: InceptionV3 - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train: [loss: 0.0054, acc: 0.9995]
- Validation: [loss: 0.1420, val_acc: 0.9690]
- Test: [loss: 0.1475, acc: 0.9632]
- Learning Time: 0:42:14.161199

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: InceptionV3 - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train: [loss: 0.3541, acc: 0.8347]
- Validation: [loss: 0.1579, val_acc: 0.9669]
- Test: [loss: 0.1605, acc: 0.9607]
- Learning Time: 0:54:04.894952

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: InceptionV3 - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train: [loss: 0.4921, acc: 0.6413]
- Validation: [loss: 0.4707, val_acc: 0.7297]
- Test: [loss: 0.4700, acc: 0.7299]
- Learning Time: 0:49:31.292331

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
- Train: [loss: 0.0375, acc: 0.9808]
- Validation: [loss: 0.1004, val_acc: 0.9808]
- Test: [loss: 0.0980, acc: 0.9752]
- Learning Time: 0:40:56.483226

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train: [loss: 0.1020, acc: 0.9603]
- Validation: [loss: 0.4744, val_acc: 0.9327]
- Test: [loss: 0.3179, acc: 0.9470]
- Learning Time: 0:36:49.548395

</br>

## 3. The result of InceptionV3 fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 97.26% | 2638176 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 97.26% | 2576175 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 96.32% | 2534161 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | 96.07% | **3244894** |
| **mn_resultset5** | **3** | 8 | 1e-5 | **72.99%** | 2979292 |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | **97.52%** | 2456483 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 94.70% | **2209348** |

</br>

## 6. 회고 / 느낀점
>Hidden Layer:<br>
	- Hidden Layer가 증가할 수록 성능이 감소하는 경향성을 확인 할 수 있습니다.<br>
	- Hidden Layer를 2개로 설정한 mn_resultset4에서는 정확도가 약간 감소한 것을 볼 수 있습니다.<br>
	- Hidden Layer의 수를 증가시키면 모델의 복잡성이 증가하여 일부 데이터에 대해 과적합이 발생할 수 있습니다.<br>
	- Hidden Layer를 3개로 설정한 mn_resultset5에서는 낮은 정확도를 보여줍니다.<br>
	- Hidden Layer의 수를 증가시킬 경우, 모델이 더 복잡한 특징을 학습하기 위해 더 많은 데이터와 시간이 필요할 수 있습니다.<br>
>Dense Count:<br>
	- Dense Count가 증가할 수록 성능이 감소하는 경향성을 확인 할 수 있습니다.<br>
	- mn_resultset2와 mn_resultset3에서 Dense Count를 16과 32로 증가시킨 경우에는 정확도가 변하지 않거나 오히려 줄어든 것을 볼 수 있습니다.<br>
	- Dense Count를 늘려도 모델의 성능 향상에 한계가 있었을 것으로 보입니다.<br>
>Learning Rate:<br>
	- Learning Rate의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset7에서 Learning Rate를 1e-4로 증가시킨 경우에는 정확도가 낮아진 것을 볼 수 있습니다.<br>
	- 너무 큰 학습률은 모델의 학습 과정을 불안정하게 만들 수 있으므로 주의가 필요합니다.<br>
>Conculusion:<br>
	- mn_resultset6의 Hidden Layer를 1개, Dense Count를 8로 설정하고 Learning Rate를 5e-5로 설정한 경우가 가장 높은 정확도를 보였습니다.<br>

</br>
