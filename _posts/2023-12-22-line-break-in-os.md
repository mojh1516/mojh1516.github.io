---
title: "Java에서 OS별 줄바꿈 적용"
categories:
  - Java
tags:
  - Java
excerpt: "Java에서 OS별로 줄바꿈을 적용 하는 방법"
---

OS별로 줄바꿈 하는 방법이 달라요.

Windows는 CRLF, Mac은 LF 방식이에요.

쉽게 말해 Windows는 줄바꿈을 하기위해 Home 한 번, Enter 한 번 누르는 느낌이에요.
맨 왼쪽으로 이동하고 한 줄 아래로 이동한다는 내용이죠.

Mac은 그냥 Enter 한 번만 입력하는 방식이에요.
Linux도 Mac과 같은 LF 방식이에요.

여기서 문제는 환경이에요. 개발을 할 땐 Windows를 사용하고, 운영을 할 땐 Linux를 사용한다고 했을때 발생하죠.
개발할 때 String 내에 줄바꿈을 하기위해 아래와 같이 작성하게 될거에요.

```java
String str = "줄\r\n바꿈";
```

하지만 Linux에선 LF 방식을 사용해요. LF 방식은 아래와 같이 작성해요.

```java
String str = "줄\n바꿈";
```

이렇게 다양한 줄바꿈 형태로 코드를 작성하면 다양한 문제들이 발생할 수 있어요.
이러한 문제를 방지하기 위해 Java에선 OS환경에 맞는 줄바꿈을 제공하는 System함수가 존재해요.

```java
String str = "줄" + System.lineSeparator() + "바꿈";
```

위와 같이 System.lineSeparator() 함수를 사용하면 OS환경에 맞게 CRLF 또는 LF로 자동 변환 해줘요.