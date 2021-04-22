# Class
### 클래스란?
- 객체를 정의하는 틀 또는 설계도 
- 객체의 상태를 나타내는 필드와 객체의 행동을 나타내는 메소드로 구성됨
- 필드 : 클래스에 포함된 변수
- 메소드 : 어떠한 특정 작업을 수행하기 위한 명령문의 집합

```java
public class Body {
  
  // 필드
  public String ear;
  public String eye;
  public String leg;
  
  // 메소드
  public void listen() {
    System.out.println("듣는다");
  }
  
  public void see() {
    System.out.println("본다");
  }
  
  public void walk() {
    System.out.println("걷는다);
  }
}
```

#### 인스턴스
- 자바에서는 클래스를 사용하기 위해 우선 해당 클래스 타입의 객체를 선턴해야함
- 이렇게 클래스로부터 객체를 선언하는 과정을 클래스의 인스턴스 화라고 함
- 인스턴스란 메모리에 할당된 객체를 의미

#### 객체
- 객체란 물리적으로 존재하거나 추상적으로 생각할 수 있는 것 중에서 자신의 속성을 가지고 있고 다른 것과 식별 가능한 것
- 객체는 속성과 동작으로 구성되어 있음

```java
public class Main {
  public static void main(String [] args) {
    // Body 클래스 객체 생성
    Body body = new Body();
    body.ear = "귀";
    body.eye = "눈";
    body.leg = "다리";
    
    // 객체를 통해 Body 클래스의 메소드 호출 및 적용
    body.listen();
    body.see();
    body.walk();
  }
}
```
