# ESG 등급 투자 효과 확인

비재무적 지표인 ESG 등급이 투자 지표로써 활용될 수 있는가를 분석해보려고 한다.



## 데이터

####  수집한 데이터

- ESG 등급 : ESG포탈과 한국기업지배구조원(KCGC)에서 셀레니움 활용 크롤링
- 재무제표 :  금감원에서 OpenAPI 및 크롤링 활용
- 시가총액 : krx 정보데이터시스템에서 셀레니움 활용 크롤링
- 주식 데이터 : yfinance 패키지를 이용해 수집

#### 모델에 사용되는 변수

- ESG 등급 : 각 등급별로 점수 부여(A+ ~ D => 6 ~ 1)

- ROA : 당기순이익 / 총자산(부채+자본) * 100
  
- ROE : 당기순이익 / 총자본(자산-자본)
  
- LEV(부채 비율) = 총부채 / 총자산(부채+자본)

- SIZE(기업규모) = 총자산의 자연 로그 값

- OCF(영업현금흐름) = 영업활동으로 인한 현금흐름/총자산

- CAPEX(자본적 투자금액) = 자본투자 / 총자산(부채+자본)

- 누적 수익률

### 프로젝트 수행 방법

1. 취합한 데이터를 바탕으로 다중 회귀분석 수행
2. 유의한 변수에 대해서 분산 분석 수행
3. 분산 분석에서 유의미한 결과를 보여준 변수에 대해서 사후 검증 분석 실시
