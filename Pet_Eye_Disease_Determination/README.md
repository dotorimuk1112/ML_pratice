# Pet Eye Disease Determination

##1. Description
 aihub에서 제공하는 반려견 안구질환 데이터를 활용한 연습 목적의 프로젝트.
 aihub에서 소개하듯이, 견주들이 해당 모델이 적용된 어플리케이션을 활용하여 동물병원 방문이 어려운 야간, 주말에도 사진을 찍어 안구질환 여부를 쉽게 판별할 수 있다.
 나아가, 육안으로 식별할 수 있는 다른 질병의 데이터셋을 확보하여 안구질환뿐만 아니라 피부질환 등에 대해서도 판별할 수 있을 것이다.
 
 
##2. Environment
 Python Version: 3.9.13
 
##3. Dataset
url: https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=562
결막염과 백내장 두 가지 질병에 대한 데이터셋이나, 컬러로 된 결막염 데이터셋만 활용하였다.

##4. model explanation
 모델은 Keras의 CNN을 사용했다. 데이터셋은 2차원 컬러 이미지로서 단순 이진분류(병이 있는지 없는지)를 판단하기에는 가장 직관적이고 높은 정확도를 보일 것으로 판단했기 때문이다.

##5. Hyperparameter Tuning
 ###version 1
   image resolution: 64x64
   filter: 32
   kernel size: 3, 3
   padding: same padding
   pool size: 2, 2
   dropout: 25%
   epoch: 20
   early stop patience: 2
   output layer activation function: softmax
   
   accuracy: 0.9471
   
 ###version 2
  이미지 해상도를 128x128로 늘리고 kernel size 등의 파라미터도 두 배로 늘림.
   image resolution: 128x128
   filter: 32
   kernel size: 6, 6
   padding: same padding
   pool size: 4, 4
   dropout: 25%
   epoch: 20
   early stop patience: 2
   output layer activation function: softmax
   
   accuracy: 0.9894
   
 ###version 3
  이미지 해상도를 256x256으로 한 차례 더 두 배.
   image resolution: 256x256
   filter: 32
   kernel size: 12, 12
   padding: same padding
   pool size: 8, 8
   dropout: 25%
   epoch: 20
   early stop patience: 2
   output layer activation function: softmax
   
   accuracy: 0.9418
   
 ###version 4
  이미지 해상도를 128x128로 되돌리고 출력층 활성화 함수를 sigmoid 함수로 변경
   image resolution: 128x128
   filter: 32
   kernel size: 6, 6
   padding: same padding
   pool size: 4, 4
   dropout: 25%
   epoch: 20
   early stop patience: 2
   output layer activation function: sigmoid
   
   accuracy: 0.9524
   
version 2가 가장 높은 성능을 
