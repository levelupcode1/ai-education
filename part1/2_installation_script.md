# Cursor AI 설치부터 첫 "Hello World" 앱 실행까지! - 강의 대본

## 인트로 (00:00-00:45)
안녕하세요! 이번 강의에서는 Cursor AI를 설치하고 첫 번째 앱을 만드는 과정을 함께 해보겠습니다. 코딩 경험이 전혀 없어도 걱정하지 마세요. 모든 과정을 단계별로 차근차근 설명해 드리겠습니다.

오늘 강의가 끝나면 여러분은 Cursor AI를 완벽하게 설치하고, 기본 인터페이스를 이해하며, 첫 번째 "Hello World" 앱을 실행할 수 있게 될 것입니다. 그럼 바로 시작해볼까요?

## Cursor AI 설치 및 계정 설정 (00:45-05:00)
먼저 Cursor AI를 설치하는 방법부터 알아보겠습니다.

1. 웹 브라우저를 열고 주소창에 'cursor.sh'를 입력하여 Cursor AI 공식 웹사이트에 접속합니다.
(화면 전환: 브라우저에서 Cursor 웹사이트 접속 장면)

2. 홈페이지에서 'Download' 버튼을 클릭합니다.
(화면 전환: Download 버튼 강조 표시)

3. 여러분의 운영체제에 맞는 버전을 선택하세요. Windows, macOS, Linux 모두 지원합니다.
(화면 전환: 운영체제 선택 화면)

4. 다운로드가 완료되면 설치 파일을 실행합니다.
(화면 전환: 설치 파일 실행 및 설치 진행 과정)

5. 설치가 완료되면 Cursor AI를 실행해보세요.
(화면 전환: Cursor AI 실행 화면)

설치가 완료되었다면 이제 계정을 만들고 설정해보겠습니다. Cursor AI의 모든 기능을 사용하려면 계정이 필요합니다.

1. Cursor AI를 처음 실행하면 로그인 또는 회원가입 화면이 나타납니다.
(화면 전환: 로그인/회원가입 화면)

2. 'Sign Up'을 클릭하고 이메일, 비밀번호를 입력하여 계정을 만듭니다.
(화면 전환: 회원가입 과정)

3. 이메일 인증을 완료하면 Cursor AI에 로그인할 수 있습니다.
(화면 전환: 로그인 완료 및 Cursor AI 메인 화면)

Cursor AI는 무료 플랜과 유료 플랜을 제공합니다. 무료 플랜으로도 충분히 많은 기능을 사용할 수 있지만, 더 많은 기능과 높은 성능의 AI 모델을 사용하려면 Pro 플랜을 고려해볼 수 있습니다. 이번 강의에서는 무료 플랜으로도 충분히 따라올 수 있습니다.

## 개발 환경 최적화 및 인터페이스 소개 (05:00-10:00)
Cursor AI가 설치되고 계정 설정이 완료되었으니, 이제 개발 환경을 최적화하고 기본 인터페이스를 살펴보겠습니다.

먼저 Cursor AI의 인터페이스를 살펴봅시다. Cursor AI는 VS Code를 기반으로 만들어져서 VS Code 사용자라면 친숙하게 느껴질 겁니다. 하지만 처음 보는 분들도 걱정하지 마세요.
(화면 전환: Cursor AI 인터페이스 전체 화면)

화면 왼쪽에는 파일 탐색기가 있습니다. 여기서 프로젝트 파일들을 관리할 수 있죠.
(화면 전환: 파일 탐색기 부분 강조)

중앙에는 코드 편집 영역이 있습니다. 실제 코드를 작성하고 수정하는 공간입니다.
(화면 전환: 코드 편집 영역 강조)

오른쪽에는 Cursor AI의 핵심인 AI 어시스턴트 패널이 있습니다. 여기서 AI와 대화하며 코드 생성을 요청할 수 있습니다.
(화면 전환: AI 어시스턴트 패널 강조)

하단에는 터미널과 콘솔이 있어 앱을 실행하고 테스트할 수 있습니다.
(화면 전환: 터미널/콘솔 영역 강조)

이제 개발 환경을 최적화해보겠습니다. 몇 가지 설정을 조정하면 더 효율적으로 작업할 수 있습니다.

1. 먼저 설정 메뉴를 열어보세요. 상단 메뉴의 'File > Preferences > Settings'를 클릭하거나 단축키 Ctrl+,(콤마)를 사용하세요.
(화면 전환: 설정 메뉴 접근 과정)

2. 검색창에 'Cursor'를 입력하면 Cursor AI 관련 설정들이 나타납니다.
(화면 전환: Cursor 설정 검색 결과)

3. 'Cursor: API Provider'를 'OpenAI'로 설정하고, 필요하다면 API 키를 입력합니다.
(화면 전환: API Provider 설정)

4. 'Cursor: Auto Complete Enabled'를 체크하여 자동 완성 기능을 활성화합니다.
(화면 전환: 자동 완성 설정)

5. 'Cursor: Chat Panel Visible'을 체크하여 AI 어시스턴트 패널을 항상 표시하도록 합니다.
(화면 전환: 채팅 패널 설정)

이제 기본적인 환경 설정이 완료되었습니다. Cursor AI를 더 효과적으로 사용하기 위한 몇 가지 단축키도 알아두면 좋습니다.

- Ctrl+K: AI 어시스턴트에게 현재 코드에 대한 질문이나 요청을 할 수 있습니다.
- Ctrl+L: 코드 블록을 선택하고 이 단축키를 누르면 AI가 해당 코드를 설명해줍니다.
- Ctrl+Enter: 코드 편집기에서 바로 AI에게 질문할 수 있습니다.
- F5: 앱을 실행하는 단축키입니다.

