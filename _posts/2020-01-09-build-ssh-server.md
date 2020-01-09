---
layout: post
title:  "SSH 서버 구축하기"
author: dave
categories: [ Development ]
tag: [Ubuntu, Development, SSH, Terminal, 우분투, 개발환경, 터미널]
image: assets/images/posts/2020-01-09-build-ssh-server/0001.jpg
description: "Ubuntu 서버에 SSH를 통해 원격 접속할 수 있는 방법을 정리"
featured: true
hidden: true
---

터미널을 통해 우분투에 접속해 작업을 진행해야 할 상황이 생겼고, 검색을 통해 간단히 정리된 포스트를 찾았다. 아래는 해당 포스트의 가이드를 따라 진행하며 간략히 정리한 내용이다.



## 작업환경
작업을 진행한 환경은 다음과 같다.

> Server: **Ubuntu 16.04.5**  
> Client: **Mac OS X**

## SSH 설치 (Ubuntu)
다음 구문으로 관련 패키지가 설치되어 있는지 확인 후 필수 패키지인 openssh-server를 설치한다.

```
# 설치 패키지 확인
$ dpkg -l | grep openssh 

# 필수 패키지 설치
$ sudo apt-get update
$ sudo apt-get install openssh-server
$ dpkg -l | grep openssh
```

이제 서비스를 구동시키고 정상적으로 동작하는지 확인한다.

```
# 서비스 구동
$ sudo service ssh start

# 실행 중인 서비스 목록 확인
$ service --status-all | grep + 

# 점유 포트 확인
$ sudo netstat -antp 
```

이제 접속할 서버가 준비됐으니 클라이언트에서 접속을 시도한다.


## 원격 접속 (Mac OS X)
터미널을 켜고 다음 구문을 통해 원격 접속을 시도한다.

```
$ ssh [id]@[address]
```


## 참고
[[우분투 16.04] SSH서버 구축하기(SSH 접속 설정)](https://jimnong.tistory.com/713)
