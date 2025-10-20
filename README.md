# 4장. 플러터 필수 개념 이해하기 - TIL

## 📌 학습 목표
플러터를 활용하기 위해 반드시 알아야 할 핵심 개념을 이해하고 실제 코딩에 적용할 수 있는 능력 습득.  
- 아키텍처 구조
- 위젯 시스템 원리
- 라이프사이클 흐름
- 레이아웃 구성 방식
- 애니메이션 처리
- 라우팅/네비게이션

---

## 1. 플러터 아키텍처

### 📊 3계층 구조

### 주요 구성 요소
- **Embedder**: 플랫폼 네이티브 코드 (Android: Java/C++, iOS: Objective-C), 화면 렌더링, 이벤트 처리  
- **Engine**: C++ 렌더링 엔진, Skia 그래픽, 파일/네트워크 I/O  
- **Framework**: Dart 기반 반응형 UI, Material/Cupertino, 위젯 및 상태 관리

---

## 2. 위젯 시스템

> **플러터에서 모든 것은 위젯**

### 3가지 기본 위젯

**1) StatelessWidget**
```dart
class MyWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Hello');
  }
}
class MyWidget extends StatefulWidget {
  @override
  _MyWidgetState createState() => _MyWidgetState();
}

class _MyWidgetState extends State<MyWidget> {
  int counter = 0;

  void increment() {
    setState(() {
      counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Text('$counter');
  }
}
