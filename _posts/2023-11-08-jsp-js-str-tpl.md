---
title: "Jsp에서 Javascript Template Literals 사용"
categories:
  - Javascript
tags:
  - Javascript
excerpt: "Jsp에서 Javascript Template Literals을 사용하는 방법"
---

Javascript Template Literals(템플릿 리터럴)은 ES6 문법이에요.

이번 포스트에는 템플릿 리터럴을 Jsp에서 사용하는 방법을 작성하려고 해요.

우선 템플릿 리터럴은 아래 코드처럼 사용해요.

```javascript
let str = '템플릿';
console.log(`${str} 리터럴`);
```

이렇게 ``(백틱)을 사용해서 변수들을 하나의 문자열처럼 표현할 수 있어요.

코드의 가독성이 훨씬 좋아지죠.

그렇다면 Jsp에서는 이 템플릿 리터럴을 어떻게 사용할까요?

```html
<script>
  let str = '템플릿';
  console.log(str + ' 리터럴');
</script>
```

위 코드와 같이 + 연산자를 사용했어요. 이는 가독성이 좋지않고, 더해야 하는 변수가 많으면 코드가 길어지면서 코딩에 실수가 생길수도있죠.

또 Jsp에는 템플릿 리터럴 처럼 사용하는 jstl 문법이 있어서 템플릿 리터럴이 적용되지 않아요.

그래서 Jsp에서도 템플릿 문자열을 적용할 수 있는 방법을 찾아봤어요.

```html
<script>
  let str = '템플릿';
  console.log(`${'${str}'} 리터럴`);
</script>
```

이렇게 하면 Jsp에서도 템플릿 문자열을 사용할 수 있어요.

물론 이것도 가독성이 좋진 않아요. 그래서 Jsp안에서 script 코드를 짜지 말고 script 파일을 따로 include 시켜 사용하는걸 추천해요.