# study_AI_26 (branch: 01)

> NumPy / Matplotlib 학습 노트 정리 & 진행 로그  
> 목표: “학습 기록형(공부 과정 중심)”으로 누적

---

## 학습 진행 로그

### ✅ Day 1 — NumPy 기초 (numpy.ipynb)
- 파일: [`numpy.ipynb`](./numpy.ipynb)
- 학습 목표
  - [x] ndarray 구조 이해
  - [x] 배열 생성 방법 (list/tuple → np.array 등)
  - [x] dtype 개념 / 자료형 지정 (int8, i1 등)
  - [x] 1D/2D/3D 배열 다루기
  - [x] 리스트 vs ndarray 연산 차이 (벡터화)
  - [x] 기본 집계 함수 맛보기 (sum, mean 등)
  - [ ] 인덱싱 & 슬라이싱 정리 보강
  - [ ] 브로드캐스팅 원리 예제 추가
  - [ ] reshape / transpose 구조 변환 예제 추가

- 실습 체크포인트
  - [x] `np.array()`로 배열 생성
  - [x] `dtype` 확인/지정
  - [x] 기본 연산(+, *, /) 벡터화 체감
  - [x] `np.sum`, `np.mean`으로 집계

- 메모 / 느낀 점
  - (여기에 오늘 배운 핵심 3줄 요약)
  - (헷갈린 개념 / 내일 보완할 내용)

---

### ✅ Day 2 — Matplotlib 기초 + Titanic 시각화 (Matplotlib.ipynb)
- 파일: [`Matplotlib.ipynb`](./Matplotlib.ipynb)
- 학습 목표
  - [x] Matplotlib 기본 개념 이해 (figure/axes 감 잡기)
  - [x] 기본 그래프 생성 (line 중심)
  - [ ] 다양한 그래프 생성 (bar / hist / scatter 등) 정리
  - [ ] 그래프 스타일 및 옵션(제목/라벨/범례/간격/색 등) 정리
  - [ ] Titanic 데이터 기반 시각화 미니 실습 정리

- 실습 체크포인트
  - [x] `plt.plot()` 기본 사용
  - [ ] `plt.title()`, `plt.xlabel()`, `plt.ylabel()` 옵션 정리
  - [ ] `plt.legend()` 범례 처리
  - [ ] `plt.subplot()` / `plt.suptitle()` / `tight_layout()` 레이아웃 정리
  - [ ] 스타일 적용(`color`, `linewidth`, `marker`, `grid` 등)

- 메모 / 느낀 점
  - (여기에 오늘 배운 핵심 3줄 요약)
  - (헷갈린 개념 / 내일 보완할 내용)

---

## 다음에 할 일 (Backlog)
- [ ] NumPy: 브로드캐스팅/마스킹/boolean indexing 예제 추가
- [ ] NumPy: reshape/transpose/axis 개념 정리 + 그림으로 설명
- [ ] Matplotlib: subplot + suptitle + tight_layout 충돌 케이스 정리
- [ ] Titanic: “성별/등급별 생존율” 그래프 2~3개로 정리

---

## 규칙 (내가 보기 좋게)
- 노트북 1개 끝날 때마다 README 로그에 **체크 + 3줄 요약** 남기기
- 코드 블록은 “최소 예제”만, 나머지는 bullet로 설명
