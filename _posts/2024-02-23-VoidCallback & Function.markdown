---
layout: post
title: Widget간 이벤트 처리
date: 2024-02-23 20:30:00 +0900
category: Flutter
permalink: /flutter/callback
tags: [VoidCallback, Function]
---

Flutter는 하나의 Widget에서 다른 Widget으로 이벤트 처리를 할때는 방식이 꽤나 까다로워진다.  
이 때 사용하는 방식은 [Function](https://api.flutter.dev/flutter/dart-core/Function-class.html), 즉 (Callback)함수 자체를 넘겨주는 방식이다.

아래의 예시는 Statelsess한 Button위젯을 클릭했을 때, Stateful한 위젯에 표시되는 값을 변경하게 된다.

<br>

이 때,

- State클래스에서는 정의된 Callback함수를 Button위젯에 생성자로 전달한다. (18~19번째 줄)
- Button위젯은 생성자로부터 전달받은 Callback함수를 이벤트에 매핑하여 사용하게 된다. (30~32, 39~41번쨰 줄)

<br>
함수를 전달받는 변수는 Function타입으로 선언하며, () 안에 전달받을 변수들의 type을 동일하게 정의해야 한다.

Function()처럼 값을 전달하지 않을 때는 [VoidCallback](https://api.flutter.dev/flutter/dart-ui/VoidCallback.html)을 사용해도 무방하다. (32번째 줄)
<br>
<br>

```dart
class TestWidget extends StatefulWidget {
  const TestWidget({super.key});

  @override
  State<TestWidget> createState() => _TestWidgetState();
}

class _TestWidgetState extends State<TestWidget> {
  int value = 0;

  @override
  Widget build(BuildContext context) {
    return Column(mainAxisAlignment: MainAxisAlignment.center, children: [
      Text(
        'Count: $value',
        style: TextStyle(fontSize: 30),
      ),
      // Callback함수를 생성자를 통해 전달
      TestButton(addCounter,3 addCounter2)
    ]);
  }

  void addCounter(int addValue) => setState(() => value += addValue);
  void addCounter2() => setState(() => value *= 2);
}

class TestButton extends StatelessWidget {
  const TestButton(this.callback, this.callback2, {super.key});

  final Function(int) callback;
//final Function() callback2;
  final VoidCallback callback2;

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: EdgeInsets.symmetric(vertical: 8),
      child: GestureDetector(
        // 터치 이벤트에 Callback함수를 매핑
        onTap: () => callback.call(3),
        onDoubleTap: callback2,
        onLongPress: () => callback.call(100),
        child: Center(
          child: Container(
            padding: EdgeInsets.symmetric(vertical: 4, horizontal: 8),
            decoration: BoxDecoration(border: Border.all()),
            child: Text(
              'Up counter',
              style: TextStyle(fontSize: 24),
            ),
          ),
        ),
      ),
    );
  }
}
```

Callback 타입은 Function / VoidCallback 외에 GestureDoubleTapCallback / GestureTapDownCallback / GestureTapCancelCallback 등 다양한 Callback타입으로도 정의되어 있어서, 필요에 맞게 사용할 수 있다.
