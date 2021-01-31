## Sampling 

> ### 1. Imbalanced Learning (불균형 학습) 개요
- 비정상 거래 탐지와 같은 케이스의 경우, 정상적인 거래 보다는 정상 범위에서 벗어난 것으로 판단되는 거래 기록의 비중이 매우 작음
- 이러한 비정상 거래를 찾아내기 에는 이러한 데이터의 불균형이 중요한 이슈로 작용함


#### 1.1. Over-Sampling

Over-Sampling은 부족한 데이터를 추가하는 방식으로 진행되며, 크게 3가지로 구분
1) 무작위 추출. 단순하게 랜덤하게 부족한 Class의 데이터를 복제하여 데이터셋에 추가
2) 기존 데이터를 단순히 복사하는 것에 그치지 않고, 어떠한 방법론에 의해 합성된 데이터를 생성 ex) SMOTE 
3) 어떤 특별한 기준에 의해 복제할 데이터를 정하고 이를 실행

#### 1.2. Under-Sampling

Over-Sampling과 반대로 Under-Sampling은 정상 데이터의 수를 줄여 데이터셋의 균형을 맞추는 것.
주의해서 사용하지 않으면 매우 중요한 정보를 잃을 수도 있기 때문에 확실한 근거를 바탕으로 사용해야 하는 방법

Under-Sampling의 대표적인 예로는 RUS가 있고, Random Under Sampling을 뜻함 
　
 
 
 　

> ### 2. SMOTE 기법
#### 2.1. SMOTE
Synthetic Minority Oversampling TEchnique
2002년에 처음 등장한 Over-Sampling의 대표적인 알고리즘

#### 2.2. 알고리즘의 원리
Boostrap이나 KNN 모델 기법을 기반으로 함 

1) 소수 데이터 중 1개의 Sample을 선택한다. (기준 Sample) 
2) 기준 Sample과 거리(유클리드 거리)가 가까운 k개의 Sample(KNN)을 찾는다. 
3) 이 k개의 Sample 중 랜덤하게 1개의 Sample을 선택한다. (KNN Sample)
4) 새로운 Synthetic Sample은 아래와 같이 계산한다. 




본 과정을 일정 수 만큼 진행하면 아래 그림과 같이 새로운 합성 데이터가 생성됨을 알 수 있다.
