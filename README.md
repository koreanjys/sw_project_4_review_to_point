# 쇼핑몰 리뷰를 자연어처리 모델 kobert로 분석하여 수치화(점수로 변환 5점 만점)

## 팀 소개

- 팀장
- 신주용 : 전처리 및 kobert 모델링
- 팀원
- 김현수 : 크롤링 및 웹 구축
- 박은영 : 웹 디자인 및 파워포인트 작성
- 허우영 : 크롤링 및 파워포인트 작성
- 김주환 : 자료조사 및 전처리

## 프로젝트 주제 소개

- 상품 구매시 리뷰 평점을 참고를 하는데, 리뷰를 읽어보면 해당 리뷰의 평점은 높으나 글 자체에는 불만이나 부정적인 상품평인 경우가 많이 있습니다. 고로 평점 자체는 신뢰성이 부족하다고 느끼고, 한 상품의 모든 리뷰를 수치화 하고 평균 점수를 구해서 새롭게 평점을 생성해서 유저에게 보여줍니다.

## 웹 프레임워크

- django

## 크롤링 웹

- Naver API, 네이버 쇼핑몰 리뷰(selenium 기반)

## 사용된 모델

- kobert

## 후기

- 우선 selenium으로 user가 요청하는 즉시 리뷰를 여러개 크롤링 하다보니, 속도나 차단 문제 발생.
- 무거운 kobert모델로 즉시 많은 리뷰들을 분석해서 점수를 user에게 보여주는데 많은 시간 소모. django대신 fastapi를 사용해야 한다고 판단.
- aws 배포과정에서 selenium이 또 발목을 잡았다. ubuntu에서 구글크롬과 같은 웹 브라우저를 설치하고 크롬드라이버를 설치 해 봤지만, 동작하지 않음.
