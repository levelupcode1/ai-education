# 파트 3 - Cursor AI에서 Flutter로 실제 작동하는 광고 시스템 구현하기

<!-- 이 문서는 파트 3의 두 번째 강의 교재입니다. -->

## 학습 목표
- 모바일 앱에 광고 시스템을 도입하는 전체 과정을 이해한다.
- Google AdMob을 활용한 광고 연동 실습을 경험한다.
- 광고 수익 극대화를 위한 배치 전략을 익힌다.

## 1. 광고 시스템의 기본 개념
앱 내 광고는 무료 앱에서 가장 널리 쓰이는 수익화 방식입니다. 광고 플랫폼(예: Google AdMob)을 연동하면, 앱 사용자가 광고를 볼 때마다 수익이 발생합니다. 광고는 배너, 전면, 보상형 등 다양한 형태로 제공되며, 각 방식마다 수익과 사용자 경험에 미치는 영향이 다릅니다.

## 2. Google AdMob 소개
- Google에서 제공하는 대표적인 모바일 광고 플랫폼
- 다양한 광고 유형(배너, 전면, 보상형 등) 지원
- Flutter와의 연동이 쉬움
- 광고 단위별로 수익 및 통계 확인 가능

## 3. Flutter 앱에 AdMob 연동하기: 실습 단계
### 1단계: AdMob 계정 생성 및 앱 등록
- [https://admob.google.com/](https://admob.google.com/)에서 계정 생성
- 새 앱 등록 후 광고 단위 ID 발급

### 2단계: Flutter 프로젝트 준비
- Flutter 프로젝트 생성 또는 기존 프로젝트 오픈
- pubspec.yaml에 광고 패키지 추가
  ```yaml
  dependencies:
    google_mobile_ads: ^3.0.0
  ```
- 패키지 설치: `flutter pub get`

### 3단계: Cursor AI 프롬프트로 광고 코드 생성
- Cursor AI에 아래와 같이 프롬프트 입력
  ```
  Flutter 앱에 Google AdMob 배너 광고를 추가하는 코드를 만들어줘. 광고 단위 ID는 'ca-app-pub-xxxxxxxxxxxxxxxx/xxxxxxxxxx'로 넣어줘.
  ```
- 생성된 코드를 main.dart에 복사/붙여넣기

### 4단계: 광고 단위 ID 적용 및 테스트
- 실제 발급받은 광고 단위 ID로 교체
- 에뮬레이터 또는 실제 기기에서 앱 실행 후 광고 노출 확인

## 4. 광고 배치 전략
- 사용자 경험을 해치지 않는 위치 선정(예: 하단 고정 배너)
- 광고 노출 빈도와 수익의 균형 맞추기
- A/B 테스트로 최적의 배치 찾기
- 전면 광고, 보상형 광고는 사용자의 흐름을 방해하지 않는 시점에 노출

## 5. 실습: 간단한 광고 앱 만들기
- Flutter로 기본 앱 생성
- 배너 광고 삽입 코드 예시 제공
- 실제 광고가 노출되는 화면 확인
- Cursor AI 프롬프트 예시:
  ```
  Flutter 앱에서 버튼을 누르면 전면 광고가 뜨도록 코드를 만들어줘. 광고 단위 ID는 'ca-app-pub-xxxxxxxxxxxxxxxx/xxxxxxxxxx'로 해줘.
  ```

---
<!-- 강의 교재 끝 --> 