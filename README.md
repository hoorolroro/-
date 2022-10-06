지역별 범죄 현황 시각화

출처 : 경찰청 범죄 발생 지역별 통계(공공데이터 포털 사이트)
https://www.data.go.kr/tcs/dss/selectFileDataDetailView.do?publicDataPk=3074462

본인 역할 : 데이터 전처리 및 시각화

1. 전처리

(1)groupby 함수의 sum()메소드를 사용하여, 지역별로 범죄 대분류를 묶고, 범죄 중분류는 drop처리 하였다.



(2)filter 함수를 통해 지역별로 나눠진 데이터프레임을 광역시 별로 묶었다.

(3)각 지역별 범죄 비율 데이터 만들기 : 인구수에 관한 데이터를 기존 데이터에 합쳤다.(출처:통계청)


2. 지도 시각화
(1) 각자 행정 구역별로 마커를 만들었다. : 마커 클릭하면, 각자 행정 구역별로 주요 범죄수가 나오도록 하였다.

(2) 도시 지적도 긋기 & 주요 범죄율 대비 지역별 색깔 넣기(choropleth)


3.범죄 요인별 insight 및 시각화
(1)도시 별 지역별 인구밀도, 지역별 총소득, 경찰관 비율, 대졸자 비율 등에 따른 주요 범죄율과 상관관계를 알아본다. (출처: 서울시 범죄발생의 결정요인 분석과 도시계획적 시사점 등)
