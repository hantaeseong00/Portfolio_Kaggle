# :pushpin: Kaggle - Chest X-Ray
- CNN 모델별(MobileNet, InceptionV3, Xception, ResNet50) Chest X-Ray 데이터 분석 성능 비교

</br>

## 1. 제작 기간 & 참여 인원
- 2023.00.00 ~ 2023.00.00
- 개인 프로젝트

</br>

## 2. 사용 라이브러리(Python)
  - 

</br>

## 3. 소스코드(Colab)
[KaggleProject-Chest X-Ray.ipynb](https://colab.research.google.com/drive/18BXx_fb77k9KbYsv_bVidVf9FhbqK2KA#scrollTo=f2XiUpwDXhNq)

</br>

## 4. 모델 비교
- 기본 아키텍처 : pre_trained_model - F - D - D
- weight : imagenet
- 노드 수 : 16
- Dropout : 0.5
- optimizer : Adam(1e-5)

</br>

### 4.1. MobileNet
- Model Architecture: MobileNet - F - D(16)
- Learning Rate: 1e-5
![](./Graph/2.png)
- Train: [loss: 0.0298, acc: 0.9867]
- Validation: [loss: 0.0945, val_acc: 0.9754]
- Test: [loss: 0.0652, acc: 0.9838]
- Learning Time: 0:28:23.514364

</br>

### 4.2. InceptionV3
- Model Architecture: InceptionV3 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/InceptionV3.png)
- Train: [loss: 0.0375, acc: 0.9808]
- Validation: [loss: 0.1004, val_acc: 0.9808]
- Test: [loss: 0.0980, acc: 0.9752]
- Learning Time: 0:40:56.483226

</br>

### 4.3. Xception
- Model Architecture: Xception - F - D(8)
- Learning Rate: 5e-5
![](./Graph/Xception.png)
-Train: [loss: 0.1187, acc: 0.9885]
-Validation: [loss: 0.0938, val_acc: 0.9744]
-Test: [loss: 0.1277, acc: 0.9718]
-Learning Time: 0:50:50.284919

</br>

### 4.4. ResNet50
- Model Architecture: ResNet50 - F - D(8)
- Learning Rate: 5e-5
![](./Graph/ResNet50.png)
- Train: [loss: 0.1127, acc: 0.9949]
- Validation: [loss: 0.0438, val_acc: 0.9882]
- Test: [loss: 0.0754, acc: 0.9812]
- Learning Time: 0:42:09.593870

</br>

### 4.4. VGG16
- Model Architecture: VGG16 - F - D(16)
- Learning Rate: 1e-5
![](./Graph/VGG16.png)
- Train: [loss: 0.0243, acc: 0.9907]
- Validation: [loss: 0.1040, val_acc: 0.9754]
- Test: [loss: 0.1024, acc: 0.9735]
- Learning Time: 0:38:45.366013

</br>

## 5. 모델 별 학습시간, 정확도 그래프

![](./Graph/result.png)

| Model | Hidden Layer | Dense Count | Learning Rate | Accuracy | Learning Time(ms) | 
| :-- | :-: | :-: | :-: | :-: | :-: |
| MobileNet | 1 | 16 | 1e-5 | 98.38% | 1703514 |
| InceptionV3 | 1 | 8 | 5e-5 | 97.52% | 2456483 |
| Xception | 1 | 8 | 5e-5 | 97.18% | 3050284 |
| ResNet50 | 1 | 8 | 5e-5 | 98.12% | 2529593 |
| VGG16 | 1 | 16 | 1e-5 | 97.35% | 2325366 |

</br>

## 6. 회고 / 느낀점
>정확도:<br>
	- MobileNet 모델이 가장 높은 정확도를 보여주고,<br>
	- 그 다음으로 ResNet50 모델이 높은 정확도를 보여줍니다.<br>
>학습시간:<br>
	- MobileNet 모델이 가장 빠른 학습 시간을 보여주고,<br>
	- 그 다음으로 VGG16 모델이 빠른 학습 시간을 보여줍니다.<br>

</br>
