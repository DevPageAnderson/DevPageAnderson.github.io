---
layout: post
title:  Java의 Class Path
date:   "2021-01-05 21:47:15"
author: Anderson
categories: Code
tag: Java
cover:  "/assets/instacode.png"
---

# Java의 Class Path

### 본 내용은 윤성우 님의 "난 정말 Java를 공부한적이 없다구요!"를 참조하였습니다
<br>
## 환경변수
윈도우에서 기본적으로 적용하는 프로그램, 예를 들어 메모장이나 계산기 같은 것은 어떤 경로에서든 실행이 가능하다

* cmd창에서
    - C:\Users\sonkh>calc.exe
    - C:\Users\sonkh>

위와 같은 것이 가능한 이유는 환경변수 path에 해당 실행파일의 경로가 지정되어 있기 때문이다

* cmd창에서 환경변수 확인
    - C:\Users\sonkh>echo %path%

환경변수의 path는 .exe파일을 찾는 경로이고 class path는 .class파일을 찾는 경로이다

## class path (.class 파일 검색 경로 지정)

* cmd창에서
    - C:\Users\sonkh>echo %classpath% <br>
    (결과가 %classpath% 이면 지정된 class path가 없다는 의미이다)

* class path 설정 방법

    1) 작업 경로로 이동하기
    - C:\Users\sonkh>cd C:\MyWork

    - C:\MyWork>set classpath=.;C:\MyWork\subWork; (절대경로)
    - C:\MyWork>set classpath=.;.\subWork; (상대경로)<br>
    (참고로 .는 cmd가 현재 위치하는 곳을 의미한다)

위같은 방법 대신 제어판에서 UI를 통해 설정이 가능하나, 다수의 PC에 동일한 설정을 수작업으로 하는 것이 어려우므로 배치파일을 생성하여 설정을 자동화 할수 있다

* setting.bat
    - javac *****.java (컴파일 진행)
    - md myDirectory
    - copy AAA.class .\myDirectory\AAA.class
    - copy BBB.class .\myDirectory\BBB.class
    - del AAA.class
    - del BBB.class
    - set classpath=.;.\myDirectory (상대경로)
    - java *****
    - pause

