## 🏆 AIFactory 쳔연가스 소비 예측 - 3st Place Solution
![Python](https://img.shields.io/badge/Python-3.8-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Success-green)

## Introduction
- 민간/산업용 장기 천연가스 소비 예측 모델을 개발하는 task

## Dataset
- 민간/산업용 천연가스 소비 데이터
- 기후 데이터 (온도, 습도 등)
- 경제 데이터 (GDP, 월별 수출입 등)
- 기타 데이터 (인구, 음의 북극진동 등)

## CV Strategy
- 가장 마지막 년도의 4개의 분기를 각각 검증기간으로 간주하여 4-CV 검증시스템을 구축

## Preprocessing & Feature Engineering
- Sin(x), Cos(x) 연산을 통해 시간 데이터를 주기성 데이터로 변환
- 2015년도를 기준으로 정규화한 경제 데이터 사용 (인플레이션 normalizing)

## Modeling
- 민간용 - 최근 3년치 월별 소비량 평균
- 산업용 - ElasticNet/랜덤포레스트/LightGBM/XGBoost/CatBoost/KNN/MLP 7개 모델 예측치 가중평균

![image](https://github.com/user-attachments/assets/c4902b2b-5de2-45c8-9628-928bcf54316c)

## Core Strategy
### Ensemble by Timestep
- 추론 시, 최근 timestep만을 이용하여 예측하는 것이 아닌 그 이전 timestep도 함께 활용하여 예측 성능을 올리는 기법을 사용

![image](https://github.com/user-attachments/assets/b919ff5c-d701-4283-bf5c-ba70b9ca103d)
