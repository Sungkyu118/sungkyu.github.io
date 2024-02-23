---
layout: post
title: Container에서 BoxDecoration을 사용할 때, 배경색 적용 시 에러
date: 2024-02-20 21:00:00 +0900
category: Flutter
permalink: /flutter/containercolor
tags: [Container, BoxDecoration]
---

Container Widget에서 color값을 설정한 상태로, decoration값에 BoxDecoration을 주었을 때, 에러가 발생한다.

![error1](/assets/img/container_error1.png)

원인은 BoxDecoration Widget에서도 배경색을 적용할 수 있기 때문에, 중첩 적용을 막기위한 것이다.

해결방법은 color값을 Container에서 주지 말고 decoration의 BoxDecoration Widget에 주면 된다.

![error2](/assets/img/container_error2.png)
