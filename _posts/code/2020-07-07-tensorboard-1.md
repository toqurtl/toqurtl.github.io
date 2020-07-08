---
layout: post
title: "서버의 텐서보드를 로컬에서 모니터링"
categories:
  - Code
tags:
  - tensorflow
  - tensorboard
---

우선 서버 환경에서 텐서보드를 실행 (로그 경로 지정)

```md
$ tensorboard --logdir="./log" 
```

서버에서는 `http://localhost:6006` 통해 접속 가능하며 원격에서도 6006 포트로 접속이 가능함. 방화벽으로 막혀있을 경우 방화벽을 해제하거나, ssh로 포트 포워딩을 이용

원격 pc의 16006 포트를 이용할 경우 16006 포트를 만들고 아래와 같이 이 포트와 서버의 6006 포트를 ssh로 연결

```md
ssh -L 16006:localhost:6006 [ID]@[ServerIP] -p [port]
```

원격 pc에서 `http://localhost:16006`를 통해 접속 가능