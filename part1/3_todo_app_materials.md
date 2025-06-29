# 효과적인 프롬프트로 간단한 TO-DO 앱 완성하기 - 강의 교재

## 1. 효과적인 프롬프트 작성법
### 1.1 좋은 프롬프트의 핵심 요소
1. **명확성(Clarity)**
   - 무엇을 원하는지 명확하게 표현
   - 모호한 표현 피하기
   - 구체적인 목표와 요구사항 명시

2. **구체성(Specificity)**
   - 필요한 기능 상세히 나열
   - 디자인 스타일 및 UI 요소 설명
   - 원하는 코드 구조나 패턴 언급

3. **맥락 제공(Context)**
   - 프로젝트 목적 설명
   - 대상 사용자 정보
   - 기존 코드나 프로젝트 상황 설명

### 1.2 나쁜 프롬프트 vs 좋은 프롬프트

| 나쁜 프롬프트 | 좋은 프롬프트 | 개선된 이유 |
|-------------|--------------|-----------|
| "TO-DO 앱 만들어줘." | "Flutter로 간단한 TO-DO 앱을 만들어줘. 사용자가 할 일을 추가, 삭제, 완료 표시할 수 있어야 해. Material 디자인을 사용하고, 할 일 목록은 로컬 저장소에 저장되어야 해. 코드는 간결하고 주석이 잘 달려있으면 좋겠어." | 기술 스택, 필요 기능, 디자인 스타일, 데이터 저장 방식, 코드 스타일 명시 |
| "로그인 기능 추가해줘." | "Firebase 인증을 사용해서 이메일/비밀번호 로그인 기능을 추가해줘. 로그인 화면에는 이메일과 비밀번호 입력 필드, 로그인 버튼, 회원가입 링크가 필요해. 유효성 검사도 구현해줘서 이메일 형식과 비밀번호 강도를 확인해야 해." | 사용할 기술, UI 구성 요소, 필요한 유효성 검사 명시 |
| "버그 고쳐줘." | "ListView에서 아이템을 삭제할 때 setState 호출 후 화면이 제대로 갱신되지 않는 버그가 있어. 아마도 setState 호출 시점이나 리스트 업데이트 방식에 문제가 있는 것 같아. 문제를 찾아서 수정해줘." | 버그 발생 상황, 예상 원인, 해결 방향 제시 |

### 1.3 효과적인 프롬프트 작성 전략
1. **단계적으로 요청하기**
   - 복잡한 앱은 한 번에 요청하지 않기
   - 기본 구조부터 시작해 점진적으로 기능 추가
   - 각 단계에서 생성된 코드 검토 및 이해

2. **예시와 참조 제공하기**
   - 비슷한 앱이나 디자인 참조 언급
   - 원하는 결과물과 유사한 예시 설명
   - "~와 비슷한 스타일로" 등의 표현 활용

3. **피드백 주고 반복하기**
   - 첫 결과물 평가 후 구체적 피드백 제공
   - "이 부분은 좋지만, ~부분을 개선해줘" 형식
   - 점진적으로 원하는 결과에 근접

4. **기술적 세부사항 명시하기**
   - 사용할 패키지나 라이브러리 언급
   - 원하는 코드 패턴이나 아키텍처 설명
   - 성능이나 호환성 요구사항 포함

## 2. TO-DO 앱 개발 과정
### 2.1 앱 기본 구조 설계

**기본 구조 요청 프롬프트:**
```
Flutter로 간단한 TO-DO 앱의 기본 구조를 만들어줘. Material 디자인을 사용하고, 앱 제목은 'My Tasks'로 표시해. 화면 상단에는 앱 바가 있고, 중앙에는 할 일 목록이 표시되는 ListView가 있어야 해. 하단에는 새 할 일을 추가할 수 있는 FloatingActionButton이 필요해. 아직 기능 구현은 필요 없고, 기본 레이아웃만 잡아줘.
```

**생성된 기본 코드:**
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
      title: 'My Tasks',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: const TasksScreen(),
    );
  }
}

class TasksScreen extends StatelessWidget {
  const TasksScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('My Tasks'),
      ),
      body: ListView.builder(
        itemCount: 0, // 아직 데이터가 없으므로 0
        itemBuilder: (context, index) {
          return const ListTile(
            title: Text('Task item will appear here'),
          );
        },
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          // 새 할 일 추가 기능은 나중에 구현
        },
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

### 2.2 데이터 모델 및 상태 관리 구현

