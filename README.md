<div align="center">
  <img src="https://github.com/Jangrae/img/blob/master/parking.png?raw=true" width="700px" />
  <p><i>신규 임대아파트 주차 수요 예측 데이터 분석 프로젝트</i></p>
</div>

<div align="center">
<table>
  <tr>
    <th>단지코드</th>
    <th>단지명</th>
    <th>총세대수</th>
    <th>지역</th>
    <th>예상차량수</th>
  </tr>
  <tr>
    <td>C0154</td>
    <td>정관신도시휴먼시아1단지</td>
    <td>1533</td>
    <td>부산울산</td>
    <td>1392</td>
  </tr>
  <tr>
    <td>C0352</td>
    <td>대전판암4</td>
    <td>2389</td>
    <td>대전충남</td>
    <td>1241</td>
  </tr>
  <tr>
    <td>C0225</td>
    <td>신안마을 휴먼시아 6단지</td>
    <td>1116</td>
    <td>광주전남</td>
    <td>1070</td>
  </tr>
  <tr>
    <td>C0258</td>
    <td>수원호매실 휴먼시아 8단지 아파트</td>
    <td>1270</td>
    <td>경기</td>
    <td>992</td>
  </tr>
  <tr>
    <td>C0286</td>
    <td>소사뷸 이국마을3단지</td>
    <td>1191</td>
    <td>경기</td>
    <td>903</td>
  </tr>
</table>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-3F4F75?style=for-the-badge&logo=matplotlib&logoColor=white" />
</p>

## 📋 프로젝트 개요

> ***"데이터 기반 주차 시설 최적화를 통한 효율적인 주거 환경 구축"***

본 프로젝트는 OO토지주택공사의 의뢰를 받아 새롭게 건설될 공공 임대 아파트 단지의 등록 차량 수를 예측하는 데이터 분석 프로젝트입니다. KT AIVLE School 2차 미니프로젝트로서, 공공 데이터를 활용해 실제 주차 수요를 정확히 예측함으로써 과대 또는 과소 설계를 방지하고 효율적인 주거 환경을 구축하는 데 기여하고자 합니다.

## 📊 데이터 소개

<table>
  <tr>
    <td><b>분석 대상</b></td>
    <td>공공 임대 아파트 단지 주차 수요</td>
  </tr>
  <tr>
    <td><b>출처</b></td>
    <td>한국토지주택공사, 마이홈포털</td>
  </tr>
  <tr>
    <td><b>활용 데이터</b></td>
    <td>
      • 단지 기본 정보(단지코드, 총세대수, 지역 등)<br>
      • 건물 특성(건물형태, 난방방식, 승강기설치여부 등)<br>
      • 세대 특성(전용면적, 공용면적, 세대수 등)<br>
      • 경제 지표(임대보증금, 임대료 등)<br>
      • 실차량수(목표변수)
    </td>
  </tr>
</table>

## 🛠️ 기술 스택

- **언어**: Python
- **데이터 처리 및 분석**:
  - Pandas: 데이터프레임 조작 및 전처리
  - NumPy: 수치 연산 및 배열 처리
- **데이터 시각화**:
  - Matplotlib: 기본 차트 및 그래프 생성
  - Seaborn: 고급 통계 시각화
- **머신러닝**:
  - Scikit-learn: 데이터 전처리, 모델 학습 및 평가
  - XGBoost: 그래디언트 부스팅 기반 예측 모델
  - LightGBM: 경량 그래디언트 부스팅 프레임워크
- **개발 환경**:
  - Jupyter Notebook: 코드 작성 및 분석 문서화

## 📝 문제 정의

```
❓ 신규 임대아파트 단지의 주차 수요(실차량수)를 정확히 예측하여 효율적인 주차 공간 설계에 기여
```

현실적인 주차 수요 예측이 필요한 이유:
- 법정 주차대수와 실제 필요 주차대수 간의 차이 존재
- 주차원단위법의 한계(인력 조사 오차, 시점 차이로 인한 과대/과소 산정)
- 아파트 단지별 특성에 따라 주차 수요가 크게 달라짐
- 적절한 주차 공간 설계로 자원을 효율적으로 활용

## 📊 분석 방법론

### 1️⃣ 데이터 전처리
- 결측치 처리 및 데이터 정제
- 필요한 변수 추가(준공연도, 총면적, 세대당 평균 면적 등)
- 불필요한 변수 제거(단지명, 단지내주차면수, 준공일자 등)
- 단지별 데이터와 상세 데이터 분리 후 적절한 형태로 집계
- 범주형 변수 가변수화 및 범주 통합

### 2️⃣ 탐색적 데이터 분석
- 단변량 분석: 주요 변수 분포 확인 및 이상치 파악
- 이변량 분석: 변수 간 상관관계 분석 및 실차량수와의 관계 탐색
- 추가 전처리: 범주형 변수 재코딩, 이상치 처리

