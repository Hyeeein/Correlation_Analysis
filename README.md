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
#### 데이터 마이닝 기법 : 상관관계 분석 사용
-  대표적인 상관계수 구하는 방법: Pearson(피어슨), Kendall(켄달), Spearman(스피어만)
-  이때, 변수가 모두 연속형 변수이므로, **Pearson(피어슨) 상관계수를 사용** & 유의성 검정 & 산포도로 시각화

#### 검색량과 클릭량 사이의 상관관계
* **피어슨 상관계수 검정 결과**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/b582cbe9-10e4-4e0c-9d0c-cefd9c167b1f)

마스크와 나이키 운동화가 1에 가까운 양의 상관관계를 가지고 있음을 확인

P-value의 경우, 아이폰을 제외한 7가지 품목에서 0.01, 0.05의 유의수준에서 유의하다는 것을 확인
따라서, 유의수준 0.05에서도 유의하지 않은 아이폰 품목은 검색량과 클릭량 사이의 상관관계 분석에서 제외

* **실생활 필수품 (물티슈, 마스크, 샴푸, 오메가3)**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/625dbc63-a4d4-4fe6-98a5-748d2f4149fc)

물티슈와 오메가3는 각각 상관계수가 0.5, 0.4으로 검색량과 쇼핑 품목 클릭량 사이에 적당한 상관관계 존재

마스크의 경우, 상관계수가 0.92로 검색량과 클릭량 사이에 강한 상관관계가 있음. <br>
이는 코로나 19로 인해, 마스크를 구매하고자 하는 사람들의 영향도 배제할 수 X

샴푸도 상관계수가 0.77로 상관관계가 높은 편. <br>
주로, 개인이 사용하는 샴푸 브랜드가 있기 때문에, 검색량과 클릭량 사이에 양의 상관관계가 있다고 볼 수 있음

* **사치품 (내셔널지오그래픽 패딩, 나이키 운동화, 포켓몬빵, 아이폰)**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/0d0621c2-cde1-4b1f-8e9d-13407124cfc3)

내셔널지오그래픽은 상관계수가 0.84로 검색량과 클릭량 사이에 강한 양의 상관관계를 가지고 있음. <br>
겨울 시즌에 유행하는 상품인만큼, 분포는 아래에 쏠려 있음.

나이키 운동화는 상관계수가 0.913으로 검색한 사람이 쇼핑 품목을 클릭했다고 볼 수 있을 정도로 강한 상관관계

포켓몬빵은 검색한 만큼 쇼핑 품목을 클릭하지는 않음. 적당한 양의 상관관계 0.55

아이폰은 유의하지 않으므로 분석에 포함하지 않음

#### 검색량과 거래액 사이의 상관관계
* **피어슨 상관계수 검정 결과**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/52d97571-8499-45f1-b7c2-9a980a9bccc0)

피어슨 상관계수를 구한 결과, 검색량과 거래액 사이에 아주 강한 양의 상관관계를 가지고 있는 것은 물티슈와 샴푸 <br>
1에 가까운 양의 상관관계를 가지고 있음을 확인

P-value의 경우, 마스크와 아이폰은 0.05 수준에서 유의. 나머지 품목은 0.01의 유의수준에서도 유의함

따라서, 이 분석에서는 유의수준 0.05로 두고 분석 (제외하는 값 없이 진행)

* **실생활 필수품 (물티슈, 마스크, 샴푸, 오메가3)**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/e97cd953-c4be-4b08-b834-6823fd9e94f4)

물티슈와 샴푸의 생활용품 거래액과의 상관계수는 각각 0.86, 0.77로 강한 양의 상관관계를 이루고 있음

물티슈와 샴푸의 산포도도 우상향하는 모습을 보이기에 검색 키워드를 검색한만큼, 거래액이 증가했다고 볼 수 있음

반면, 마스크와 오메가3의 기타(의료)와의 상관계수는 각각 0.32, 0.47로 중간 정도의 양의 상관관계를 지님 <br>
하지만, 산포도 상으로 분포가 흩어져있거나, 한 줄로 쏠려 있어 상관관계가 있다고 말하기에 명확하지 않음

* **사치품 (내셔널지오그래픽 패딩, 나이키 운동화, 포켓몬빵, 아이폰)**

![image](https://github.com/Hyeeein/Correlation_Analysis/assets/81239567/2911aca3-b345-44c2-b76e-e6e7a6d3b542)

내셔널지오그래픽 패딩의 경우, 검색량과 거래액 사이의 상관계수가 0.50 <br>
하지만, 겨울에 주로 판매되는 의류임을 고려하면, 다른 변수들과 약간 차이가 있음

나이키 운동화의 경우, 분포가 조금 흩어져 완벽하게 상관관계를 가지고 있다고 말하기에 명확하지 않음

포켓몬빵의 경우, 갑자기 신드롬을 일으켰기에 이전까지 상관관계가 없다가, 갑자기 상관이 있어졌을 수도 있음 (0.50)

아이폰은 -0.339로 음의 상관관계를 지님. 즉, 아이폰을 검색한다고해서 사람들이 구매하는 것은 아님

## 5. 결론 및 제언

### 가설 검정 결과
```
1. 필수적으로 필요한 물티슈, 마스크, 샴푸, 오메가3 품목의 경우, 네이버 검색트렌드
   검색량과 관계 없이 네이버쇼핑 클릭량 및 온라인쇼핑 거래액이 일정할 것이다.
```
- 마스크의 경우, 검색량과 네이버쇼핑 클릭량이 높은 상관관계가 있다.
- 물티슈의 경우, 검색량과 온라인쇼핑 거래액이 높은 상관관계가 있다.
- 샴푸의 경우, 검색량과 네이버쇼핑 클릭량, 온라인쇼핑 거래액 모두 높은 상관관계가 있다.

**▷ 오메가3를 제외한, 나머지 3가지 상품은 검색량이 클릭량, 온라인쇼핑 거래액과 상관관계가 있다.**

```
2. 이외에 내셔널지오그래픽 패딩, 나이키 운동화, 포켓몬빵, 아이폰 품목의 경우, 
   네이버 검색트렌드 검색량과 네이버쇼핑 클릭량 및 온라인쇼핑 거래액이 비례할 것이다.
```
- 내셔널지오그래픽 패딩의 경우, 검색량과 클릭량, 온라인쇼핑 거래액에 상관관계가 있다.
- 나이키 운동화의 경우, 검색량과 클릭량은 높은 상관관계가 있다.
- 아이폰은 검색량과 클릭량은 비교할 수 없고, 온라인쇼핑 거래액과는 음의 상관관계를 지닌다.

**▷ 포켓몬빵을 제외한, 나머지 3가지 상품은 검색량이 클릭량, 온라인쇼핑 거래액와 상관관계가 있다.**

### 최종 결론 및 제언
```
검색량과 네이버쇼핑 클릭 수, 그리고 온라인쇼핑 거래액이 완벽하게 관련이 있다고 볼 수는 어렵지만
대체적으로, 상품을 구매하기 전에 위와 같은 행동을 한다는 것을 염두해두면, 앞으로의 상품 판매도 충분히 예측할 수 있다
```

## 6. 참고자료

- [최종 발표자료](https://github.com/Hyeeein/Correlation_Analysis)
