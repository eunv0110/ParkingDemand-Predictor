# 🚗 신규 임대아파트 주차 수요 예측 프로젝트

<div align="center">
  <img src="https://github.com/Jangrae/img/blob/master/parking.png?raw=true" width="700px" />
  <br><br>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-3F4F75?style=for-the-badge&logo=matplotlib&logoColor=white" />
  <br><br>
  <p><i>KT AIVLE School 6기 미니프로젝트 2차</i></p>
</div>

<br>

## 📋 프로젝트 개요

<div align="center">
  <h3><i>"데이터 기반 주차 시설 최적화를 통한 효율적인 주거 환경 구축"</i></h3>
</div>

<br>

본 프로젝트는 OO토지주택공사의 의뢰를 받아 새롭게 건설될 공공 임대 아파트 단지의 등록 차량 수를 예측하는 데이터 분석 프로젝트입니다. 공공 데이터를 활용해 실제 주차 수요를 정확히 예측함으로써 과대 또는 과소 설계를 방지하고 효율적인 주거 환경을 구축하는 데 기여하고자 합니다.

<br>

## 📝 문제 정의

```
❓ 신규 임대아파트 단지의 주차 수요(실차량수)를 정확히 예측하여 효율적인 주차 공간 설계에 기여
```

<br>

### 현실적인 주차 수요 예측이 필요한 이유:

- 🔹 법정 주차대수와 실제 필요 주차대수 간의 차이 존재
- 🔹 주차원단위법의 한계(인력 조사 오차, 시점 차이로 인한 과대/과소 산정)
- 🔹 아파트 단지별 특성에 따라 주차 수요가 크게 달라짐
- 🔹 적절한 주차 공간 설계로 자원을 효율적으로 활용

<br>

## 📊 데이터 소개

<table>
  <tr>
    <th align="center" width="20%">분석 대상</th>
    <td>공공 임대 아파트 단지 주차 수요</td>
  </tr>
  <tr>
    <th align="center">출처</th>
    <td>한국토지주택공사, 마이홈포털</td>
  </tr>
  <tr>
    <th align="center">활용 데이터</th>
    <td>
      <ul>
        <li>단지 기본 정보(단지코드, 총세대수, 지역 등)</li>
        <li>건물 특성(건물형태, 난방방식, 승강기설치여부 등)</li>
        <li>세대 특성(전용면적, 공용면적, 세대수 등)</li>
        <li>경제 지표(임대보증금, 임대료 등)</li>
        <li>실차량수(목표변수)</li>
      </ul>
    </td>
  </tr>
</table>

<br>

## 🛠️ 분석 방법론

<div style="display: flex; justify-content: space-between;">
  <div style="width: 30%;">
    <h3>1️⃣ 데이터 전처리</h3>
    <ul>
      <li>결측치 처리 및 데이터 정제</li>
      <li>필요한 변수 추가(준공연도, 총면적, 세대당 평균 면적 등)</li>
      <li>불필요한 변수 제거(단지명, 단지내주차면수, 준공일자 등)</li>
      <li>단지별 데이터와 상세 데이터 분리 후 적절한 형태로 집계</li>
      <li>범주형 변수 가변수화 및 범주 통합</li>
    </ul>
  </div>
  <div style="width: 30%;">
    <h3>2️⃣ 탐색적 데이터 분석</h3>
    <ul>
      <li>단변량 분석: 주요 변수 분포 확인 및 이상치 파악</li>
      <li>이변량 분석: 변수 간 상관관계 분석 및 실차량수와의 관계 탐색</li>
      <li>추가 전처리: 범주형 변수 재코딩, 이상치 처리</li>
    </ul>
  </div>
  <div style="width: 30%;">
    <h3>3️⃣ 모델링</h3>
    <ul>
      <li>다양한 알고리즘 적용 및 성능 비교
        <ul>
          <li>KNN(K-Nearest Neighbors)</li>
          <li>Decision Tree</li>
          <li>Random Forest</li>
          <li>XGBoost</li>
          <li>LightGBM</li>
          <li>Linear Regression</li>
        </ul>
      </li>
      <li>하이퍼파라미터 최적화</li>
      <li>데이터 파이프라인 구축</li>
      <li>모델 평가 및 최종 모델 선정</li>
    </ul>
  </div>
</div>

<br>

## 🔍 주요 분석 결과

<table>
<tr>
  <th width="33%" align="center">📊 단변량 분석</th>
  <th width="33%" align="center">📈 이변량 분석</th>
  <th width="33%" align="center">🤖 모델링 결과</th>
