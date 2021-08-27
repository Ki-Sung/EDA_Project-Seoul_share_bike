# EDA_Project-Seoul_share_bike

- 프로젝트 목적: 서울시 공공포털 "**2020 서울시 공공 자전거 이용 현황**" 데이터를 바탕으로 코로나 시국 서울 공공 자전거 이용량 탐색 및 분석
- 데이터: kaggle의 [인도 중고차 예측하기](https://www.kaggle.com/avikasliwal/used-cars-price-prediction) 데이터셋
- 프로젝트 기간: 2021.03.26 ~ 2021.04.21
- 최종 발표일: 2021.04.21
- 발표자: 김기성
- [프로젝트 발표 프레젠테이션](https://docs.google.com/presentation/d/1z0IVpmXbb7BUQRCvyXT9ASFUfEokY6FSLG_8pjfrLQA/edit#slide=id.p)
- 팀원: 
  - [송강](https://github.com/rivels): 데이터 파악 후EDA, 발표자료에 사용할 그래프 구상
  - [김기성](https://github.com/Ki-Sung): 데이터 이해를 위해 탐색, 흩어진 12개의 데이터 하나로 정리, EDA
- 첨삭: 
  - [박두진 강사님](https://github.com/radajin)
  - [정현석 클래스 매니저님](https://github.com/FLY-CODE77)
 - 사용언어 및 패키지
  - [![Python Badge](http://img.shields.io/badge/-Python%20-blue?style=flat-square&&logoColor=yellow&logo=python&link=https://www.python.org/)](https://www.python.org/) [![Pandas Badge](http://img.shields.io/badge/-Pandas%20-blue?style=flat-square&&logoColor=yellow&logo=pandas&link=https://pandas.pydata.org/)](https://pandas.pydata.org/) [![Matplotlib Badge](http://img.shields.io/badge/-Matplotlib%20-blue?style=flat-square&&logoColor=yellow&logo=matplotlib&link=https://matplotlib.org/)](https://matplotlib.org/) [![Seaborn Badge](http://img.shields.io/badge/-Seaborn%20-blue?style=flat-square&&logoColor=yellow&logo=seaborn&link=https://seaborn.pydata.org/)](https://seaborn.pydata.org/)

## 개요 1
```
- 등/하원때마다 성수역 앞의 따릉이가 쌓여있는것을 보고 따릉이를 필요한곳에 더, 반납이 많은곳엔 덜 배치해서 따릉이의 이용률을 더 높힐 수 있을까? 라는 의문점에서 출발.

- 대여소 번호가 많은 순으로 랭킹을 선정해서 수요가 가장 많았던 스테이션을 추려내고
- 반대로 반납 대여소를 카운트해서 가장 많았던 스테이션도 추려내서

- 수요가 많은 곳에는 따릉이를 더 배치하고, 반납이 많았던 곳에는 따르이 배치를 덜 해서 효율성과 경제성을 도모 할 수 있는 인사이트 제시  
 ```
  
## 개요 2
~~~
- 코로나팬대믹 이후로 사람들은 따릉이를 더 탈까 덜 탈까?
- 재택근무의 확대로 유동자체가 적어져서 따릉이 이용 횟수가 적어졌을까?
- 아니면 팬대믹으로 대중교통 이용에 불안감이 조성되어 따릉이로 출퇴근을 해서 더 많아졌을까? 라는 궁금점에서 출발.

* 7월과 8월의 비교
1. 19년도 7월과 20년도 7월의 이용량 비교 (코로나의 영향이 있는지)
2. 위 지표들간의 이용시간의 차이, 이용거리의 변화도 있는지 확인.
~~~

### extra)
- 풍속, 가시거리, 미세먼지, 초미세먼지, 강수여부, 요일, 휴일여부 등에 대한 수치들을 수집해서 모델링 후 따릉이 수가 부족할것으로 예상되는곳, 따릉이의 반납이 집중될 곳을 예측

- 계절별, 시간대별 분류
신형따릉이 구형따릉이 미니따릉이에 대한 이용분석
  
        
## 활용 데이터
~~~
- 2019년 7월,8월 & 2020년 7월,8월의 따릉이 이용 데이터 활용  

- 지역 : 서울시 마포구  
  ~~~
  
### 따릉이 이용내역 데이터에서 사용할 column : 자전거번호, 대여일시, 대여 대여소번호, 대여소 이름, 반납일시, 반납대여소번호, 반납대여소이름, 이용시간, 이용거리
~~~
- 따릉이 이용내역 데이터 칼럼 설명  

- bicycle_type : 자전거 타입(1 : 일반,2 : QR,3 : 새싹)  

- rental_day : 대여 날짜

- rental_time : 대여 시간  

- return_day : 반납 날짜

- return_time : 반납 시간

- station_num : 대여소 번호

- station_name : 대여소 이름 

- return_station_num : 반납대여소 번호  

- return_station_name : 반납대여소 이름

- using_time : 이용시간  

- using_distance : 이용거리
  ~~~
### station 데이터에서 사용할 column : 대여소번호, 보관소(대여소)명, 소재지, longitude, latitude  
~~~
- 대여소 데이터 칼럼 설명  

- station_num : 대여소번호  

- station_name : 대여소이름  

- gu : 소재지(ex: 성동구)  

- latitude : 위도  

- longitude : 경도  
~~~
