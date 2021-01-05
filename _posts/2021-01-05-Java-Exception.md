---
layout: post
title:  Java의 예외처리
date:   "2021-01-05 21:52:15"
author: Anderson
categories: Code
tag: Java
cover:  "/assets/instacode.png"
---

# Java의 예외처리

- 가동 중인 실행 파일의 불능 방지
- 예외 상황 발생 시 로그를 기록할 있는 기회 부여

## 예외처리의 기본 구조

1) try-catch-finally : {} 구조

```java
public class exceptionTest {

	public static void main(String[] args){
		
		FileInputStream myFile = null;
		
		try {
			myFile = new FileInputStream("C:\\a.txt");
		}catch(FileNotFoundException e) {
			System.out.println(e.toString());
		}finally {
			try {
				myFile.close();
			}catch(Exception e) {
				System.out.println(e.toString());
			}
		}
	}
}
```
2) try-catch : ()구조, try-with-resource 사용
```java
public class exceptionTest {

	public static void main(String[] args){
		
		try(FileInputStream myFile = new FileInputStream("C:\\b.txt")) {
		}catch(FileNotFoundException e) {
			System.out.println(e.toString());
		} catch (IOException e) {
			System.out.println(e.toString());
		}
	}
}
```
java7부터 반영되었고, 해당 예외처리 리소스가 AutoCloserble을 구현한 경우 close()가 자동으로 호출
FileInputStream는 AutoCloserble를 구현하였음

## 사용자 정의 예외처리

JDK에서 지원하는 예외 클래스 이외의 사용자 정의가 필요한 경우
JDK의 최상의 클래스 "Exception"을 상속하여 구현한다

```java
class SerialException extends Exception{
	public SerialException(String EceptionMessage) {
		super(EceptionMessage);
	}
}

class MakeSerialNumber{
	private String serialNumber;
	public void setSerialNumber(String serialNumber) throws SerialException{
		//예외조건1) 5자리 초과, 예외조건2) null이면 안됨
		if(serialNumber == null) {
			throw new SerialException("null은 수용할수 없습니다");
		}
		else if(serialNumber.length() > 5) {
			throw new SerialException("시리얼 번호가 4자리 미만입니다");
		}
		this.serialNumber = serialNumber;
	}
}

public class MakeSerialNumberTest {

	public static void main(String[] args) {
		
		MakeSerialNumber mySerial = new MakeSerialNumber();
		String mySerialNumber = null;
		
		try {
			mySerial.setSerialNumber(mySerialNumber);
		} catch (SerialException e) {
			System.out.println(e.toString());
		}finally{
			System.out.println("종료 되었습니다");
		}
	}
}
```

## Etc...

- throws는 예외처리를 다른 영역으로 미루는 것
- throw는 예외를 고의적으로 발생 시키는 것