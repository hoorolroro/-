## 지역별 범죄 현황 시각화

#### *목표* : 본 프로젝트를 통해 각 지역별 범죄 통계와 인구 밀도, 경찰관 비율, 지역 총소득과

#### 어떠한 상관관계를 가지는지 파악한다.

<br/>

#### *출처* : 경찰청 범죄 발생 지역별 통계(공공데이터 포털 사이트)
https://www.data.go.kr/tcs/dss/selectFileDataDetailView.do?publicDataPk=3074462

<br/>

#### *역할*
#### *본인* : 데이터 전처리 및 상관관계 시각화
#### 신엽 : 지도 시각화
#### 기나 : 상관관계 시각화
#### 제근 : 상관관계 시각화
#### 예진 : 데이터 전처리 보조
#### 성민 : 데이터 시각화 및 정리, 취합
#### 지수 : 데이터 전처리 보조


## 1. 데이터 전처리

#### (1) Raw data

<img src="https://user-images.githubusercontent.com/98728682/194224185-f1f8862d-2ebf-4598-87d1-59551074b382.PNG" width="1250" height="260"> 

<br/>

#### (2)groupby 함수의 sum()메소드를 사용하여, 지역별로 범죄 대분류를 묶고, 범죄 중분류는 drop처리 하였다.


<img src="https://user-images.githubusercontent.com/98728682/194227979-2e384364-0dbe-4587-ba32-1f4045d6b3ce.PNG" width="1250" height="260"> 

<br/>

#### (3)filter 함수를 통해 지역별로 나눠진 데이터프레임을 광역시 별로 묶었다.


<img src="https://user-images.githubusercontent.com/98728682/194228815-acf73fb4-ad78-4464-8ac8-aadfdd7dbd80.PNG" width="1250" height="260">

<br/>

#### (4)각 지역별 범죄 비율 데이터 만들기 : 인구수에 관한 데이터를 기존 데이터에 합쳤다.(출처:통계청)


<img src="https://user-images.githubusercontent.com/98728682/194228818-871e90e5-e9d2-4d6c-bdfb-39afc2092bae.PNG" width="1250" height="230">

<br/>

#### (5)각 지역별로 인구밀도, 지역별 총소득, 경찰관 비율, 대졸자 비율 등을 데이터프레임에 넣는다.

#### (출처:통계청, "서울시 범죄발생의 결정요인 분석과 도시계획적 시사점" 등)
<img src="https://user-images.githubusercontent.com/98728682/194243830-9bfa02d7-5f3a-424b-8175-ceae7a149150.PNG" width="1250" height="250">

## 2. Python Folium Library를 사용한 지도 시각화
#### (1) 도시 지적도 긋기 & 주요 범죄율 대비 지역별 색깔 넣기(choropleth)

<img src="https://user-images.githubusercontent.com/98728682/194219827-83bbd307-c9cf-4662-a4d9-63fc4f260d0a.PNG" width="550" height="500"><img src="https://user-images.githubusercontent.com/98728682/194219830-1bf99ccf-73ec-456d-ba04-2b7712db2f6a.PNG" width="550" height="500">

#### (2) 행정 구역별로 마커를 만들었다. 마커를 클릭하면, 각 행정 구역별로 주요 범죄수가 나오도록 하였다.
<img src="https://user-images.githubusercontent.com/98728682/194219834-81508d02-059b-42e9-a54f-7e00815480a9.PNG" width="1200" height="500">

## 3.범죄 요인별 insight 및 상관관계 시각화
### (1)각 지역별 요인과 주요 범죄율의과 상관관계를 알아본다.

<img src="https://user-images.githubusercontent.com/98728682/194219836-9dcad185-1c76-4ebf-be4e-a9232ce899af.PNG" width="1200" height="460"> <img src="https://user-images.githubusercontent.com/98728682/194219838-bd92692e-82af-4506-b75e-99685e44fd75.PNG" width="1200" height="460">

<img src="https://user-images.githubusercontent.com/98728682/194219842-5a3419bf-55fd-4425-9406-9a80d297dca2.PNG" width="1200" height="460"><img src="https://user-images.githubusercontent.com/98728682/194245285-67c889a9-91cc-4c68-8fae-7b051a96e927.png" width="1200" height="460">

#### ● 주요 범죄는 강력 범죄와 절도 범죄, 폭력 범죄를 가리킨다.

#### ● 주요 범죄율과 인구밀도, 경찰관 비율, 대졸자 비율 등과는 양의 상관관계를 나타내었고, 지역 총소득과는 음의 상관관계를 나타내었다.

#### ● 하지만 대졸자 비율에서는 유의미한 양의 상관관계를 찾지 못하였다.

<br/>

### (2)각 지역별 인구밀도와 주요 범죄율과의 트리맵 시각화
<img src="https://user-images.githubusercontent.com/98728682/194219844-f7b07d24-33f6-4307-a1ee-21f63d665e20.PNG" width="1200" height="550">

#### ● 인구밀도에 비해서 제주도가 유난히 주요 범죄율이 높은 것을 볼 수 있다.

#### ● 이것은 제주도의 유동 인구가 다른 지역에 비해 유독 많아서 범죄율이 높은 것으로 파악된다.

<br/>

### (3)주요 범죄율과 인구밀도, 지역 총소득, 경찰관 비율, 대졸자 비율 등과의 상관관계를 히트맵으로 알아보았다.
<img src="https://user-images.githubusercontent.com/98728682/194219840-5f57c99c-63ff-4a87-9d3b-a2c2048c8342.PNG" width="640" height="500">

#### ● 상관관계가 높은(0.5 이상)의 요인은 찾을 수 없었다.
#### ● 주요 범죄율과 가장 상관관계가 높은 요인은 0.38의 상관관계를 가진 인구밀도였다.
