# Cursor AI 설치부터 첫 "Hello World" 앱 실행까지! - 강의 교재

## 1. Cursor AI 설치 및 계정 설정
### 1.1 Cursor AI 설치하기
1. **Cursor AI 다운로드**
   - 공식 웹사이트(cursor.sh)에 접속
   - 'Download' 버튼 클릭
   - 운영체제에 맞는 버전 선택 (Windows, macOS, Linux)

2. **설치 과정**
   - 다운로드된 설치 파일 실행
   - 설치 마법사의 안내에 따라 진행
   - 기본 설정 수락 (별도 설정이 필요한 경우 안내)

### 1.2 계정 생성 및 로그인
1. **계정 생성**
   - Cursor AI 첫 실행 시 회원가입/로그인 화면 표시
   - 'Sign Up' 클릭하여 계정 생성
   - 이메일 주소와 비밀번호 입력
   - 이메일 인증 완료

2. **로그인**
   - 계정 생성 후 로그인 진행
   - 로그인 상태 유지 옵션 선택 가능

3. **무료 플랜 vs 유료 플랜**
   - 무료 플랜: 기본 기능 사용 가능
   - 유료 플랜(Pro): 더 큰 컨텍스트 창, 고급 AI 모델 접근, 추가 기능
   - 이 강의는 무료 플랜으로 충분히 진행 가능

## 2. Cursor AI 인터페이스 및 개발 환경 최적화
### 2.1 인터페이스 구성 요소
1. **파일 탐색기 (좌측)**
   - 프로젝트 파일 및 폴더 관리
   - 파일 생성, 이동, 삭제 기능

2. **코드 편집 영역 (중앙)**
   - 실제 코드 작성 및 편집 공간
   - 문법 강조 표시 및 자동 들여쓰기 기능

3. **AI 어시스턴트 패널 (우측)**
   - AI와 대화하여 코드 생성 요청
   - 코드 분석 및 최적화 요청 가능

4. **터미널 및 콘솔 (하단)**
   - 명령어 실행 및 앱 테스트
   - 오류 메시지 및 로그 확인

### 2.2 개발 환경 최적화 설정
1. **Cursor AI 기본 설정**
   - File > Preferences > Settings (Ctrl+,)
   - 설정 검색창에 'Cursor' 입력
   - 주요 설정 항목:
     * API Provider: 'OpenAI' 설정
     * Auto Complete Enabled: 체크
     * Chat Panel Visible: 체크

2. **유용한 단축키**
   - Ctrl+K: AI 어시스턴트에 요청
   - Ctrl+L: 선택한 코드에 대한 AI 설명 요청
   - Ctrl+Enter: 코드 편집기에서 AI에 직접 질문
   - F5: 앱 실행

### 2.3 테마 및 폰트 설정 (선택사항)
   - 가독성 높은 폰트 선택 (예: JetBrains Mono, Fira Code)
   - 테마 변경 (밝은 테마/어두운 테마)
   - 글자 크기 조정

## 3. Flutter 개발 환경 설정
### 3.1 Flutter SDK 설치
1. **Flutter 다운로드**
   - flutter.dev 웹사이트 접속
   - 'Get started' 클릭
   - 운영체제에 맞는 설치 가이드 선택

2. **설치 과정**
   - ZIP 파일 다운로드 및 원하는 위치에 압축 해제
   - 환경 변수 설정 (PATH에 Flutter 경로 추가)
   - 설치 확인: 터미널에서 `flutter doctor` 명령어 실행

3. **필수 종속성 설치**
   - Android Studio (Android 개발용)
   - Xcode (iOS 개발용, macOS만 해당)
   - Visual Studio (Windows 앱 개발용, Windows만 해당)

### 3.2 Cursor AI와 Flutter 연동
1. **Flutter 프로젝트 생성**
   - Cursor AI에서 File > New Folder로 프로젝트 폴더 생성
   - 터미널에서 명령어 실행: `flutter create hello_world`
   - 프로젝트 구조 확인

2. **Flutter 프로젝트 구조 이해**
   - lib/: 주요 Dart 코드 파일 위치
   - pubspec.yaml: 프로젝트 메타데이터 및 종속성
   - android/, ios/, web/: 플랫폼별 프로젝트 파일

