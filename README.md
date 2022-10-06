지역별 범죄 현황 시각화

출처 : 경찰청 범죄 발생 지역별 통계(공공데이터 포털 사이트)
https://www.data.go.kr/tcs/dss/selectFileDataDetailView.do?publicDataPk=3074462

본인 역할 : 데이터 전처리 및 시각화

1. 전처리

(1)groupby 함수의 sum()메소드를 사용하여, 지역별로 범죄 대분류를 묶고, 범죄 중분류는 drop처리 하였다.

<img src="https://user-images.githubusercontent.com/98728682/194219304-cbd60b44-91dc-4252-8d03-1c04b4ec43d5.PNG" width="620" height="250"> 

(2)filter 함수를 통해 지역별로 나눠진 데이터프레임을 광역시 별로 묶었다.
<img src="https://user-images.githubusercontent.com/98728682/194219847-7e6a58c3-7ba2-404c-b1c2-58a7ae8cefda.PNG" width="620" height="250">
(3)각 지역별 범죄 비율 데이터 만들기 : 인구수에 관한 데이터를 기존 데이터에 합쳤다.(출처:통계청)
<img src="https://user-images.githubusercontent.com/98728682/194219825-4ea475c5-c57f-4d31-b9bb-4bf43e8b07e1.PNG" width="620" height="250">

2. 지도 시각화
(1) 도시 지적도 긋기 & 주요 범죄율 대비 지역별 색깔 넣기(choropleth)
<img src="https://user-images.githubusercontent.com/98728682/194219827-83bbd307-c9cf-4662-a4d9-63fc4f260d0a.PNG" width="220" height="250"><https://user-images.githubusercontent.com/98728682/194219830-1bf99ccf-73ec-456d-ba04-2b7712db2f6a.PNG" width="220" height="250">
(2) 각자 행정 구역별로 마커를 만들었다. : 마커 클릭하면, 각자 행정 구역별로 주요 범죄수가 나오도록 하였다.
<img src="https://user-images.githubusercontent.com/98728682/194219834-81508d02-059b-42e9-a54f-7e00815480a9.PNG" width="320" height="250">

3.범죄 요인별 insight 및 시각화
(1)도시 별 지역별 인구밀도, 지역별 총소득, 경찰관 비율, 대졸자 비율 등에 따른 주요 범죄율과 상관관계를 알아본다. (출처: 서울시 범죄발생의 결정요인 분석과 도시계획적 시사점 등)
<img src="https://user-images.githubusercontent.com/98728682/194219836-9dcad185-1c76-4ebf-be4e-a9232ce899af.PNG" width="320" height="250"><img src="https://user-images.githubusercontent.com/98728682/194219838-bd92692e-82af-4506-b75e-99685e44fd75.PNG" width="320" height="250">

<img src="https://user-images.githubusercontent.com/98728682/194219842-5a3419bf-55fd-4425-9406-9a80d297dca2.PNG" width="320" height="250"><img src="https://user-images.githubusercontent.com/98728682/194219843-964dc98f-8513-493b-9718-62ecbc414cdf.PNG" width="320" height="250">

(2)주요 범죄율과 인구밀도, 지역 총소득, 경찰관 비율, 대졸자 비율 등과의 상관관계를 히트맵으로 알아본다.
<img src="https://user-images.githubusercontent.com/98728682/194219840-5f57c99c-63ff-4a87-9d3b-a2c2048c8342.PNG" width="320" height="250">
