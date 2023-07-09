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
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-5
![](./Graph/1.png)
- Train : [loss: 0.4201, acc: 0.8180]
- Validation : [loss: 0.0563, val_acc: 0.9925]
- Test : [loss: 0.0385, acc: 0.9948]
- Learning Time : 1:00:08.099976

</br>

### 2.2. Change dense value to 16
- Model Architecture: MobileNet - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train : [loss: 0.0896, acc: 0.9729]
- Validation : [loss: 0.0266, val_acc: 0.9930]
- Test : [loss: 0.0127, acc: 0.9976]
- Learning Time : 0:57:24.579436

</br>

### 2.3. Change dense value to 32
- Model Architecture: MobileNet - F - D(32)
- Learning Rate: 1e-5
![](./Graph/3.png)
- Train : [loss: 0.0110, acc: 0.9966]
- Validation : [loss: 0.0186, val_acc: 0.9975]
- Test : [loss: 0.0203, acc: 0.9952]
- Learning Time : 0:59:01.862169

</br>

### 2.4. Change the number of hidden layers to 2
- Model Architecture: MobileNet - F - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/4.png)
- Train : [loss: 0.8968, acc: 0.5598]
- Validation : [loss: 0.3956, val_acc: 0.7875]
- Test : [loss: 0.3965, acc: 0.7900]
- Learning Time : 1:00:42.714123

</br>

### 2.5. Change the number of hidden layers to 3
- Model Architecture: MobileNet - F - D(8) - D(8) - D(8)
- Learning Rate: 1e-5
![](./Graph/5.png)
- Train : [loss: 1.1404, acc: 0.5053]
- Validation : [loss: 0.9254, val_acc: 0.8970]
- Test : [loss: 0.9224, acc: 0.9056]
- Learning Time : 1:04:22.204818

</br>

### 2.6. Change learning rate value to 5e-5
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 5e-5
![](./graph/6.png)
- Train : [loss: 0.3715, acc: 0.8345]
- Validation : [loss: 0.0782, val_acc: 0.9885]
- Test : [loss: 0.0533, acc: 0.9896]
- Learning Time : 0:56:14.163438

</br>

### 2.7. Change learning rate value to 1e-4
- Model Architecture: MobileNet - F - D(8)
- Learning Rate: 1e-4
![](./Graph/7.png)
- Train : [loss: 0.2687, acc: 0.8556]
- Validation : [loss: 0.0216, val_acc: 0.9945]
- Test : [loss: 0.0298, acc: 0.9928]
- Learning Time : 0:55:34.746021

</br>

## 3. The result of MobileNet fine-tuning

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| **mn_resultset1** | 1 | 8 | 1e-5 | 99.48% | 3608099.976 |
|  |  |  |  |  |  |
| **mn_resultset2** | 1 | **16** | 1e-5 | **99.76%** | 3444579.436 |
| **mn_resultset3** | 1 | **32** | 1e-5 | 99.52% | 3541862.169 |
|  |  |  |  |  |  |
| **mn_resultset4** | **2** | 8 | 1e-5 | **79.00%** | 3642714.123 |
| **mn_resultset5** | **3** | 8 | 1e-5 | 90.56% | **3862204.818** |
|  |  |  |  |  |  |
| **mn_resultset6** | 1 | 8 | **5e-5** | 98.96% | 3374163.438 |
| **mn_resultset7** | 1 | 8 | **1e-4** | 99.28% | **3334746.021** |


</br>

## 4. Reflection

- 히든 레이어와 정확도
	- 실험 결과에 따르면, 히든 레이어의 수가 증가함에 따라 정확도가 감소하는 경향이 있습니다. 
	- 히든레이어가 2개 또는 3개인 모델들은 다른 모델들보다 상대적으로 낮은 정확도를 보여주었습니다. 
	- 히든레이어의 수가 증가할수록 모델의 복잡성이 증가하고, 적절한 수의 히든레이어가 모델의 성능을 향상시킬 수 있음을 시사합니다.

- 덴스 수 증가와 정확도
	- 실험 결과를 분석한 결과, 덴스 수가 증가함에 따라 정확도가 증가하는 경향을 관찰할 수 있었습니다.
	- 덴스 수가 16인 모델은 다른 모델들보다 높은 정확도를 보여주었습니다. 
	- 그러나 덴스 수가 32인 모델은 높은 정확도를 기록하였으나 덴스 수가 16인 모델보다 낮은 정확도를 보여주었습니다. 
	- 이는 덴스의 수를 증가시키는 것이 항상 모델의 성능을 향상시키는 것은 아니며, 적절한 수준을 찾는 것이 중요하다는 것을 시사합니다.

- 러닝 레이트와 정확도
	- 러닝 레이트가 영향을 끼치지 않는 결과를 보여주고 있습니다
	- 러닝 레이트가 5e-5인 모델은 베이직 모델보다 상대적으로 낮은 정확도를 기록하였습니다.
	- 하지만 러닝 레이트가 1e-4인 모델은 상대적으로 높은 정확도를 기록하였습니다.
	- 이는 적절한 학습률을 선택하는 것이 모델의 성능을 최적화하는 데 중요하다는 것을 시사합니다.
	
- 히든 레이어와 학습시간
	- 실험 결과에 따르면, 히든 레이어의 수가 증가함에 따라 학습시간이 증가하는 경향이 있습니다. 
	- 히든레이어가 2개인 모델은 다른 모델들보다 긴 학습시간을 보여주었습니다. 
	- 그러나 히든레이어의 수가 3개인 모델은 히든레이어 수가 2개인 모델보다 낮은 학습시간을 보여줬습니다.
	- 이는 히든레이어 수를 감소시키는 것이 항상 모델의 학습시간을 감소시키는 것은 아니며, 적절한 수준을 찾는 것이 중요하다는 것을 시사합니다.
	
- 덴스 수 증가와 학습시간
	- 실험 결과에 따르면, 덴스의 수가 증가함에 따라 학습시간이 감소하는 경향이 있습니다. 
	- 덴스 수가 16개 또는 32개인 모델들은 다른 모델들보다 상대적으로 낮은 학습시간을 보여주었습니다. 
	- 이는 덴스의 수가 증가할수록 학습시간을 낮출 수 있음을 시사합니다.

- 러닝 레이트와 학습시간
	- 실험 결과에 따르면, 러닝레이트의 수가 증가함에 따라 학습시간이 감소하는 경향이 있습니다. 
	- 러닝 레이트가 5e-5 또는 1e-4인 모델들은 다른 모델들보다 상대적으로 낮은 학습시간을 보여주었습니다. 
	- 러닝 레이트 수가 증가할수록 학습시간을 낮출 수 있음을 시사합니다.
	
</br>
