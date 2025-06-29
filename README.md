# 풍력 발전소 효율성 분석

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/imjeasung/Wind-Turbine-Production-Efficiency-Optimization-Analysis/blob/main/wind_turbine.ipynb)
[![NBViewer](https://img.shields.io/badge/render-nbviewer-orange.svg)](https://nbviewer.org/github/imjeasung/Wind-Turbine-Production-Efficiency-Optimization-Analysis/blob/ec33637b44ee295d9b36e0373549b922ab2272a6/wind_turbine.ipynb)

이 프로젝트는 풍력 터빈의 발전 데이터를 분석하여 성능을 평가하고 최적화 방안을 찾는 데이터 분석 프로젝트입니다.

https://www.kaggle.com/datasets/mubashirrahim/wind-power-generation-data-forecasting

## 프로젝트 개요

풍력 터빈이 환경 조건에 따라 얼마나 효율적으로 전력을 생산하는지 분석합니다. 특히 풍속, 풍향, 온도, 습도 등의 요인이 발전량에 미치는 영향을 파악하고, 비정상적으로 낮은 효율을 보이는 시점을 찾아냅니다.

## 분석 내용

### 1. 데이터 탐색
- 5년간(2017-2021) 시간별 발전 데이터 분석 (총 43,800개 데이터)
- 풍속, 풍향, 온도, 습도, 이슬점 등 환경 변수와 발전량 관계 파악

### 2. 성능 곡선 분석
- 풍속별 발전량 평균 및 정상 운영 범위 도출
- 터빈의 표준 성능 대비 실제 성능 비교

### 3. 비효율 탐지
- 통계적 방법으로 비정상적으로 낮은 발전량 구간 식별
- 전체 가동 시간 중 약 1.98%가 비효율 상태로 판별

### 4. 머신러닝 모델 개발
- 환경 조건을 바탕으로 발전량을 예측하는 모델 구축
- 3가지 알고리즘 비교: 선형회귀, SVR, 랜덤포레스트
- 최적 모델로 R² = 0.696 달성

## 주요 발견

- **풍속이 가장 중요한 요인**: 발전량의 약 85% 설명력
- **풍향의 영향**: 특정 방향에서 더 높은 발전 효율 확인
- **온도와 습도**: 발전량에 미미하지만 일정한 영향
- **비효율 패턴**: 충분한 풍속에도 불구하고 낮은 발전량을 보이는 시점 존재

## 실용적 활용

이 분석 결과는 다음과 같이 활용할 수 있습니다:

- 터빈 점검 시기 결정을 위한 조기 경고 시스템
- 발전량 예측을 통한 전력 생산 계획 수립
- 터빈 배치 및 운영 최적화 전략 수립

## 파일 구성

- `wind_turbine.ipynb`: 전체 분석 과정과 결과를 담은 주피터 노트북
- `Location1.csv`: 분석에 사용된 풍력 발전 데이터

## 데이터 설명

분석에 사용된 데이터는 다음 변수들을 포함합니다:

- **Time**: 측정 시간 (시간별)
- **temperature_2m**: 지상 2m 온도 (°C)
- **relativehumidity_2m**: 지상 2m 상대습도 (%)
- **dewpoint_2m**: 지상 2m 이슬점 (°C)
- **windspeed_10m/100m**: 지상 10m/100m 풍속 (m/s)
- **winddirection_10m/100m**: 지상 10m/100m 풍향 (도)
- **windgusts_10m**: 지상 10m 돌풍 속도 (m/s)
- **Power**: 터빈 발전량 (정규화된 값)

## 기술 스택

- **Python**: 데이터 분석 및 머신러닝
- **pandas**: 데이터 처리
- **matplotlib, seaborn**: 데이터 시각화
- **scikit-learn**: 머신러닝 모델링
- **numpy**: 수치 계산

## 노트북 실행

```bash
jupyter notebook wind_turbine.ipynb
```

노트북을 실행하기 전에 필요한 라이브러리를 설치해주세요:

```bash
pip install pandas matplotlib seaborn scikit-learn numpy
```

### 온라인에서 바로 실행
위의 "Open in Colab" 버튼을 클릭하면 Google Colab에서 바로 노트북을 실행할 수 있습니다.
