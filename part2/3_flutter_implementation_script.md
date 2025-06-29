# Figma 디자인을 Flutter 코드로 변환하기 - 강의 스크립트

## 인트로 [0:00-0:30]
안녕하세요! 이번 강의에서는 Figma 디자인을 Flutter 코드로 변환해 MBTI 테스트 앱을 구현해보겠습니다. Cursor AI를 활용하면 코딩이 처음이신 분들도 쉽게 따라하실 수 있습니다.

## Flutter 개발 환경 설정 [0:30-3:00]
**[Flutter 설치 화면]**
Flutter는 Google의 크로스 플랫폼 UI 툴킷입니다. flutter.dev에서 SDK를 다운로드하고 설치한 후, `flutter doctor` 명령어로 설정을 확인합니다.

**[VS Code 설치 화면]**
Visual Studio Code와 Flutter, Dart 플러그인을 설치하고, Cursor AI를 함께 활용하겠습니다.

## 프로젝트 생성 [3:00-5:00]
**[터미널 화면]**
`flutter create mbti_test_app` 명령어로 새 프로젝트를 생성합니다. VS Code에서 프로젝트를 열고 기본 구조를 확인해보세요.

## Figma 에셋 가져오기 [5:00-7:00]
**[에셋 관리 화면]**
Figma에서 아이콘, 이미지 등을 내보내 Flutter 프로젝트의 assets/images/ 폴더에 복사합니다. pubspec.yaml 파일에 에셋 경로를 등록하고 `flutter pub get`을 실행합니다.

## 테마 설정 [7:00-10:00]
**[테마 코드 작성]**
lib 폴더에 theme.dart 파일을 만들고 Figma의 색상, 텍스트 스타일을 ThemeData로 정의합니다.

Cursor AI에 "Figma 디자인의 색상과 텍스트 스타일을 Flutter ThemeData로 변환해줘"라고 요청하면 됩니다.

## 공통 위젯 구현 [10:00-13:00]
**[위젯 개발 화면]**
lib/widgets/ 폴더를 만들고 버튼, 카드 등 재사용 컴포넌트를 구현합니다. 

Cursor AI에 "둥근 모서리와 그림자가 있는 커스텀 버튼 위젯을 만들어줘"라고 요청하세요.

## 화면 구현 [13:00-20:00]
**[시작 화면 구현]**
lib/screens/ 폴더에 start_screen.dart, question_screen.dart, result_screen.dart 파일을 만들고 각 화면을 구현합니다.

Cursor AI에 "Figma 디자인의 시작 화면을 Scaffold, Column, Container 등을 사용해 구현해줘"라고 요청합니다.

## 상태 관리 [20:00-25:00]
**[상태 관리 코드]**
lib/models/ 폴더에 question.dart와 mbti_result.dart 파일을 만들어 데이터 모델을 정의합니다.

lib/providers/ 폴더에 mbti_provider.dart 파일을 만들어 질문과 응답을 관리하는 로직을 구현합니다.

## 네비게이션 구현 [25:00-28:00]
**[네비게이션 코드]**
main.dart 파일에서 MaterialApp의 routes 속성을 사용해 화면 간 이동을 설정합니다.

질문 화면에서 다음/이전 버튼으로 질문 간 이동하고, 마지막 질문 후 결과 화면으로 전환하는 로직을 구현합니다.

## 반응형 레이아웃 [28:00-30:00]
**[반응형 디자인 코드]**
MediaQuery와 LayoutBuilder를 활용해 다양한, 기기 크기에 대응하는 UI를 구현합니다.

## 앱 실행 및 테스트 [30:00-31:08]
**[앱 실행 화면]**
완성된 앱을 에뮬레이터나 실제 기기에서 실행해 모든 기능이 제대로 작동하는지 확인합니다.

다음 강의에서는 광고와 인앱 결제 등 수익 기능을 추가하는 방법을 배워보겠습니다.