</tr>
<tr>
  <td align="left">
    • 총세대수, 총면적, 임대료, 임대보증금 데이터에 이상치가 존재함<br><br>
    • 대부분의 건물형태는 계단식으로 구성됨<br><br>
    • 난방방식은 지역난방이 가장 많으며, 승강기는 전체동 설치가 일반적임<br><br>
    • 전용면적은 40-50㎡ 구간이 가장 많이 분포함
  </td>
  <td align="left">
    • 실차량수와 총면적, 총세대수 간의 뚜렷한 양의 상관관계 확인<br><br>
    • T-Test 결과(t=16.20, p=3.24e-44)로 총면적과 실차량수 간 유의미한 관계 입증<br><br>
    • 전용면적 40-60㎡ 구간 세대수가 실차량수와 높은 상관관계<br><br>
    • 임대보증금과 실차량수 간 양의 상관관계 확인<br><br>
    • 건물형태가 중요 예측 요소로 작용
  </td>
  <td align="left">
    • Random Forest 모델이 최고 성능 보임<br><br>
    • 하이퍼파라미터 최적화로 R² 값 0.70→0.75 향상<br><br>
    • 이상치 유지가 성능 향상에 기여<br><br>
    • '세대당 평균 면적' 변수 추가로 모델 성능 개선
  </td>
</tr>
</table>

<br>

### 📊 모델 성능 비교 (R²)

<table width="100%">
<tr>
<td width="50%" valign="top">

| 모델 | 성능 지표 |
|------|---------|
| Random Forest | 0.75 ⭐ |
| XGBoost | 0.68 |
| LightGBM | 0.66 |
| KNN | 0.63 |
| Decision Tree | 0.44 |
| Linear Regression | 0.39 |

</td>
<td width="50%" valign="top">

