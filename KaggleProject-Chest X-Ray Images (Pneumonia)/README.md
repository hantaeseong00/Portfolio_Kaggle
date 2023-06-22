# :pushpin: Kaggle - Chest X-Ray Images (Pneumonia)
- CNN 모델별(MobileNet, InceptionV3, Xception, ResNet50, VGG16) Chest X-Ray Images (Pneumonia) 데이터 분석 성능 비교

</br>

## 1. 제작 기간 & 참여 인원
- 2023.00.00 ~ 2023.00.00
- 개인 프로젝트

</br>

## 2. 사용 라이브러리(Python)
  - 

</br>

## 3. 소스코드(Colab)
[KaggleProject-Blood Cell.ipynb](https://colab.research.google.com/drive/11vze7G2OSFKjTTldVgSjXBv_S2GLsqGv#scrollTo=UN3anGcRXBCX)

</br>

## 4. 모델 별 loss, acc 그래프 확인
- 기본 아키텍처 : pre_trained_model - F - D - D
- weight : imagenet
- 노드 수 : 16
- Dropout : 0.5
- optimizer : Adam(1e-5)

</br>

### 4.1. MobileNet
![](./graph/MobileNet_loss_acc_graph.png)
- Train : [loss: 0.4888, acc: 0.9880]
- Validation : [loss: 0.4954, val_acc: 0.9744]
- Test : [loss: 0.4937 - acc: 0.9769]
- Learning Time :  0:33:43.225520

</br>

### 4.2. InceptionV3
![](./graph/InceptionV3_loss_acc_graph.png)
loss: 0. - acc: 0. - val_loss: 0. - val_acc: 0.
Learning Time :  
37/37 [==============================] - 17s 462ms/step - loss: 0. - acc: 0.
- Train : [loss: 0.2417, acc: 0.9939]
- Validation : [loss: 0.2784, val_acc: 0.9541]
- Test : [loss: 0.2783 - acc: 0.9556]
- Learning Time :  0:19:59.704119
- Early Stopping : Epoch 16/30

### 4.3. Xception
![](./graph/Xception_loss_acc_graph.png)
- Train : [loss: 0.1125, acc: 0.9444]
- Validation : [loss: 0.0670, val_acc: 0.9840]
- Test : [loss: 0.0406 - acc: 0.9912]
- Learning Time :  0:57:58.333981

</br>

### 4.4. ResNet50
![](./graph/ResNet50_loss_acc_graph.png)
- Train : [loss: 0.0862, acc: 0.9448]
- Validation : [loss: 0.0270, val_acc: 0.9935]
- Test : [loss: 0.0145 - acc: 0.9960]
- Learning Time :  0:54:44.536932

</br>

### 4.5. VGG16
![](./graph/VGG16_loss_acc_graph.png)
- Train : [loss: 0.1831, acc: 0.8877]
- Validation : [loss: 0.0137, val_acc: 0.9960]
- Test : [loss: 0.0189 - acc: 0.9944]
- Learning Time :  1:00:10.589472

</br>

## 5. 모델 별 학습시간, 정확도 그래프
- x : 학습시간
- y : 정확도
- label : [train, validation, test]

![](./graph/compared_model_graph.png)

</br>

## 6. 회고 / 느낀점
-

</br>
