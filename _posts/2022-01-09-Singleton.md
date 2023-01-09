---
layout: post
title: "싱글턴 패턴(Singleton pattern)"
author: "Paul Le"
categories: cs
tags: [software design pattern]
image: arctic-1.jpg
---

# 싱글턴 패턴(Singleton pattern)이란?
하나의 클래스에 관해 오직 하나의 인스턴스만 생성되도록 하는 소프트웨어 디자인 패턴이다. 
여러 모듈이 클래스를 이용하더라도 최초 한번만 인스턴스를 생성하고, 이후 이미 생성되어있는 인스턴스를 사용한다.  

# 싱글턴 패턴의 장점
하나의 인스턴스를 여러 쓰레드 또는 서로 다른 모듈들이 공유하여 사용하기 때문에 인스턴스 생성에 드는 비용이 줄어든다.
이미 생성된 인스턴스를 사용할 때 속도가 보다 빠르다.
인스턴스가 단 하나임을 보장한다.  


# 싱글턴 패턴의 단점
단위 테스트를 할 때는 각 태스트가 독립적으로 진행되어야 하는데, 싱글톤 패턴은 하나의 인스턴스를 기반으로 구현되므로 독립적인 인스턴스를 만들기가 어렵다.
의존성이 높아진다.  

# 언제 싱글턴 패턴을 사용할까?
공통된 객체를 여러개 생성해 사용하는 경우 
(생성에 비용이 많이 드는 객체를 여러 개 생성하는 경우)
(같은 정보를 가진 객체를 여러번 생성해 사용하는 경우)
프로그램 내에서 하나의 객체만 존재해야 하는 경우  

# 싱글턴 패턴의 구현(Java)
1.Eager Initialization
클래스가 Class Loader에 의해 생성될 때 객체가 생성되게 한다.

2.Lazy Initialization
선언 시 객체를 생성하지 않고, 사용 시 객체를 생성한다.

3.Inner Class 사용

```java
class Singleton {

  // 생성자 접근 제한
	private Singleton() {}

  // Inner Class 사용
	private static class SingleInstanceHolder {
			private static final Singleton INSTANCE = new Singleton();
	}
	
  // 인스턴스 획득 메서드
	public static Singleton getInstance(){
	    return SingleInstanceHolder.INSTANCE;
	}
}
```

# 출처
면접을 위한 CS 전공지식 노트 | 주홍철
https://velog.io/@dailyzett/singleton
https://velog.io/@seongwon97/%EC%8B%B1%EA%B8%80%ED%86%A4Singleton-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80
https://ko.wikipedia.org/wiki/%EC%8B%B1%EA%B8%80%ED%84%B4_%ED%8C%A8%ED%84%B4
https://devmoony.tistory.com/43