3. **Flutter 확장 기능 설치 (선택사항)**
   - Cursor AI에서 Flutter 지원 확장 프로그램 설치
   - 코드 스니펫 및 자동 완성 기능 활성화

## 4. 첫 "Hello World" 앱 개발
### 4.1 기본 앱 구조 이해
1. **Flutter 앱의 기본 구조**
   - main.dart 파일: 앱의 진입점
   - MaterialApp: 앱의 기본 프레임워크
   - Scaffold: 앱의 기본 레이아웃 구조
   - 위젯 트리: Flutter 앱의 UI 구성 방식

2. **주요 위젯 개념**
   - StatelessWidget: 상태가 변경되지 않는 위젯
   - StatefulWidget: 상태가 변경될 수 있는 위젯
   - Text, Button, Container 등 기본 위젯

### 4.2 AI를 활용한 코드 생성
1. **AI에게 코드 요청하기**
   - AI 어시스턴트 패널 열기
   - 명확한 요청 작성: "Flutter로 간단한 Hello World 앱을 만들어줘. 화면 중앙에 'Hello, World!'라는 텍스트가 표시되고, 배경은 파란색, 텍스트는 흰색으로 표시되는 앱이 필요해."
   - 생성된 코드 검토

2. **생성된 코드 이해**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.blue,
        body: Center(
          child: Text(
            'Hello, World!',
            style: TextStyle(
              fontSize: 32,
              color: Colors.white,
              fontWeight: FontWeight.bold,
            ),
          ),
        ),
      ),
    );
  }
}
```

3. **코드 설명**
   - `main()`: 앱의 진입점
   - `MyApp` 클래스: 앱의 루트 위젯
   - `build()` 메서드: 위젯의 UI를 구성
   - `MaterialApp`: 머티리얼 디자인 지원
   - `Scaffold`: 기본 앱 구조 제공
   - `Center`: 내용을 중앙에 배치
   - `Text`: 텍스트 표시 위젯

### 4.3 앱 실행 및 테스트
1. **앱 실행 방법**
   - 터미널에서 `flutter run` 명령어 실행
   - 또는 F5 키를 눌러 디버그 모드로 실행
   - 지원 플랫폼 선택 (Android/iOS/Web)

2. **실행 결과 확인**
   - 에뮬레이터 또는 실제 기기에서 앱 확인
   - 중앙에 'Hello, World!' 텍스트가 표시됨
   - 파란색 배경, 흰색 글씨 확인

### 4.4 앱 기능 개선
1. **추가 기능 요청하기**
   - AI에게 추가 요청: "이 앱에 버튼을 추가하고, 버튼을 클릭하면 'Hello, World!'가 'Hello, [사용자 이름]!'으로 변경되는 기능을 추가해줘. 사용자 이름은 텍스트 필드로 입력받아."
   - 생성된 코드 검토 및 적용

2. **개선된 코드 이해**
   - StatefulWidget으로 변경: 상태 변경 지원
   - TextField 위젯: 사용자 입력 받기
   - 버튼 이벤트 처리: 텍스트 변경 기능

3. **변경 사항 테스트**
   - 앱 재실행
   - 텍스트 필드에 이름 입력
   - 버튼 클릭하여 텍스트 변경 확인

## 5. 연습 및 응용
### 5.1 자신만의 변형 만들기
1. **아이디어 확장해보기**
   - 배경색 변경 버튼 추가하기
   - 다양한 인사말 추가하기
   - 텍스트 크기 조절 기능 추가하기

2. **AI에게 요청하기**
   - 명확한 요구사항 작성
   - 단계적으로 기능 추가 요청

### 5.2 일반적인 오류 및 해결 방법
1. **일반적인 오류**
   - 라이브러리 import 오류
   - 문법 오류
   - 위젯 트리 구성 오류

2. **오류 해결 전략**
   - 오류 메시지 분석
   - AI에게 오류 해결 방법 질문
   - Flutter 문서 참조

## 6. 다음 단계
- 효과적인 프롬프트 작성법 학습
- 더 복잡한 앱 구조 이해
- Flutter 위젯 활용 방법 심화
- TO-DO 앱 개발 준비

---

## 부록: 유용한 자료
- Flutter 공식 문서: flutter.dev/docs
- Dart 프로그래밍 언어: dart.dev
- Material Design 가이드: material.io
- Flutter 위젯 카탈로그: flutter.dev/docs/development/ui/widgets