![모델 성능 비교 그래프](https://github.com/user-attachments/assets/cccdf105-3884-4f42-85c9-4ab954777713)

</td>
</tr>
</table>

## 📊 모델 예측 결과

<div align="center">
  <h4>아파트 단지별 예상 차량수 예측 결과</h4>
  <p>총세대수와 지역 등의 특성을 바탕으로 각 단지에 필요한 실제 주차 수요 예측</p>
  <br>
  <table>
    <tr style="background-color: #4472C4; color: white;">
      <th align="center">단지코드</th>
      <th align="center">단지명</th>
      <th align="center">총세대수</th>
      <th align="center">지역</th>
      <th align="center">예상차량수</th>
    </tr>
    <tr>
      <td align="center">C0154</td>
      <td>정관신도시휴먼시아1단지</td>
      <td align="center">1,533</td>
      <td align="center">부산울산</td>
      <td align="center"><b>1,392</b></td>
    </tr>
    <tr>
      <td align="center">C0352</td>
      <td>대전판암4</td>
      <td align="center">2,389</td>
      <td align="center">대전충남</td>
      <td align="center"><b>1,241</b></td>
    </tr>
    <tr>
      <td align="center">C0225</td>
      <td>신안마을 휴먼시아 6단지</td>
      <td align="center">1,116</td>
      <td align="center">광주전남</td>
      <td align="center"><b>1,070</b></td>
    </tr>
    <tr>
      <td align="center">C0258</td>
      <td>수원호매실 휴먼시아 8단지 아파트</td>
      <td align="center">1,270</td>
      <td align="center">경기</td>
      <td align="center"><b>992</b></td>
    </tr>
    <tr>
      <td align="center">C0286</td>
      <td>소사뷸 이국마을3단지</td>
      <td align="center">1,191</td>
      <td align="center">경기</td>
      <td align="center"><b>903</b></td>
    </tr>
  </table>
</div>

<br>

<div align="center">
  <h4>주요 관찰 결과</h4>
</div>

총세대수와 예상차량수 사이에 일반적으로 비례 관계가 있으나, 단순한 비례 관계만으로는 설명할 수 없는 패턴이 존재합니다:

- C0352(대전판암4)의 경우 총세대수가 2,389세대로 가장 많지만, 예상차량수는 1,241대로 세대수 대비 상대적으로 낮음
- 이는 지역적 특성, 대중교통 접근성, 세대 구성 등 다양한 요인이 복합적으로 영향을 미치는 것으로 분석됨

<br>

## 💡 결론 및 제언

<div style="display: flex; justify-content: space-between;">
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>📝 주요 결론</h3>
    <ul>
      <li>임대아파트 주차 수요(실차량수)는 총세대수와 비례관계 확인</li>
      <li>총면적과 실차량수 간 통계적으로 유의미한 관계 입증</li>
      <li>전용면적 구간별 세대수 분포가 주요 예측 요소</li>
      <li>경제적 요인(임대보증금, 임대료)과 주차 수요 간 관계 유의미</li>
      <li>난방방식, 승강기설치여부 등 건물 특성도 예측에 기여</li>
      <li>개발된 모델로 지역별 예상차량수 정확히 예측 가능</li>
    </ul>
  </div>
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>🔍 정책 제언</h3>
    <ol>
      <li>법정 주차대수 산정 시 단지별 특성(총세대수, 전용면적 분포, 임대료 수준 등)을 더 세밀하게 고려할 필요가 있음</li>
      <li>과대 설계를 방지하여 건설 비용을 절감하고, 과소 설계를 피해 입주민의 주차 불편을 최소화할 수 있는 맞춤형 주차 시설 설계가 필요함</li>
      <li>신규 아파트의 주차 수요는 본 모델을 통해 보다 정확히 예측하여 효율적인 주차 공간 설계에 활용할 수 있음</li>
    </ol>
  </div>
</div>

<br>

## 🧠 프로젝트 배운 점

<div align="center">
  <table>
    <tr>
      <td width="30%" align="center">📊<br><b>데이터 처리</b></td>
      <td width="70%">단지별 데이터와 상세 데이터가 혼합된 복잡한 구조의 데이터 처리 방법 습득</td>
    </tr>
    <tr>
      <td align="center">🔄<br><b>변수 처리</b></td>
      <td>범주형 변수와 연속형 변수에 대한 적절한 전처리 기법 적용 경험</td>
    </tr>
    <tr>
      <td align="center">🤖<br><b>모델링</b></td>
      <td>다양한 머신러닝 알고리즘의 성능 비교 및 최적화 방법 습득</td>
    </tr>
    <tr>
      <td align="center">⚙️<br><b>파이프라인</b></td>
      <td>데이터 파이프라인 구축을 통한 일관된 전처리 및 예측 프로세스 확립</td>
    </tr>
    <tr>
      <td align="center">💼<br><b>실무 적용</b></td>
      <td>데이터 기반 의사결정의 중요성과 실제 비즈니스 문제 해결에 적용하는 방법 경험</td>
    </tr>
  </table>
</div>

<br>

## 🛠️ 기술 스택

<div align="center">
  <table>
    <tr>
      <th colspan="2" align="center">분류</th>
      <th align="center">기술</th>
      <th align="center">용도</th>
    </tr>
    <tr>
      <td rowspan="5" width="10%">💻</td>
      <td width="20%"><b>언어</b></td>
      <td width="25%">Python</td>
      <td width="45%">전체 프로젝트 개발</td>
    </tr>
    <tr>
      <td rowspan="2"><b>데이터 처리</b></td>
      <td>Pandas</td>
      <td>데이터프레임 조작 및 전처리</td>
    </tr>
    <tr>
      <td>NumPy</td>
      <td>수치 연산 및 배열 처리</td>
    </tr>
    <tr>
      <td rowspan="2"><b>시각화</b></td>
      <td>Matplotlib</td>
      <td>기본 차트 및 그래프 생성</td>
    </tr>
    <tr>
      <td>Seaborn</td>
      <td>고급 통계 시각화</td>
    </tr>
    <tr>
      <td rowspan="4">🤖</td>
      <td rowspan="3"><b>머신러닝</b></td>
      <td>Scikit-learn</td>
      <td>데이터 전처리, 모델 학습 및 평가</td>
    </tr>
    <tr>
      <td>XGBoost</td>
      <td>그래디언트 부스팅 기반 예측 모델</td>
    </tr>
    <tr>
      <td>LightGBM</td>
      <td>경량 그래디언트 부스팅 프레임워크</td>
    </tr>
    <tr>
      <td><b>개발 환경</b></td>
      <td>Jupyter Notebook</td>
      <td>코드 작성 및 분석 문서화</td>
    </tr>
  </table>
</div>

<br>

## 👨‍💻 참여자 

<div align="center">
  <table>
    <tr>
      <td align="center" width="16.6%"><b>구종한</b></td>
      <td align="center" width="16.6%"><b>김효연</b></td>
      <td align="center" width="16.6%"><b>유현종</b></td>
      <td align="center" width="16.6%"><b>이대희</b></td>
      <td align="center" width="16.6%"><b>정요한</b></td>
      <td align="center" width="16.6%"><b>황은비</b></td>
    </tr>
  </table>
</div>

<br>

---

<div align="center">
  <p>본 프로젝트는 KT AIVLE School 2차 미니프로젝트로 진행되었습니다.</p>
  <p>© 2025 KT AIVLE School 6기 미니프로젝트 2차</p>
</div>
