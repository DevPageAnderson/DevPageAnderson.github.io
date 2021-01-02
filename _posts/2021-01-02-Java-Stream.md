---
layout: post
title:  Java의 Stream
date:   "2021-01-02 05:52:12"
author: Anderson
categories: Code
tag: Java
cover:  "/assets/instacode.png"
---

스트림은 반복자의 하나로 iterator와 비슷한 기능을 갖으나 아래와 같은 차이점이 있다

* Stream과 iterator의 차이점
    - 람다식으로 요소를 처리 할 수있다
    - 병렬 처리가 용이하다

자바8에서 도입되었고 자료구조의 요소를 하나씩 참조해서 처리할수 있도록 한다
생성한 스트리은 재사용 불가
비파괴
중간 연산(filler(), map())과 최종연산(forEach, count(), sum())으로 구성

* 용법
    - 1) 배열
        Arrays.stream을 사용하여 스트림을 생성(Arrays클래스 static 메소드 stream)
    - 2) 컬렉션 인스턴스(String 또는 사용자 정의 class의 리스트)
        stream 메소드를 사용하여 스트림을 생성

``` java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.DoubleStream;
import java.util.stream.IntStream;
import java.util.stream.Stream;

class Person{
	private String personName;
	public Person(String personName) {
		this.personName = personName;
	}
	@Override
	public String toString() {
		return personName;
	}
}
public class Control {

	public static void main(String[] args) {
		
		int[] arr1 = {1, 2, 3};
		double[] arr2 = {1.1, 2.2, 3.3};
		String[] arr3 = {"AA", "BB", "CC"};
		ArrayList<String> arr4 = new ArrayList<String>();
		List<Person> arr5 = new ArrayList<Person>();
		
		IntStream myStream1 = Arrays.stream(arr1);
		myStream1.forEach(a->System.out.println(a+100));
		
		DoubleStream myStream2 = Arrays.stream(arr2);
		myStream2.forEach(b->System.out.println(b+10));
		
		Stream<String> myStream3 = Arrays.stream(arr3);
		myStream3.forEach(str->System.out.println(str + ", **"));
		//Arrays.stream(arr3).forEach(str->System.out.println(str + ", **"));
		
		arr4.add("C++");
		arr4.add("JavaScript");
		arr4.add("Python");
		Stream<String> myStream4 = arr4.stream();
		myStream4.forEach(str->System.out.println(str + ", language"));
		
		arr5.add(new Person("Father"));
		arr5.add(new Person("Mother"));
		arr5.add(new Person("Baby"));
		Stream<Person> myStream5 = arr5.stream();
		myStream5.forEach(p->System.out.println(p));
	}
}
``` 
