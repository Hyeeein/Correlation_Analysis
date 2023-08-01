# Search Keywords & On-line Shopping Correlation

### 2022-2학기 인천대학교 컴퓨터공학부 빅데이터입문 Term Project 💫

* 주제: 포털사이트 검색 키워드와 실제 온라인 쇼핑 구매 품목 사이의 상관관계
* 기간: 2022.09.15 ~ 2022.11.24
* 참여 인원: 박혜인

## 1. 프로젝트 배경 및 목표
* 프로젝트 배경
  - 인터넷 이용자 수 증가 및 온라인 쇼핑 플랫폼의 활성화 & 거래액 증가
  - 생필품의 경우에도 온라인으로 구매하는 경우가 많아짐

* Question
```
실제로 관심을 많이 가지는 품목과 실제로 구매하는 품목 사이에 관련이 있는가?
```

* 프로젝트 목표 : 사람들이 실제로 관심 있게 검색하는 상품과 구매하는 상품 사이에 차이가 있는지 확인

## 2. 연구대상 선정 및 가설 설정
* '네이버 데이터랩' 쇼핑인사이트 분야별 인기검색어 중 8가지 품목 선정

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/c10b446a-84b2-41e7-82c3-ce2bb2228521)

* 가설 설정
```
1. 필수적으로 필요한 물티슈, 마스크, 샴푸, 오메가3 품목의 경우, 네이버 검색트렌드
   검색량과 관계 없이 네이버쇼핑 클릭량 및 온라인쇼핑 거래액이 일정할 것이다.

2. 이외에 내셔널지오그래픽 패딩, 나이키 운동화, 포켓몬빵, 아이폰 품목의 경우, 
   네이버 검색트렌드 검색량과 네이버쇼핑 클릭량 및 온라인쇼핑 거래액이 비례할 것이다.
```

## 3. 데이터

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/46b3c8fd-d5ec-496e-87aa-67a1cad1bb15)

## 4. 데이터 마이닝
### (1) EDA
* 각 품목 검색량에 대한 시계열 그래프

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/207f8c98-acec-4e33-9179-71fe61c56116)

* 네이버쇼핑 각 품목 클릭량에 대한 시계열 그래프

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/e4687b82-9272-4065-8125-3d0fb7ff28b0)

* 온라인쇼핑몰 상품군별 거래액 시계열 그래프

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/f41ad2ee-fc7c-4e97-9df5-ba8d6317b98b)

코로나 19 이후, **음식료품의 온라인쇼핑 거래액이 증가**함

**의복**의 경우, 상대적으로 **단가가 비싼 겨울 의상을 구매**할 때 **온라인쇼핑 거래액 증가** <br>
이외에도 가전/전자/통신기기, 생활용품도 온라인으로 구매하는 경우가 점차 증가하고 있음

### (2) Correlation



## 5. 결론 및 제언

## 6. 참고자료

- [최종 발표자료](https://github.com/Hyeeein/Correlation_Analysis)
