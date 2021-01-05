---
layout: post
title:  Java의 Stream
date:   "2021-01-05 21:57:15"
author: Anderson
categories: Code
tag: Java
cover:  "/assets/instacode.png"
---

# Java의 Stream

```java
class Person{
	private String personName;
	public Person(String personName) {
		this.personName = personName;
	}
	public String getName() {
		return personName;
	}
	@Override
	public String toString() {
		return personName;
	}
}

public class StreamTest {

	public static void main(String[] args) {
		int[] arr1 = {1, 2, 3, 4, 5};
		String[] arr2 = {"AA", "BB", "CC"};
		ArrayList<String> arr3 = new ArrayList<String>();
		List<Person> arr4 = new ArrayList<Person>();
		
		arr3.add("Python"); arr3.add("C++"); arr3.add("JavaScript");
		
		arr4.add(new Person("Brown")); arr4.add(new Person("Chris")); arr4.add(new Person("Andy"));
		
		Arrays.stream(arr1).forEach(val-> System.out.println(val+100));
		
		arr3.stream().sorted().forEach(language->System.out.println(language));
		//arr4.stream().sorted().forEach(language->System.out.println(language));	//sorted의 기준을 구현해야 한다
		
		arr3.stream().map(language->language.length()).forEach(langLength->System.out.println(langLength));
		
		System.out.println(Arrays.stream(arr1).sum());
		int count = (int)Arrays.stream(arr2).count();	//count()는 long을 반환한다
		System.out.println(count);
		
		arr4.stream().filter(person->(person.getName() == "Andy")).forEach(name->System.out.println(name));
		System.out.println(Arrays.stream(arr1).reduce(0, (a, b)->a+b));	// 요소를 하나씩 줄이며 누적연산 수행
	}
}
```

## Stream과 BinaryOperator

- 경우1) 
```java
public class BinaryOperatorTest {

	public static void main(String[] args) {
		
		String[] lang = {"C++", "TypeScript", "Ruby"};
		
		String langLength = Arrays.stream(lang).reduce("", (lang1, lang2)->{
			if(lang1.getBytes().length > lang2.getBytes().length) {
				return lang1;
			}
			else {
				return lang2;
			}
		});
		System.out.println(langLength);
	}
}
```

- 경우2) BinaryOperator 사용

```java
class CompareLanguage implements BinaryOperator<String>{

	@Override
	public String apply(String t, String u) {
		if(t.getBytes().length > u.getBytes().length) {
			return t;
		}
		else {
			return u;
		}
	}
}

public class BinaryOperatorTest {

	public static void main(String[] args) {
		
		String[] lang = {"C++", "TypeScript", "Ruby"};
		
		String langLength = (Arrays.stream(lang).reduce(new CompareLanguage())).get();
		System.out.println(langLength);
	}
}
```