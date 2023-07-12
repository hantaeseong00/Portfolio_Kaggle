# :pushpin: Kaggle - Chest X-Ray
- Fine-Tuning the Xception Model Using the 'Chest X-Ray' Dataset

</br>

## 1. 소스코드(Colab)
- [KaggleProject-Chest X-Ray.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

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
-Train: [loss: 0.0525, acc: 0.9627]
-Validation: [loss: 0.0994, val_acc: 0.9701]
-Test: [loss: 0.1454, acc: 0.9667]
-Learning Time: 0:46:39.773500

</br>

### 2.2. Change dense value to 16
- Model Architecture: Xception - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
-Train: [loss: 0.0128, acc: 0.9987]
-Validation: [loss: 0.0996, val_acc: 0.9733]
-Test: [loss: 0.1832, acc: 0.9650]
-Learning Time: 0:45:28.518346

</br>

### 2.3. Change dense value to 32
- Model Architecture: Xception - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
-Train: [loss: 0.0071, acc: 0.9987]
-Validation: [loss: 0.0855, val_acc: 0.9765]
-Test: [loss: 0.1677, acc: 0.9675]
-Learning Time: 0:45:31.250777

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: Xception - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
-Train: [loss: 0.2962, acc: 0.9096]
-Validation: [loss: 0.2271, val_acc: 0.9712]
-Test: [loss: 0.2450, acc: 0.9581]
-Learning Time: 0:49:08.442575

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: Xception - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
-Train: [loss: 0.5484, acc: 0.7397]
-Validation: [loss: 0.3992, val_acc: 0.9573]
-Test: [loss: 0.3989, acc: 0.9590]
-Learning Time: 0:54:51.391264

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: Xception - F - D(8)
- Learning Rate: 5e-5
![](./Graph/6.png)
-Train: [loss: 0.1187, acc: 0.9885]
-Validation: [loss: 0.0938, val_acc: 0.9744]
-Test: [loss: 0.1277, acc: 0.9718]
-Learning Time: 0:50:50.284919

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: Xception - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
-Train: [loss: 0.0565, acc: 0.9859]
-Validation: [loss: 0.1144, val_acc: 0.9797]
-Test: [loss: 0.1476, acc: 0.9692]
-Learning Time: 0:50:25.817765

</br>

## 3. The result of Xception fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 96.67% | 2799773 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | 96.50% | **2728518** |
| **mn_resultset3** | 1 | **32** | 1e-5 | 96.75% | 2731250 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | **95.81%** | 2948442 |
| **mn_resultset5** | **3** | 8 | 1e-5 | 95.90% | **3291391** |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | **97.18%** | 3050284 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 96.92% | 3025817 |

</br>

## 6. 회고 / 느낀점
>Hidden Layer:<br>
	- Hidden Layer의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- Hidden Layer를 2개로 설정한 mn_resultset4에서는 정확도가 상당히 낮아진 것을 볼 수 있습니다.<br>
	- Hidden Layer의 수를 늘리면 모델이 더 복잡한 패턴을 학습할 수 있지만, 학습에 필요한 데이터 양이 증가할 수도 있습니다.<br>
	- Hidden Layer를 3개로 설정한 mn_resultset5에서는 높은 정확도를 보여줍니다. <br>
	- Hidden Layer의 수를 증가시킴으로써 모델의 표현력이 증가하고, 적절한 학습 데이터로 충분히 학습되었을 것으로 예상됩니다.<br>
>Dense Count:<br>
	- Dense Count가 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset2와 mn_resultset3에서 Dense Count를 16과 32로 증가시킨 경우에는 정확도가 비슷한 수준을 유지하는 것을 볼 수 있습니다.<br>
	- 모델의 표현력을 증가시키는 데는 한계가 있었을 것으로 보입니다.<br>
>Learning Rate:<br>
	- Learning Rate의 증가에 따른 경향성을 파악 할 수 없었습니다.<br>
	- mn_resultset5에서 Learning Rate를 1e-5로 설정한 경우에도 높은 정확도를 유지하고 있습니다.<br>
	- 학습 속도를 적절히 조절하여 모델의 성능을 개선한 것으로 보입니다.<br>
>Conculusion:<br>
	- mn_resultset6의 Hidden Layer를 1개, Dense Count를 8로 설정하고 Learning Rate를 5e-5로 설정한 경우가 가장 높은 정확도를 보였습니다.<br>

</br>