**데이터 모델 및 상태 관리 요청 프롬프트:**
```
이제 TO-DO 앱에 필요한 데이터 모델과 상태 관리를 추가해줘. Task 클래스를 만들어서 할 일 항목을 표현하고, StatefulWidget을 사용해서 할 일 목록의 상태를 관리하도록 해. Task 클래스는 id, title, isCompleted 속성을 가지고 있어야 해. 그리고 TasksScreen 위젯에서 할 일 목록을 표시하고, 새 할 일 추가, 할 일 완료 표시, 할 일 삭제 기능을 구현해줘.
```

**Task 모델 클래스:**
```dart
class Task {
  final String id;
  final String title;
  bool isCompleted;

  Task({
    required this.id,
    required this.title,
    this.isCompleted = false,
  });

  // JSON 변환을 위한 메서드 (로컬 저장소 사용 시 필요)
  Map<String, dynamic> toJson() {
    return {
      'id': id,
      'title': title,
      'isCompleted': isCompleted,
    };
  }

  // JSON에서 Task 객체 생성을 위한 팩토리 메서드
  factory Task.fromJson(Map<String, dynamic> json) {
    return Task(
      id: json['id'],
      title: json['title'],
      isCompleted: json['isCompleted'],
    );
  }
}
```

**StatefulWidget으로 변경된 TasksScreen:**
```dart
class TasksScreen extends StatefulWidget {
  const TasksScreen({Key? key}) : super(key: key);

  @override
  _TasksScreenState createState() => _TasksScreenState();
}

class _TasksScreenState extends State<TasksScreen> {
  final List<Task> _tasks = [];

  void _addTask(String title) {
    if (title.trim().isEmpty) return;
    
    setState(() {
      _tasks.add(
        Task(
          id: DateTime.now().millisecondsSinceEpoch.toString(),
          title: title,
        ),
      );
    });
  }

  void _toggleTask(String id) {
    setState(() {
      final task = _tasks.firstWhere((task) => task.id == id);
      task.isCompleted = !task.isCompleted;
    });
  }

  void _deleteTask(String id) {
    setState(() {
      _tasks.removeWhere((task) => task.id == id);
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('My Tasks'),
      ),
      body: _tasks.isEmpty
          ? const Center(
              child: Text('할 일이 없습니다. 새 할 일을 추가해보세요!'),
            )
          : ListView.builder(
              itemCount: _tasks.length,
              itemBuilder: (context, index) {
                final task = _tasks[index];
                return ListTile(
                  title: Text(
                    task.title,
                    style: TextStyle(
                      decoration: task.isCompleted
                          ? TextDecoration.lineThrough
                          : null,
                    ),
                  ),
                  leading: Checkbox(
                    value: task.isCompleted,
                    onChanged: (value) => _toggleTask(task.id),
                  ),
                  trailing: IconButton(
                    icon: const Icon(Icons.delete),
                    onPressed: () => _deleteTask(task.id),
                  ),
                );
              },
            ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          // 간단한 텍스트 입력 처리
          final controller = TextEditingController();
          showDialog(
            context: context,
            builder: (context) => AlertDialog(
              title: const Text('새 할 일 추가'),
              content: TextField(
                controller: controller,
                decoration: const InputDecoration(
                  hintText: '할 일을 입력하세요',
                ),
                autofocus: true,
              ),
              actions: [
                TextButton(
                  onPressed: () => Navigator.pop(context),
                  child: const Text('취소'),
                ),
                TextButton(
                  onPressed: () {
                    _addTask(controller.text);
                    Navigator.pop(context);
                  },
                  child: const Text('추가'),
                ),
              ],
            ),
          );
        },
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

### 2.3 할 일 추가 기능 개선

**모달 다이얼로그 개선 요청 프롬프트:**
```
할 일 추가 기능을 개선해줘. 플로팅 액션 버튼을 누르면 모달 다이얼로그가 표시되고, 텍스트 필드에 할 일을 입력할 수 있게 해. 다이얼로그에는 '추가'와 '취소' 버튼이 있어야 하고, '추가' 버튼을 누르면 입력한 할 일이 목록에 추가되도록 해. 텍스트 필드가 비어있으면 추가 버튼이 비활성화되도록 해.
```

**개선된 할 일 추가 다이얼로그:**
```dart
void _showAddTaskDialog() {
  final controller = TextEditingController();
  bool isInputValid = false;

  showDialog(
    context: context,
    builder: (context) => StatefulBuilder(
      builder: (context, setState) => AlertDialog(
        title: const Text('새 할 일 추가'),
        content: TextField(
          controller: controller,
          decoration: const InputDecoration(
            hintText: '할 일을 입력하세요',
            border: OutlineInputBorder(),
          ),
          autofocus: true,
          onChanged: (value) {
            setState(() {
              isInputValid = value.trim().isNotEmpty;
            });
          },
        ),
        actions: [
          TextButton(
            onPressed: () => Navigator.pop(context),
            child: const Text('취소'),
          ),
          ElevatedButton(
            onPressed: isInputValid
                ? () {
                    _addTask(controller.text);
                    Navigator.pop(context);
                  }
                : null,
            style: ElevatedButton.styleFrom(
              disabledBackgroundColor: Colors.grey.shade300,
            ),
            child: const Text('추가'),
          ),
        ],
      ),
    ),
  );
}
```

### 2.4 로컬 저장소에 데이터 저장하기

**로컬 저장소 기능 요청 프롬프트:**
```
shared_preferences 패키지를 사용해서 할 일 목록을 로컬 저장소에 저장하고 불러오는 기능을 추가해줘. 앱이 시작될 때 저장된 할 일 목록을 불러오고, 할 일이 추가, 삭제, 변경될 때마다 변경 사항을 저장소에 저장해야 해.
```

**패키지 추가 방법:**
1. pubspec.yaml 파일에 dependency 추가:
```yaml
dependencies:
  flutter:
    sdk: flutter
  shared_preferences: ^2.2.0
