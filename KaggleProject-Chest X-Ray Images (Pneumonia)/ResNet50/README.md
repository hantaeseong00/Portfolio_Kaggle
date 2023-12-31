# :pushpin: Kaggle - Chest X-Ray
- Fine-Tuning the ResNet50 Model Using the 'Chest X-Rays' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Chest X-Ray.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 2. ResNet50 기본 세팅
- weight: imagenet
- Dropout: 0.5
- optimizer: Adam

</br>

### 2.1. Basic
- Model Architecture: ResNet50 - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
- Train: [loss: 0.1291, acc: 0.9955]
- Validation: [loss: 0.0703, val_acc: 0.9744]
- Test: [loss: 0.0984, acc: 0.9769]
- Learning Time: 0:45:15.677119

</br>

### 2.2. Change dense value to 16
- Model Architecture: ResNet50 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.0088, acc: 0.9995]
- Validation: [loss: 0.1038, val_acc: 0.9797]
- Test: [loss: 0.1264, acc: 0.9769]
- Learning Time: 0:43:55.198377

</br>

### 2.3. Change dense value to 32
- Model Architecture: ResNet50 - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train: [loss: 0.0048, acc: 0.9992]
- Validation: [loss: 0.1019, val_acc: 0.9808]
- Test: [loss: 0.0983, acc: 0.9761]
- Learning Time: 0:44:05.800716

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: ResNet50 - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train: [loss: 0.2476, acc: 0.8429]
- Validation: [loss: 0.2938, val_acc: 0.9177]
- Test: [loss: 0.2977, acc: 0.9265]
- Learning Time: 0:44:12.687518

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: ResNet50 - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train: [loss: 0.4830, acc: 0.8461]
- Validation: [loss: 0.2115, val_acc: 0.9722]
- Test: [loss: 0.2137, acc: 0.9692]
- Learning Time: 0:49:21.592140

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: ResNet50 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
- Train: [loss: 0.1127, acc: 0.9949]
- Validation: [loss: 0.0438, val_acc: 0.9882]
- Test: [loss: 0.0754, acc: 0.9812]
- Learning Time: 0:42:09.593870

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: ResNet50 - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train: [loss: 0.0475, acc: 0.9875]
- Validation: [loss: 0.1228, val_acc: 0.9840]
- Test: [loss: 0.1584, acc: 0.9778]
- Learning Time: 0:42:51.028279

</br>

## 3. The result of ResNet50 fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 97.69% | 2715677 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 97.69%% | 2635198 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 97.61% | 2645800 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | **92.65%** | 2652687 |
| **mn_resultset5** | **3** | 8 | 1e-5 | 96.92% | **2961592** |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | **98.12%** | **2529593** |
| **mn_resultset7** | 1 | 8 | **1e-4** | 97.78% | 2571028 |

</br>

## 6. 회고 / 느낀점
>Hidden Layer:
	- Hidden Layer의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- Hidden Layer를 2개로 설정한 mn_resultset4에서는 정확도가 상당히 낮아진 것을 볼 수 있습니다.
	- Hidden Layer의 수를 늘리면 모델이 더 복잡한 패턴을 학습할 수 있지만, 학습에 필요한 데이터 양이 증가할 수도 있습니다.
	- Hidden Layer를 3개로 설정한 mn_resultset5에서는 높은 정확도를 보여줍니다.
	- Hidden Layer의 수를 증가시킴으로써 모델의 표현력이 증가하고, 적절한 학습 데이터로 충분히 학습되었을 것으로 예상됩니다.
>Dense Count:
	- Dense Count의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset2와 mn_resultset3에서 Dense Count를 16과 32로 증가시킨 경우에는 정확도가 비슷한 수준을 유지하는 것을 볼 수 있습니다.<br>
	- 모델의 표현력을 증가시키는 데는 한계가 있었을 것으로 보입니다.<br>
>Learning Rate:<br>
	- Learning Rate의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset6에서 Learning Rate를 5e-5로 설정한 경우에도 높은 정확도를 유지하고 있습니다.<br>
	- 학습 속도를 적절히 조절하여 모델의 성능을 개선한 것으로 보입니다.<br>
>Conculusion:<br>
	- mn_resultset6의 Hidden Layer를 1개, Dense Count를 8로 설정하고 Learning Rate를 5e-5로 설정한 경우가 가장 높은 정확도를 보였습니다.<br>

</br>
