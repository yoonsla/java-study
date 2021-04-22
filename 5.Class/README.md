# Class
### 클래스란?
- 객체를 정의하는 틀 또는 설계도 
- 객체의 상태를 나타내는 필드와 객체의 행동을 나타내는 메소드로 구성됨
- 필드 : 클래스에 포함된 변수
- 메소드 : 어떠한 특정 작업을 수행하기 위한 명령문의 집합

```java

접근제어자 class 클래스 이름 {

}

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

### 클래스 구성요소
#### 필드
클래스 내에서 필드는 선언된 위치에 따라 다음과 같이 구분됨
1. 클래스 변수
2. 인스턴스 변수
3. 지역 변수

```java
public Class Car {
  static int modelOutput; // 클래스 변수
  String modelName;       // 인스턴스 변수
  
  public void carList() {
    int something = 10;   // 지역 변수
  }
}
```

#### 메소드
클래스에서 메소드란 어떠한 특정 작업을 수행하기 위한 명령문의 집합
즉, 메소드를 사용하면 중복되는 코드의 반복적인 프로그래밍을 피할 수 있음

```java
접근제어자 반환타입 메소드이름(매개변수목록) {

}

public class Car {
  private int curentSpeed;
  private int accelerationTime;
  
  public void accelerate(int speed, int second) {   // 선언부
    // 구현부
    System.out.prinlin(second + "초간 속도를 시속" + speed + "로 가속");
  }
}
```

#### 생성자(constructor)
- 클래스를 가지고 객체를 생성하면 해당 객체는 메모리에 즉시 생성됨
- 하지만 이렇게 생성된 모든 인스턴스 변수가 아직 초기화 되지 않은 상태임
- 따라서 자바에서는 객체의 생성과 동시에 인스턴스 변수를 원하는 값으로 초기화할 수 있는 생성자라는 메소드를 제공함
- 자바에서 생성자의 이름은 해당 클래스의 이름과 같아야 함
- 생성자는 반환값이 없음
- 생성자는 매개변수에 따라 여러개가 정의 될 수 있음

``` java
// 클래스 이름() {...} -> 매개변수가 없는 생성자 선언
// 클래스 이름(인수1, 인수2, ...) {...} 매개변수가 있는 생성자 선언

Car(String modelName) {}
Car(String modelName, int modelYear) {}
...
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