이러한 단축키들을 잘 활용하면 개발 속도를 크게 높일 수 있습니다.

## Flutter 개발 환경 설정 (10:00-15:00)
이제 Flutter 개발 환경을 설정해보겠습니다. Flutter는 구글에서 개발한 크로스 플랫폼 프레임워크로, 하나의 코드베이스로 iOS, Android, 웹 등 여러 플랫폼에서 동작하는 앱을 만들 수 있습니다.

먼저 Flutter SDK를 설치해야 합니다. 브라우저를 열고 'flutter.dev'에 접속하세요.
(화면 전환: Flutter 공식 웹사이트)

'Get started' 버튼을 클릭하고 여러분의 운영체제에 맞는 설치 가이드를 따라 진행하세요.
(화면 전환: Flutter 설치 가이드)

설치가 완료되면 터미널을 열고 다음 명령어를 입력하여 Flutter가 제대로 설치되었는지 확인하세요:
```
flutter doctor
```

이 명령어는 Flutter 개발 환경에 필요한 모든 구성 요소가 제대로 설치되었는지 확인하고, 문제가 있다면 해결 방법을 제시합니다.
(화면 전환: flutter doctor 실행 결과)

이제 Cursor AI와 Flutter를 연동해보겠습니다. Cursor AI에서 새 프로젝트를 만들어보세요.
1. File > New Folder를 선택하고 프로젝트 폴더를 만듭니다.
2. 터미널을 열고 다음 명령어를 입력하여 새 Flutter 프로젝트를 생성합니다:
```
flutter create hello_world
```
3. 생성된 프로젝트 폴더를 Cursor AI에서 엽니다.
(화면 전환: Flutter 프로젝트 구조)

Flutter 프로젝트가 성공적으로 생성되었습니다. 프로젝트 구조를 살펴보세요:
- lib 폴더: 앱의 주요 Dart 코드가 위치하는 곳입니다.
- pubspec.yaml: 프로젝트의 메타데이터와 종속성을 관리하는 파일입니다.
- android, ios 폴더: 각 플랫폼별 프로젝트 파일들이 위치합니다.

이제 Cursor AI에서 Flutter 앱을 개발할 준비가 되었습니다!

## 첫 "Hello World" 앱 만들기 (15:00-17:30)
이제 드디어 첫 번째 Flutter 앱을 만들어보겠습니다. lib 폴더에 있는 main.dart 파일을 열어보세요. 이 파일이 앱의 시작점입니다.

기본 생성된 코드를 모두 지우고, AI 어시스턴트에게 간단한 "Hello World" 앱을 만들어달라고 요청해보겠습니다. AI 어시스턴트 패널을 열고 다음과 같이 입력하세요:

"Flutter로 간단한 Hello World 앱을 만들어줘. 화면 중앙에 'Hello, World!'라는 텍스트가 표시되고, 배경은 파란색, 텍스트는 흰색으로 표시되는 앱이 필요해."

(화면 전환: AI 어시스턴트 요청 및 응답)

AI가 생성한 코드를 확인하고 main.dart 파일에 복사하세요. 생성된 코드는 다음과 비슷할 것입니다:

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

이제 앱을 실행해보겠습니다. 터미널에서 다음 명령어를 입력하세요:
```
flutter run
```

또는 F5 키를 눌러 디버그 모드로 실행할 수도 있습니다.
(화면 전환: 실행 중인 Hello World 앱)

축하합니다! 여러분의 첫 번째 Flutter 앱이 성공적으로 실행되었습니다!

이제 AI에게 이 앱을 조금 더 개선해달라고 요청해보겠습니다. AI 어시스턴트에게 다음과 같이 요청하세요:

"이 앱에 버튼을 추가하고, 버튼을 클릭하면 'Hello, World!'가 'Hello, [사용자 이름]!'으로 변경되는 기능을 추가해줘. 사용자 이름은 텍스트 필드로 입력받아."

(화면 전환: 추가 요청 및 응답)

AI가 제안한 수정된 코드를 main.dart 파일에 적용하고 앱을 다시 실행해보세요.
(화면 전환: 수정된 앱 실행 화면)

이렇게 Cursor AI를 사용하면 코딩 지식 없이도 간단한 Flutter 앱을 만들 수 있습니다. 여러분의 아이디어를 자연어로 설명하면 AI가 그에 맞는 코드를 생성해주죠.

## 마무리 및 다음 강의 예고 (17:30-18:43)
오늘 우리는 Cursor AI를 설치하고, 기본 인터페이스를 살펴보고, Flutter 개발 환경을 설정하고, 첫 번째 "Hello World" 앱을 성공적으로 만들었습니다. 정말 놀랍지 않나요? 코드 한 줄 직접 작성하지 않고도 기능하는 앱을 만들었습니다!

이제 여러분은 Cursor AI의 기본 사용법을 알게 되었습니다. 다음 강의에서는 이를 바탕으로 좀 더 복잡한 앱을 만들기 위한 효과적인 프롬프트 작성법에 대해 배우게 될 것입니다.

오늘 배운 내용을 복습하고 여러분만의 아이디어로 "Hello World" 앱을 더 발전시켜보세요. 예를 들어, 배경색을 바꾸는 버튼을 추가하거나, 다른 인사말을 추가해보는 것은 어떨까요?

다음 강의에서는 효과적인 프롬프트 작성법을 배우고 간단한 TO-DO 앱을 만들어볼 예정입니다. 기대해주세요!

궁금한 점이나 도움이 필요한 부분이 있으면 언제든지 질문해주세요. 다음 강의에서 만나요!
