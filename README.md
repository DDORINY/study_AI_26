# 📊 파이썬 데이터 분석 기초 학습 노트

> 목표: 데이터 분석 기초 체력 만들기  
> 구성: Numpy → Pandas → Matplotlib 순서 학습

---

## 1️⃣ Numpy 기초

📂 파일: numpy.ipynb

### ✔ 학습 내용
- 배열 생성 (np.array, arange, linspace)
- 다차원 배열 구조 이해
- 인덱싱 & 슬라이싱
- 브로드캐스팅
- 기본 연산 (sum, mean, max, min)

### ✔ 핵심 개념 정리
- 리스트 vs ndarray 차이
- 벡터화 연산의 속도 장점
- axis 개념

### ✔ 느낀 점
- 데이터 분석은 배열 구조 이해가 핵심
- 브로드캐스팅은 처음엔 헷갈리지만 매우 중요

---

## 2️⃣ Pandas 기초

📂 파일: pandas.ipynb

### ✔ 학습 내용
- Series / DataFrame 생성
- CSV 파일 읽기 (read_csv)
- head(), info(), describe()
- 컬럼 선택
- 조건 필터링
- 결측치 (NaN) 이해
- 데이터 타입 확인 (dtypes)

### ✔ 실습 데이터
- netflix 데이터
- korea_weather_data.csv (가상 데이터 생성 후 분석)

### ✔ 핵심 개념
- DataFrame은 2차원 테이블 구조
- index 개념 이해 중요
- dtype 확인은 데이터 전처리의 시작

---

## 3️⃣ Matplotlib 시각화

📂 파일: Matplotlib.ipynb

### ✔ 학습 내용
- 기본 그래프 (plot)
- 막대 그래프 (bar)
- 히스토그램 (hist)
- 산점도 (scatter)
- 그래프 꾸미기 (title, xlabel, ylabel)

### ✔ 핵심 개념
- 데이터 → 시각화 흐름 이해
- 축 설정 중요
- 그래프는 데이터 설명 도구

---

# 📌 학습 흐름 요약

Numpy → 데이터 구조 이해  
↓  
Pandas → 데이터 다루기  
↓  
Matplotlib → 데이터 시각화  

---

# 🎯 다음 학습 목표

- 그룹화 (groupby)
- 정렬 (sort_values)
- 데이터 전처리 심화
- Seaborn 시각화
- 기초 통계

---

✍ 공부 방식:
- 직접 코드 작성
- CSV 직접 생성
- 에러 해결 경험 쌓기
