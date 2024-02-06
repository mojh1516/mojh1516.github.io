---
title: "nginx config 수정 후 적용"
categories:
  - nginx
tags:
  - nginx
excerpt: "nginx config 파일을 수정 후 적용 하는 방법"
---

웹 서버인 nginx를 사용하게되면 config파일(conf)을 자주 변경하게 되요.

설정파일들을 수정하고 난뒤에는 정상적으로 적용이 될 수 있게 해줘야해요.

적용하는 방법은 두 가지가 있어요

```
service nginx restart
service nginx reload
```

restart 명령어는 service를 재기동 하기 때문에 약간의 딜레이나 멈춤이 있을 수 있고, 만약 설정 파일에 문제가 있으면 service가 재기동 되지 않고 아예 멈춰 버리죠.

reload 명령어는 service를 재기동 하지 않고 설정 파일들만 새로고침하는 방식이에요.

또, 설정 파일에 문제가 있어도 service가 중단되지 않고 기존 설정파일을 상대로 정상적으로 작동해요.

이렇기 때문에 reload 명령어는 설정 파일의 문제를 알 수 없는 경우가 종종 있어요.

그래서 개발서버와 운영서버로 나뉘어진 서비스라면 개발서버에서 restart로 확인하고
운영서버에서 reload로 적용하는게 좋은 방법같아 보여요.