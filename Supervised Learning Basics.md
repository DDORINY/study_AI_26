# 1단계: 머신러닝 기초

## 📂 포함 노트북
01_01_mbc마켓머신러닝.ipynb
02_01_훈련세트_테스트세트.ipynb
02_02_데이터전처리.ipynb

## 📌 1️⃣ 단계 목표
지도학습(Supervised Learning) 개념 이해
분류(Classification) 문제 해결 방법 학습
훈련 세트 / 테스트 세트 분리 필요성 이해
데이터 전처리(Feature Scaling)의 중요성 학습

## 📌 2️⃣ 사용한 주요 라이브러리
```
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.preprocessing import StandardScaler
```

## 3️⃣ 핵심 명령어 사용법 정리
### 1. 데이터 생성 및 결합
**np.column_stack()**
여러 1차원 배열을 열(column) 기준으로 묶어 2차원 배열 생성
```
fish_data = np.column_stack((fish_length, fish_weight))
```
✔ 입력 데이터(X)를 2차원 특성 행렬로 만들 때 사용
✔ 머신러닝 모델은 2차원 입력을 요구함

---

### 2. 타깃(label) 생성
**np.concatenate()**
두 배열을 이어붙임
```
fish_target = np.concatenate((np.ones(35), np.zeros(14)))
```
✔ 도미 = 1
✔ 빙어 = 0
✔ 분류 문제의 정답 데이터 생성

---

### 3. 훈련/테스트 데이터 분리
**train_test_split()**
```
train_input, test_input, train_target, test_target = train_test_split(
    fish_data, fish_target, random_state=42
)
```
✔ 데이터를 훈련용과 테스트용으로 나눔
✔ random_state는 재현성을 위한 시드값
✔ 모델 성능을 공정하게 평가하기 위해 필수

---

### 4. KNN 분류 모델 생성 및 학습
**KNeighborsClassifier()**
```
kn = KNeighborsClassifier()
kn.fit(train_input, train_target)
```
✔ KNN 알고리즘으로 모델 생성
✔ fit() → 모델 학습

---

### 5. 모델 평가
```
kn.score(test_input, test_target)
```
✔ 테스트 세트 정확도 확인
✔ 과대적합 여부 확인 가능

---

### 6. 데이터 전처리 (스케일 조정)
**StandardScaler()**
```
ss = StandardScaler()

ss.fit(train_input)          # 평균과 표준편차 계산
train_scaled = ss.transform(train_input)
test_scaled = ss.transform(test_input)
```
✔ 특성 간 단위 차이를 제거
✔ 거리 기반 알고리즘(KNN)에서 매우 중요
✔ 반드시 훈련 데이터로만 fit() 수행

---

## 📊 학습 핵심 포인트
### ✅ 1. 훈련/테스트 분리의 중요성

모델은 훈련 데이터로만 학습해야 하며
테스트 데이터는 최종 성능 평가용으로 사용한다.

### ✅ 2. 거리 기반 알고리즘의 특징

KNN은 거리 계산을 기반으로 하기 때문에
특성 간 스케일 차이에 매우 민감하다.

### ✅ 3. 데이터 전처리의 필요성

표준화를 적용하지 않으면 특정 특성이 모델에 과도한 영향을 줄 수 있다.

## 🚀 현재 진행 상태

✔ KNN 분류 개념 이해
✔ train/test 분리 구조 이해
✔ 데이터 스케일 문제 해결 가능
✔ 전처리 적용 후 성능 개선 경험

> 머신러닝 기초 단계 완료
