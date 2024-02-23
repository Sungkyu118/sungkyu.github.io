---
layout: post
title: BottomNavigationBar
date: 2024-02-23 22:37:00 +0900
category: Flutter
permalink: /flutter/navigator
tags: [Navigator, MaterialPageRoute]
---

Flutter의 [BottomNavigationBar](https://api.flutter.dev/flutter/material/BottomNavigationBar-class.html)는 하단 탐색 메뉴를 만드는 데 사용됩니다. 각 아이템은 Icon과 Text로 구성되어 있습니다. 주로, 사용자가 탭을 했을 때, 새로운 페이지로 이동하는 기능을 넣게 됩니다.

웹이라면 버튼 하나에 각각 링크를 주입하는 방식이지만, BottomNavitaionBar는 NavigationBar 전체를 기준으로 tab 이벤트가 실행되고 실제 클릭된 아이템의 index를 탐지하는 방식이다.

## 특징

1. 아이템 구성: BottomNavigationBar의 각 아이템은 IconData와 String으로 정의됩니다. [BottomNavigationBarItem](https://api.flutter.dev/flutter/widgets/BottomNavigationBarItem-class.html) Widget을 사용합니다.
2. onTap 콜백: 사용자가 아이템을 탭할 때 호출되는 콜백입니다. 각 아이템마다 onTap 속성을 설정하여 해당 아이템이 탭됐을 때 실행할 작업을 지정할 수 있습니다.
3. currentIndex: 현재 선택된 아이템의 인덱스를 나타냅니다. 이를 통해 화면 전환 등을 처리할 수 있습니다.

## 처리방식

- onTap: onTap 콜백은 사용자가 BottomNavigationBar의 아이템을 탭할 때마다 호출됩니다. 이 콜백을 통해 해당 아이템이 선택되었을 때의 동작을 정의할 수 있습니다.
- currentIndex: currentIndex는 현재 선택된 아이템의 인덱스를 가리킵니다. 이 값을 변경하여 BottomNavigationBar의 상태를 관리할 수 있습니다. 예를 들어, 해당 인덱스에 따라 다른 페이지를 표시할 수 있습니다.
