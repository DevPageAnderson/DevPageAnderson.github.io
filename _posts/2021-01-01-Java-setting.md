---
layout: post
title:  Java 개발환경 구축 (JDK)
date:   "2021-01-02 18:05:15"
author: Anderson
categories: Code
tag: Java
cover:  "/assets/instacode.png"
---

### Java의 개발 환경 준비

## 1) JDK 다운로드

* Edition
    - SE : standard edition
    - EE : enterprise edition
    - ME : micro edition

## 2) JDK 설치

설치 경로를 잘 기억해 두자
: C:\Program Files\Java\jdk-13.0.2\bin
: javac.exe, java.exe가 있어야 한다

## 3) 환경변수 설정

제어판 -> 시스템 -> 고급 시스템 설정

PATH에 C:\Program Files\Java\jdk-13.0.2\bin; 추가

## 4) cmd창 열기

java
javac

## 5) Java 코드 작성

메모장에서 

```java
class FirstJavaProgram{
    public static void main(String[] args){
        System.out.println("Welcome to Java!");
    }
}
```

작성 후 원하는 저장 경로에 작업 폴더 생성 및 저장
.java

## 6) cmd 경로 변경

## 7) 컴파일
javac FirstJavaProgram.java
: FirstJavaProgram.class 파일이 생성

## 8) 실행
java FirstJavaProgram