```

2. 패키지 설치:
```
flutter pub get
```

**로컬 저장소 구현 코드:**
```dart
import 'dart:convert';
import 'package:shared_preferences/shared_preferences.dart';

// TasksScreen 클래스에 다음 메서드 추가

// 할 일 목록 저장
Future<void> _saveTasks() async {
  final prefs = await SharedPreferences.getInstance();
  final taskListJson = _tasks.map((task) => task.toJson()).toList();
  await prefs.setString('tasks', jsonEncode(taskListJson));
}

// 할 일 목록 불러오기
Future<void> _loadTasks() async {
  final prefs = await SharedPreferences.getInstance();
  final tasksString = prefs.getString('tasks');
  
  if (tasksString != null) {
    final taskListJson = jsonDecode(tasksString) as List;
    setState(() {
      _tasks.clear();
      _tasks.addAll(
        taskListJson.map((taskJson) => Task.fromJson(taskJson)).toList(),
      );
    });
  }
}

// 기존 메서드 수정 - 변경사항 저장 추가
void _addTask(String title) {
  if (title.trim().isEmpty) return;
  
  setState(() {
    _tasks.add(
      Task(
        id: DateTime.now().millisecondsSinceEpoch.toString(),
        title: title,
      ),
    );
  });
  _saveTasks(); // 데이터 저장
}

void _toggleTask(String id) {
  setState(() {
    final task = _tasks.firstWhere((task) => task.id == id);
    task.isCompleted = !task.isCompleted;
  });
  _saveTasks(); // 데이터 저장
}

void _deleteTask(String id) {
  setState(() {
    _tasks.removeWhere((task) => task.id == id);
  });
  _saveTasks(); // 데이터 저장
}

// initState에서 데이터 로드
@override
void initState() {
  super.initState();
  _loadTasks();
}
```

### 2.5 UI 디자인 개선하기

**UI 개선 요청 프롬프트:**
```
TO-DO 앱의 디자인을 개선해줘. 각 할 일 항목을 Card 위젯으로 감싸고, 완료된 할 일은 텍스트에 취소선을 표시해. 그리고 앱의 전체적인 색상 테마를 파란색에서 보라색 계열로 변경해. 또한 앱 바에 할 일 개수를 표시하는 기능도 추가해.
```

**개선된 UI 코드:**
```dart
class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My Tasks',
      theme: ThemeData(
        primarySwatch: Colors.purple,
        accentColor: Colors.purpleAccent,
        visualDensity: VisualDensity.adaptivePlatformDensity,
        cardTheme: CardTheme(
          elevation: 2,
          margin: const EdgeInsets.symmetric(
            horizontal: 10,
            vertical: 5,
          ),
        ),
      ),
      home: const TasksScreen(),
    );
  }
}

