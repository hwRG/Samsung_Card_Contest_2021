# Samsung Card Contest 2021


## Introduction 

- 삼성카드 제 2회 데이터분석 공모전<br>

  

- 삼성카드 이용 고객의 리뷰에 대한 멀티 카테고리 예측<br>
  (ex. 상담하려고 기다리는 시간이 너무 길다 → 불만>고객서비스>상담시스템)<br>

  
  
- 본선 진출 (약 15~20 팀 선정)<br>

  
  
- [상세 설명 바로가기](https://github.com/hwRG/Samsung_Card_Contest_2021/blob/main/Track1_%EB%9E%8C%EC%A7%80%ED%8C%80_%EB%AA%A8%EB%8D%B8%EA%B8%B0%ED%9A%8D%EC%84%9C.pdf)

  <br><br>



## Data Preprocessing

#### 1. 구간별로 문장 자르기

- 복잡한 문장을 구체적인 규칙에 따라 나누기
  (ex. 니다_ 고_ 하고_  .. →  Divide the sentence)<br><br>

#### 2. 불필요한 요소 제거

- 모든 데이터셋(문장) 대한 파이썬의 replace 함수로 불필요한 요소(, . ; 등) 제거<br>

  

#### 3. 오타 감지 및 수정

- 키보드 자판에서 자음과 모음의 위치를 감안하여 두 음절로 나눈 단어의 좌표를 설정<br>![keyboard_weight](/assets/keyboard_weight.png)
  

  <br>

- 키보드 자판으로 설정된 단어 중 빈도수가 낮은 단어는 오타로 인식 <br>

- KNN(K-NeighborsClassifier) 알고리즘으로 주변의 세 단어(K = 3) 중 빈도수가 높은 두개의 음절로 대체<br>

  

#### 4. 핵심 피쳐 선별<br>

![feature_importance](/assets/feature_importance.png)<br>

- 위 그림의 순서에 따라 feature 선별 진행<br>

<br><br>

## Model Training and Evaluation

#### 1. 3개의 카테고리로 나뉘어 진행<br>

- **First Category**<br>
  칭찬 / 불만<br>
- **Second Categories**<br>
  상담 고객 서비스 / 삼성카드 관련 / 기타<br>
- **Third Categories**<br>
  상담원, 상담 시스템 (고객 서비스) / 혜택, 커뮤니티 서비스 등 (15개 삼성카드 카테고리)<br><br>

위 3가지 카테고리로 나누어 각각 트레이닝 진행<br><br>

#### 2. 학습 데이터 Train / test 나누기<br>

- test_size = 0.25<br>
- shuffle = True<br>
- random_state = 1228<br><br>

#### 3. Sklearn을 활용한 전통적인 머신러닝 알고리즘 사용<br>

- SVM<br>
- LightGBM<br>
- XGBoost<br>
- **CatBoost**<br><br>



## Prediction for Test set<br>

#### 1. 테스트셋 전처리<br>

#### 2. 여러 모델을 조합하여 결과 예측<br>

#### 3. 3개로 나뉜 예측값 결합<br>

#### 4. 데이터 후처리 <br><br>
