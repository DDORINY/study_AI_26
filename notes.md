# AI Vision 기술 스택 구조
```
이미지 데이터
     ↓
OpenCV
     ↓
numpy
     ↓
PyTorch
     ↓
CNN 모델
     ↓
결과 시각화
matplotlib
```

# pandas
데이터 테이블 처리 : CSV / 엑셀 같은 표 형태 데이터 분석 <br>

**데이터 처리 라이브러리**<br>
```import pandas as pd```

**주요함수**

- CSV 파일 읽기<br>
```pd.read_csv()```
- 데이터 미리보기<br>
```df.head()``` 상위 5개의 데이터를 미리 볼 수 있다.
- 데이터 통계 확인<br>
```df.describe()```
- 데이터 개수 확인<br>
```df.value_counts()```

---

# numpy
수학계산/ 행렬 계산 : 머신러닝은 대부분 행렬 연산

**수치계산 라이브러리**<br>
```import numpy as np```

**주요함수**

- 배열 생성<br>
```np.array()```
- 평균<br>
```np.mean()```
- 표준편차<br>
```np.std()```
- 랜덤 데이터 생성<br>
```np.random```

---

# matplotlib
데이터 그래프 시각화 : 데이터 패턴을 확인

**시각화 라이브러리**
```import matplotlib.pyplot as plt```<br>

**주요 함수**

- 선 그래프<br>
`plt.plot()`
- 산점도<br>
`plt.scatter()`
- 막대그래프<br>
`plt.bar()`
- 파이그래프<br>
`plt.pie()`
- 영역그래프<br>
`plt.fill_between()`
- 그래프 표시<br>
`plt.show()`

---

# scikit-learn
머신러닝 **대표라이브러리**
`sklearn`

---

# train_test_split
데이터를 훈련 데이터와 테스트 데이터로 분리 
→ 모델의 성능을 객곽적으로 평가

`from sklearn.model_selection import train_test_split`

---

# StandardScaler
데이터 스케일 맞추기 : 값의 차이가 크면 모델의 혼란이 온다. 그래서 평균 0, 표준편차1 로 변환한다.

`from sklearn.preprocessing import StandardScaler`

---

# KNN (K-최근접)
가장 가까운 데이터 기준분류<br>
데이터를 특정 클래스(범주)로 분류<br>
즉, 결과가 카테고리<br>

K 값 : 몇개의 이웃을 참고할지 
투표 : 분류 결정

`from sklearn.neighbors import KNeighborsClassifier`

**사용되는 수학 : 거리계산**
- 유클리스 거리 : 데이터 간 유사도 측정

---

# 로지스틱 회귀
선형결합 → 확률기반 분류 

`from sklearn.linear_model import LogisticRegression`

- 시그모이드함수 : 이진 분류
  → 0~1의 사이의 값을 갖는다.
  
- 소프트맥스 : 다중 분류
  → 각 클래스 확률 계산
  
---

# 경사하강

`SGDClassifier`
경사 하강법은 Loss 최소화하는 것을 목표로 한다. 

**Loss 함수**
- hinge → SVM
- log_loss → 로지스틱
- squared_loss → 회귀

Loss 기울기 계산 → 조금씩 이동 → 최소값 찾기
→ 딥러닝과 구조가 비슷하다. 

---

# DecisionTree (의사결정 트리)
조건문 기반 모델<br>
데이터 분햘 → 불순도 감소

`from sklearn.tree import DecisionTreeClassifier`

**사용되는 함수**
`Gini impurity`<br>
데이터 섞인 정도( 0 → 완전 분리 )

`Entropy`
정보량 계산 

---

# RandomForest (랜덤 포레스트)
여러 결정트리 합쳐서 성능 향상 (앙상블)
여러 DecisionTree → 결과 평균

`Bootstrap sampling` 데이터 랜덤 샘플링

`from sklearn.ensemble import RandomForestClassifier`

---

# cross_val_score (교차검증)
모델을 평가할 때 사용한다. <br>
데이터를 여러 번 나눠서 모델 안정성 평가 

`from sklearn.model_selection import cross_val_score`

---

# GridSearchCV
최적의 모델 파라미터 찾기

`from sklearn.model_selection import GridSearchCV`

```
예)
max_depth
min_samples
```

---

# RandomizedSearchCV
랜덤으로 파라미터 탐색 : GridSearch보다 빠름

`from sklearn.model_selection import RandomizedSearchCV`

---

# 비지도 학습 KMeans (K 평균)
데이터 군집 찾기
```
데이터
→ 중심 계산
→ 반복 이동
```

`from sklearn.cluster import KMeans`

---

# silhouette_score
군집 품질 평가

`from sklearn.metrics import silhouette_score`

---

# PCA 주성분분석
데이터 차원축소 
```
공분산 행렬
↓
고유값
고유벡터
```

`from sklearn.decomposition import PCA`