// TasksScreen의 build 메서드 수정
@override
Widget build(BuildContext context) {
  final completedTasks = _tasks.where((task) => task.isCompleted).length;
  
  return Scaffold(
    appBar: AppBar(
      title: Text('My Tasks (${_tasks.length})'),
      actions: [
        Center(
          child: Padding(
            padding: const EdgeInsets.only(right: 16.0),
            child: Text(
              '완료: $completedTasks/${_tasks.length}',
              style: const TextStyle(fontSize: 16),
            ),
          ),
        ),
      ],
    ),
    body: _tasks.isEmpty
        ? Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: const [
                Icon(
                  Icons.assignment,
                  size: 64,
                  color: Colors.grey,
                ),
                SizedBox(height: 16),
                Text(
                  '할 일이 없습니다. 새 할 일을 추가해보세요!',
                  style: TextStyle(
                    fontSize: 16,
                    color: Colors.grey,
                  ),
                ),
              ],
            ),
          )
        : ListView.builder(
            itemCount: _tasks.length,
            itemBuilder: (context, index) {
              final task = _tasks[index];
              return Card(
                child: ListTile(
                  title: Text(
                    task.title,
                    style: TextStyle(
                      decoration: task.isCompleted
                          ? TextDecoration.lineThrough
                          : null,
                      color: task.isCompleted
                          ? Colors.grey
                          : Colors.black,
                    ),
                  ),
                  leading: Checkbox(
                    value: task.isCompleted,
                    activeColor: Colors.purple,
                    onChanged: (value) => _toggleTask(task.id),
                  ),
                  trailing: IconButton(
                    icon: const Icon(Icons.delete, color: Colors.red),
                    onPressed: () => _deleteTask(task.id),
                  ),
                ),
              );
            },
          ),
    floatingActionButton: FloatingActionButton(
      backgroundColor: Colors.purple,
      onPressed: _showAddTaskDialog,
      child: const Icon(Icons.add),
    ),
  );
}
```

## 3. 프롬프트 작성 연습 문제
다음 요구사항을 충족하는 프롬프트를 작성해보세요:

1. **기존 TO-DO 앱에 카테고리 기능 추가**
   - 각 할 일에 카테고리 지정 가능
   - 카테고리별로 필터링 가능
   - 카테고리 추가/수정/삭제 기능

2. **TO-DO 앱에 알림 기능 추가**
   - 할 일에 마감일과 시간 설정 가능
   - 설정된 시간에 알림 표시
   - 알림 활성화/비활성화 설정

3. **TO-DO 앱의 할 일 목록을 공유하는 기능 추가**
   - 할 일 목록을 텍스트로 내보내기
   - 소셜 미디어나 메시지 앱으로 공유
   - 공유 내용의 형식 사용자 지정

## 4. 다음 단계 학습 가이드
### 4.1 더 배울 수 있는 Flutter 관련 주제
- 상태 관리 라이브러리 (Provider, Riverpod 등)
- 데이터베이스 연동 (SQLite, Firebase 등)
- 테마 및 디자인 시스템 구축
- 애니메이션 및 고급 UI 구현

### 4.2 Cursor AI 활용 심화 팁
- 코드 리팩토링 요청하기
- 성능 최적화 요청하기
- 테스트 코드 생성 요청하기
- 특정 패턴이나 아키텍처로 변환 요청하기

### 4.3 추천 자료
- Flutter 공식 문서: flutter.dev/docs
- Dart 프로그래밍 언어: dart.dev
- Flutter 패키지 저장소: pub.dev
- Cursor AI 공식 문서: cursor.sh/docs

## 부록: 전체 TO-DO 앱 코드

```dart
import 'package:flutter/material.dart';
import 'dart:convert';
import 'package:shared_preferences/shared_preferences.dart';

void main() {
  runApp(const MyApp());
}

class Task {
  final String id;
  final String title;
  bool isCompleted;

  Task({
    required this.id,
    required this.title,
    this.isCompleted = false,
  });

  Map<String, dynamic> toJson() {
    return {
      'id': id,
      'title': title,
      'isCompleted': isCompleted,
    };
  }

  factory Task.fromJson(Map<String, dynamic> json) {
    return Task(
      id: json['id'],
      title: json['title'],
      isCompleted: json['isCompleted'],
    );
  }
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My Tasks',
      theme: ThemeData(
        primarySwatch: Colors.purple,
        accentColor: Colors.purpleAccent,
        visualDensity: VisualDensity.adaptivePlatformDensity,
        cardTheme: CardTheme(
          elevation: 2,
          margin: const EdgeInsets.symmetric(
            horizontal: 10,
            vertical: 5,
          ),
        ),
      ),
      home: const TasksScreen(),
    );
  }
}