### 3️⃣ 모델링
- 다양한 알고리즘 적용 및 성능 비교
  - KNN(K-Nearest Neighbors)
  - Decision Tree
  - Random Forest
  - XGBoost
  - LightGBM
  - Linear Regression
- 하이퍼파라미터 최적화
- 데이터 파이프라인 구축
- 모델 평가 및 최종 모델 선정

## 🔍 주요 분석 결과

### ✅ 단변량 분석 결과
- 총세대수, 총면적, 임대료, 임대보증금 데이터에 이상치가 존재함
- 대부분의 건물형태는 계단식으로 구성됨
- 난방방식은 지역난방이 가장 많으며, 승강기는 전체동 설치가 일반적임
- 전용면적은 40-50㎡ 구간이 가장 많이 분포함

### ✅ 이변량 분석 결과
- 상관계수와 산점도를 통해 실차량수와 총면적, 실차량수와 총세대수 간의 뚜렷한 양의 상관관계를 확인함
- T-Test 결과(t 통계량=16.20, p-value=3.24e-44)를 통해 총면적과 실차량수 간의 통계적으로 유의미한 관계를 확인함
- 전용면적 40-50㎡ 구간과 50-60㎡ 구간 세대수도 실차량수와 상관관계가 높음
- 임대보증금 역시 실차량수와 양의 상관관계를 보임
- 준공연도는 실차량수와 뚜렷한, 일관된 관계를 보이지 않음
- 건물형태는 실차량수 예측에 중요한 요소로 작용할 가능성이 있음

### ✅ 모델링 결과
- 다양한 머신러닝 모델들의 성능을 비교한 결과, Random Forest가 가장 우수한 예측 성능을 보임
- GridSearchCV를 통한 하이퍼파라미터 최적화(max_depth: 5, n_estimators: 100) 결과, R² 값이 0.70에서 0.75로 향상됨
- 이상치 제거 실험 결과, 오히려 성능이 0.70에서 0.66으로 저하되어 유의미한 이상치로 판단하고 그대로 유지함
- 변수 추가('세대당 평균 면적' = 총면적/총세대수)를 통해 모델 성능 개선
- 모델 성능 비교(Cross-Validation Score Mean):
  - Linear Regression: R² = 0.39
  - Decision Tree: R² = 0.44
  - KNN: R² = 0.63
  - LightGBM: R² = 0.66
  - XGBoost: R² = 0.68
  - Random Forest: R² = 0.71 (최적화 후 0.75)

## 💡 결론 및 제언

- 임대아파트 단지의 주차 수요(실차량수)는 총세대수와 비례함을 통계적으로 확인함
- T-Test 결과를 통해 총면적과 실차량수 간의 통계적으로 유의미한 관계가 입증됨
- 전용면적 구간에 따른 세대수 분포도 중요한 예측 요소로 작용함
- 경제적 요인(임대보증금, 임대료)과 주차 수요 간의 관계도 유의미함
- 난방방식, 승강기설치여부 등 건물 특성도 예측에 기여함
- 개발된 모델을 통해 각 지역별 예상차량수를 정확히 예측할 수 있음

<b>정책 제언:</b>
1. 법정 주차대수 산정 시 단지별 특성(총세대수, 전용면적 분포, 임대료 수준 등)을 더 세밀하게 고려할 필요가 있음
2. 과대 설계를 방지하여 건설 비용을 절감하고, 과소 설계를 피해 입주민의 주차 불편을 최소화할 수 있는 맞춤형 주차 시설 설계가 필요함
3. 신규 아파트의 주차 수요는 본 모델을 통해 보다 정확히 예측하여 효율적인 주차 공간 설계에 활용할 수 있음

## 📝 프로젝트 배운 점

- 단지별 데이터와 상세 데이터가 혼합된 복잡한 구조의 데이터 처리 방법
- 범주형 변수와 연속형 변수에 대한 적절한 전처리 기법
- 다양한 머신러닝 알고리즘의 성능 비교 및 최적화 방법
- 데이터 파이프라인 구축을 통한 일관된 전처리 및 예측 프로세스 확립
- 데이터 기반 의사결정의 중요성과 실제 비즈니스 문제 해결에 적용하는 방법

## 👨‍💻 참여자 
<div align="center">
  <table>
    <tr>
      <td align="center"><b>구종한</b></td>
      <td align="center"><b>김효연</b></td>
      <td align="center"><b>유현종</b></td>
      <td align="center"><b>이대희</b></td>
      <td align="center"><b>정요한</b></td>
      <td align="center"><b>황은비</b></td>
    </tr>
  </table>
</div>

---

<div align="center">
  <p>본 프로젝트는 KT AIVLE School 2차 미니프로젝트로 진행되었습니다.</p>
  <p>© 2025 KT AIVLE School 6기 미니프로젝트 2차</p>
</div>
