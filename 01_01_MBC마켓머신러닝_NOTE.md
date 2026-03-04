# 데이터 준비
```
bream_length = [...]
bream_weight = [...]
```
**역할**
- “도미” 클래스의 원시 데이터를 리스트로 준비
- 머신러닝은 “학습할 재료(훈련 데이터)”가 먼저 필요함. 이 단계가 전처리 전의 원천 데이터.
  
---

# 데이터 시각화 (산점도)
```
import matplotlib.pyplot as plt
plt.scatter(bream_length, bream_weight)
plt.xlabel("length")
plt.ylabel("weight")
plt.show()
```
**역할**
- 길이(x)–무게(y)의 관계를 점으로 찍어서 데이터 분포 확인
- 숫자만 보면 “패턴/군집/이상치”를 놓치기 쉬움 → 산점도는 **분류 가능성(클래스가 분리되는지)**을 직관적으로 확인하는 가장 빠른 방법
  
---

# 빙어 데이터 추가 + 시각화
```
smelt_length = [...]
smelt_weight = [...]

plt.scatter(bream_length, bream_weight)
plt.scatter(smelt_length, smelt_weight)
plt.show()
```
**역할**
- 두 클래스(도미/빙어)를 한 그래프에 표시
- “분류가 가능한 문제인지”를 확인하려면 클래스 간 분리도를 봐야 함 | 겹치면 난이도 ↑ (정규화/다른 특징/다른 모델 필요)

---

# 입력(x)만들기 : 길이, 무게를 한 샘플로 묶기
```
fish_data = [[l, w] for l, w in zip(bream_length, bream_weight)] \
          + [[l, w] for l, w in zip(smelt_length, smelt_weight)]
```
또는 
```
import numpy as np
fish_data = np.column_stack((fish_length, fish_weight))
```
**역할**
- 모델이 학습할 입력 특성(feature) 행렬 X 생성
- 머신러닝 모델은 “특성 벡터(길이, 무게)” 단위로 학습함 → 리스트 2개를 그대로 주면 학습 구조가 깨짐
  
---

# 정답(y)만들기 : 도미=1, 빙어=0 같은 라벨
```
fish_target = [1]*len(bream_length) + [0]*len(smelt_length)
```
**역할**
- 지도학습의 정답(타깃) 벡터 y 생성
- KNN 분류는 “가까운 이웃들의 라벨이 뭐냐”를 보고 예측함 → 라벨이 있어야 학습/평가가 가능

---

# 중요) 훈련/테스트 분리
```
from sklearn.model_selection import train_test_split

train_input, test_input, train_target, test_target = train_test_split(
    fish_data, fish_target, stratify=fish_target, random_state=42
)
```
**역할**
- 학습용/평가용 데이터 분리
- 학습에 쓴 데이터로 성능을 재면 “외운 성능”이 나옴 → 새 데이터에서 성능을 보려면 테스트셋이 필수
- `stratify=...` 이유: 클래스 비율(도미/빙어)을 훈련·테스트에 비슷하게 유지해서 평가가 왜곡되지 않게 함

---

# 모델 생성 + 학습(fit)
```
from sklearn.neighbors import KNeighborsClassifier

kn = KNeighborsClassifier()
kn.fit(train_input, train_target)
```
**역할**
- KNN 분류 모델 생성 후 훈련 데이터로 “이웃 구조”를 준비
- KNN은 전통적인 의미의 “가중치 학습”은 없지만, fit()으로 훈련 데이터를 기억하고 거리 계산 준비를 함

---

# 점수 확인(score)
```
kn.score(test_input, test_target)
```
**역할**
- 테스트 정확도 계산
- “현재 모델이 실제로 분류를 잘하는지”를 수치로 확인해야 다음 개선(정규화/k값 조절)이 가능

---

# 예측(predict)으로 새 샘플 분류
```
kn.predict([[30, 600]])
```
**역할**
- 길이 30cm, 무게 600g 같은 새 샘플의 클래스 예측
- 우리가 진짜 하고 싶은 건 “현장에서 들어오는 생선이 도미냐 빙어냐” 같은 실전 추론(inference)

---

# 정규화가 필요한 이유 
도미/빙어 문제에서 흔한 함정:

- 길이: 10~40 (범위 작음)
- 무게: 10~1000 (범위 큼)
KNN은 “거리”를 쓰니까, 무게가 거리 계산을 지배해버림 → 길이 정보가 묻힘.
  
```
from sklearn.preprocessing import StandardScaler

ss = StandardScaler()
ss.fit(train_input)

train_scaled = ss.transform(train_input)
test_scaled  = ss.transform(test_input)

kn.fit(train_scaled, train_target)
kn.score(test_scaled, test_target)
```
**역할**
- 길이/무게의 스케일을 맞춰 “거리 계산이 공정”해지게 함
- KNN/클러스터링처럼 거리 기반 알고리즘은 스케일링이 성능을 좌우함
