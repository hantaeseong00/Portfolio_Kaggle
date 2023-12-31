# :pushpin: Kaggle - COVID-19
- Fine-Tuning the InceptionV3 Model Using the 'COVID-19' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-COVID-19.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

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
-Train: [loss: 0.3584, acc: 0.8459]
-Validation: [loss: 0.2892, val_acc: 0.9273]
-Test: [loss: 0.2789, acc: 0.9267]
-Learning Time: 0:37:22.135810


</br>

### 2.2. Change dense value to 16
- Model Architecture: InceptionV3 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
-Train: [loss: 0.1171, acc: 0.9491]
-Validation: [loss: 0.3531, val_acc: 0.9247]
-Test: [loss: 0.3588, acc: 0.9286]
-Learning Time: 0:33:52.998940

</br>

### 2.3. Change dense value to 32
- Model Architecture: InceptionV3 - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
-Train: [loss: 0.0304, acc: 0.9925]
-Validation: [loss: 0.3265, val_acc: 0.9323]
-Test: [loss: 0.3481, acc: 0.9336]
-Learning Time: 0:32:43.499508

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: InceptionV3 - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
-Train: [loss: 0.8644, acc: 0.7231]
-Validation: [loss: 0.5290, val_acc: 0.9123]
-Test: [loss: 0.5627, acc: 0.9173]
-Learning Time: 0:42:05.952831

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: InceptionV3 - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
-Train: [loss: 1.1834, acc: 0.5419]
-Validation: [loss: 1.0620, val_acc: 0.8597]
-Test: [loss: 1.0627, acc: 0.8488]
-Learning Time: 0:43:16.059274

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
-Train: [loss: 0.2802, acc: 0.8586]
-Validation: [loss: 0.3454, val_acc: 0.9445]
-Test: [loss: 0.3972, acc: 0.9440]
-Learning Time: 0:32:30.708499

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
-Train: [loss: 0.3295, acc: 0.8938]
-Validation: [loss: 0.2912, val_acc: 0.9386]
-Test: [loss: 0.3809, acc: 0.9334]
-Learning Time: 0:34:04.444849

</br>

## 3. The result of InceptionV3 fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 92.67% | 2242135 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 92.86% | 2032998 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 93.36% | 1963499 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | **91.73%** | 2525952 |
| **mn_resultset5** | **3** | 8 | 1e-5 | 91.88% | **2596059** |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | **94.40%** | **1950708** |
| **mn_resultset7** | 1 | 8 | **1e-4** | 93.34% | 2044449 |

</br>

## 6. 회고 / 느낀점
>Hidden Layer:<br>
	- Hidden Layer의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- Hidden Layer를 2개로 설정한 mn_resultset4에서는 정확도가 낮아진 것을 볼 수 있습니다.<br>
	- Hidden Layer를 추가하여 모델의 복잡성을 증가시키는 것이 항상 더 좋은 결과를 가져오는 것은 아니며, 과적합의 가능성도 존재합니다.<br>
	- Hidden Layer를 3개로 설정한 mn_resultset5에서는 정확도가 증가한 것을 볼 수 있습니다. <br>
	- Hidden Layer의 수를 늘리면 모델의 표현력이 향상되어 더 복잡한 패턴을 학습할 수 있습니다.<br>
>Dense Count:<br>
	- Dense Count의 증가에 따라 정확도가 증가하는 경향성을 확인 하였습니다.<br>
	- mn_resultset2와 mn_resultset3에서 Dense Count를 16과 32로 증가시킨 경우에는 약간의 정확도 향상이 있습니다.<br>
	- 모델의 표현력을 증가시키는 데에는 일정한 효과가 있었을 것으로 보입니다.<br>
>Learning Rate:<br>
	- Learning Rate의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset5에서 Learning Rate를 1e-5로 설정한 경우에도 정확도가 유지되고 있습니다. 적절한 학습 속도를 선택하여 모델의 성능을 개선할 수 있습니다.<br>
>Conculusion:<br>
	- mn_resultset6의 Hidden Layer를 1개, Dense Count를 8로 설정하고 Learning Rate를 5e-5로 설정한 경우가 가장 높은 정확도를 보였습니다.<br>

</br>
