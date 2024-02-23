---
layout: post
title: MaterialApp 위젯
date: 2024-02-19 21:53:00 +0900
category: Flutter
permalink: /flutter/materialapp
tags: [MaterialApp]
---

<br>

Flutter의 `MaterialApp` Widget은 Google이 제시한 Material Design을 구현하는 가장 바탕이 되는 Widget으로, 주요 속성은 다음과 같습니다:

1. `home`: 애플리케이션의 첫 화면으로 표시할 위젯을 지정합니다.
2. `title`: 애플리케이션의 제목을 설정하여 디바이스에서 표시합니다.
3. `theme`: 애플리케이션의 전체적인 테마를 정의하며, 색상, 타이포그래피 및 모양을 포함합니다.
4. `routes`: 이름이 지정된 경로를 빌더 함수에 매핑하여 화면 간의 이동을 가능하게 합니다.
5. `initialRoute`: 애플리케이션이 시작될 때 표시할 초기 경로를 지정합니다.
6. `onGenerateRoute`: 들어오는 경로 설정을 기반으로 동적으로 경로를 생성합니다.
7. `navigatorKey`: 네비게이션을 제어하기 위한 네비게이터 위젯에 대한 키를 제공합니다.
8. `navigatorObservers`: 네비게이션 이벤트를 추적하기 위한 옵저버입니다.
9. `builder`: 애플리케이션의 루트 위젯을 생성합니다.
10. `locale`: 애플리케이션의 로컬라이제이션을 위한 로캘을 설정합니다.
11. `localizationsDelegates`와 `supportedLocales`: 앱의 로컬라이즈된 리소스를 정의합니다.
