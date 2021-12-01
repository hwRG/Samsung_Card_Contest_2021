# Samsung Card Contest 2021


## Introduction 

- Samsung Card's 2nd Data Analytic  contest 

- Predict multi categories of customer reviews.<br>
  (ex. 상담하려고 기다리는 시간이 너무 길다 → 불만>고객서비스>상담시스템)

- First Pass (Probably 20 teams)

  <br><br>



## Data Preprocessing

#### 1. Divide the complex sentence

- Divide the complex sentence by specific rules.
  (ex. 니다_ 고_ 하고_  .. →  Divide the sentence)<br><br>

#### 2. Remove unnecessary elements

- Remove the unnecessary elements with replace function.

#### 3. Typo Detect and Correction

- Set coordinates of words divided into 2 syllables with weight considering the keyboard vowel position.
- Among the words set as nearby coordinates, words with low frequency are recognized as typos.
- Using the KNN(K-NeighborsClassifier) algorithm, replace it with a two-syllable word with a high frequency among the three surrounding words. (K = 3)

#### 4. Feature Selection

<br><br>

## Model Training and Evaluation

#### 1. Divide into 3 Categories

- First Categories : Compliments / Complaints 
- Second Categories : Customer service / Samsung Card / etc.
- Last Categories : 
  Counselors, Counseling system ( in Customer service ) 
  / Benefits, installment financial products, community services, card use, card products, billing ... (15 categories in SamSung Card)

Learning three categories separately.

#### 2. Train Test split

- test_size = 0.25
- shuffle = True
- random_state = 1228

#### 3. Use Traditional Machine Learning Library (with sklearn)  

- SVM
- LightGBM
- XGBoost
- **CatBoost**<br><br>



## Prediction for Test set

#### 1. Preprocessing the Test set

#### 2. Predict result use each model

#### 3. Combine the predict value

#### 3. Post processing <br><br>
