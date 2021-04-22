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
- 클래스에서 메소드란 어떠한 특정 작업을 수행하기 위한 명령문의 집합
- 즉, 메소드를 사용하면 중복되는 코드의 반복적인 프로그래밍을 피할 수 있음
- 내부에서 사용하는 메소드는 접근제어자를 private으로 설정하고 그 외에는 상황에 맞게 public, default, protected로 설정

##### 오버로딩 & 오버라이딩
1. 오버로딩
- 같은 이름의 메소드 여러개를 가지면서 매개변수의 유형과 개수가 다르도록 하는 기술
- 같은 이름의 메소드를 여러개 정의하고 매개변수의 유형과 개수를 다르게 하여 다양한 유형의 호출에 응답할 수 있음

```java
class overloadingTest {
	void cat() {
		System.out.println("매개변수 없음");
	}
	void cat(int a, int b) {
		System.out.println("매개변수 : " + a + "/" + b);
	}

	void cat(String c) {
		System.out.println("매개변수 : " + c);
	}
}

public class overTest {
  public static void main(String [] args) {
    SpringApplication.run(TestApplication.class, args);

		overloadingTest ot = new overloadingTest();
		ot.cat();             // cat() 호출
		ot.cat(20,80);        // cat(int, int) 호출
		ot.cat("고양이는 귀여워");     // cat(String) 호출
  }
}
```

2. 오버라이딩
- 상위 클래스가 가지고 있는 메소드를 하위 클래스가 재정의하여 사용하는 것

```java
class Woman {
	public String name;
	public int age;

	public void info() {
		System.out.println("여자의 이름은 " + name + "이며 나이는 " + "age" + "입니다");
	}
}

class Job extends Woman{
	String job;

	public void info() {
		super.info();
		System.out.println();
	}
}

public overTest {
  public void main(String[] args) {
    Job job = new Job();
    Job job = new Job();
		job.name = "미숙이";
		job.age = 30;
		job.job = "프로그래머";
		job.info();
  }
}
```

##### 접근제어자
java에서 정보 은닉을 구체화할 수 있는 방법
- private : 같은 클래스 내에서만 접근 가능
- default : 같은 패키지 내에서만 접근 가능
- protected : 같은 패키지 내 및 다른 패키지에서 선언한 데이터가 속해있는 클래스를 상속받은 자식 클래스에서 접근 가능
- public : 어디서든 접근 가능

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

### 객체와 인스턴스 관계
클래스로부터 객체를 만드는 과정을 클래스의 인스턴스화라고 함
클래스 --> 인스턴스화 ---------------> 인스턴스(객체) 

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

객체 생성
  - 클래스명 
  - 변수명 = new 클래스명();

new 키워드
  - 클래스 타입의 인스턴스(객체)를 생성해 주는 역할
  - Heap 영역에 데이터를 저장할 공간 할당 및 그 공간의 참조값을 객체엑 반환, 생성자 호출

this
  - 현재 클래스의 인스턴스를 의미
  - 즉, 현재 클래스의 멤버 변수를 지정할 때 사용, 객체 자신

```java
public class Parent {
  private String mother;
  private String father;
  
  public Parent() {
    this.mother = "mother";
    this.father = "father";
  }
  
  public Parent(String mother, String father) {
    this.mother = mother;
    this.father = father;
  }
  
  public String toString() {
    return this.mother + "/" + this.father;
  }
}
```

super
  - 자식 클래스가 자신을 생성할 때 부모 클래스의 생성자를 불러 초기화 할 때 사용

```java
public class Child extends Parent {
  private String son;
  private String doughter;
  
  public Child() {
    this("doughter","son");
  }
  
  public Child(String doughter, String son) {
    // parentClass 생성자 호출
    super("child.mother", "child.father");
    this.doughter = doughter;
    this.son = son;
  }
  
  public String toString() {
    return super.getFather() + "/" + super.getMother() + "/" + this.doughter + "/" + this.son;
  }
}
```

### 내부 클래스
하나의 클래스 내부에 선언된 또 다른 클래스

```java
class Outer { // 외부 클래스
  ...
  class Inner { // 내부 클래스
    ...
  }
}
```

#### 내부 클래스 장점
- 내부 클래스에서 외부 클래스의 멤버에 손쉽게 접근할 수 있음
- 서로 관련 있는 클래스를 논리적으로 묶어서 표현함으로써 코드의 캡슐화 증가
- 외부에서는 내부 클래스에 접근할 수 없으므로 코드의 복잡성을 줄일 수 있음

#### 내부 클래스 종류
1. 정적 클래스
2. 인스턴스 클래스
3. 지역 클래스
4. 익명 클래스

```java
public class InnerExam {
  
  class Cal { - 중첩 클래스
    int value = 0;
    public void plus() {
      value++;
    }
  }
  
  Cal cal = new Cal();
  cal.plus();
  System.out.println(cal.value);
  
  // static class Cal{
  //	int value = 0;
  //	public void plus() {
  //		value++;
  //	}
  // }
  
  // 메소드 안에 클래스 선언
  // public void exec() {
  //	class Cal{
  //		int value = 0;
  //		public void plus() {
  //			value++;
  //		}
  //	}
}
  
  public static void main(String[] args) {
    // 내부 클래스 - 중첩 클래스
    InnerExam exam = new InnerExam();
    InnerExam.Cal cal = exam.new Cal();
    cal.plus();
    System.out.println(cal.value);
    
    // 내부 클래스 - static 클래스
    // InnerExam.Cal cal = new InnerExam().Cal();
    // cal.plus();
    // System.out.println(cal.value);
    
    // InnerExam t = new InnerExam3();
    //t.exec();
  }
}
```