class TasksScreen extends StatefulWidget {
  const TasksScreen({Key? key}) : super(key: key);

  @override
  _TasksScreenState createState() => _TasksScreenState();
}

class _TasksScreenState extends State<TasksScreen> {
  final List<Task> _tasks = [];

  @override
  void initState() {
    super.initState();
    _loadTasks();
  }

  Future<void> _saveTasks() async {
    final prefs = await SharedPreferences.getInstance();
    final taskListJson = _tasks.map((task) => task.toJson()).toList();
    await prefs.setString('tasks', jsonEncode(taskListJson));
  }

  Future<void> _loadTasks() async {
    final prefs = await SharedPreferences.getInstance();
    final tasksString = prefs.getString('tasks');
    
    if (tasksString != null) {
      final taskListJson = jsonDecode(tasksString) as List;
      setState(() {
        _tasks.clear();
        _tasks.addAll(
          taskListJson.map((taskJson) => Task.fromJson(taskJson)).toList(),
        );
      });
    }
  }

  void _addTask(String title) {
    if (title.trim().isEmpty) return;
    
    setState(() {
      _tasks.add(
        Task(
          id: DateTime.now().millisecondsSinceEpoch.toString(),
          title: title,
        ),
      );
    });
    _saveTasks();
  }

  void _toggleTask(String id) {
    setState(() {
      final task = _tasks.firstWhere((task) => task.id == id);
      task.isCompleted = !task.isCompleted;
    });
    _saveTasks();
  }

  void _deleteTask(String id) {
    setState(() {
      _tasks.removeWhere((task) => task.id == id);
    });
    _saveTasks();
  }

  void _showAddTaskDialog() {
    final controller = TextEditingController();
    bool isInputValid = false;

    showDialog(
      context: context,
      builder: (context) => StatefulBuilder(
        builder: (context, setState) => AlertDialog(
          title: const Text('새 할 일 추가'),
          content: TextField(
            controller: controller,
            decoration: const InputDecoration(
              hintText: '할 일을 입력하세요',
              border: OutlineInputBorder(),
            ),
            autofocus: true,
            onChanged: (value) {
              setState(() {
                isInputValid = value.trim().isNotEmpty;
              });
            },
          ),
          actions: [
            TextButton(
              onPressed: () => Navigator.pop(context),
              child: const Text('취소'),
            ),
            ElevatedButton(
              onPressed: isInputValid
                  ? () {
                      _addTask(controller.text);
                      Navigator.pop(context);
                    }
                  : null,
              style: ElevatedButton.styleFrom(
                disabledBackgroundColor: Colors.grey.shade300,
              ),
              child: const Text('추가'),
            ),
          ],
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    final completedTasks = _tasks.where((task) => task.isCompleted).length;
    
    return Scaffold(
      appBar: AppBar(
        title: Text('My Tasks (${_tasks.length})'),
        actions: [
          Center(
            child: Padding(
              padding: const EdgeInsets.only(right: 16.0),
              child: Text(
                '완료: $completedTasks/${_tasks.length}',
                style: const TextStyle(fontSize: 16),
              ),
            ),
          ),
        ],
      ),
      body: _tasks.isEmpty
          ? Center(
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                children: const [
                  Icon(
                    Icons.assignment,
                    size: 64,
                    color: Colors.grey,
                  ),
                  SizedBox(height: 16),
                  Text(
                    '할 일이 없습니다. 새 할 일을 추가해보세요!',
                    style: TextStyle(
                      fontSize: 16,
                      color: Colors.grey,
                    ),
                  ),
                ],
              ),
            )
          : ListView.builder(
              itemCount: _tasks.length,
              itemBuilder: (context, index) {
                final task = _tasks[index];
                return Card(
                  child: ListTile(
                    title: Text(
                      task.title,
                      style: TextStyle(
                        decoration: task.isCompleted
                            ? TextDecoration.lineThrough
                            : null,
                        color: task.isCompleted
                            ? Colors.grey
                            : Colors.black,
                      ),
                    ),
                    leading: Checkbox(
                      value: task.isCompleted,
                      activeColor: Colors.purple,
                      onChanged: (value) => _toggleTask(task.id),
                    ),
                    trailing: IconButton(
                      icon: const Icon(Icons.delete, color: Colors.red),
                      onPressed: () => _deleteTask(task.id),
                    ),
                  ),
                );
              },
            ),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Colors.purple,
        onPressed: _showAddTaskDialog,
        child: const Icon(Icons.add),
      ),
    );
  }
}
```
