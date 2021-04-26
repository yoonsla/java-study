# Inheritance
# 상속이란?
- 부모 클래스의 변수/메소드를 자식 클래스가 물려받아 그대로 사용 가능하게 하는 것으로 부모 클래스를 superclass, 자식클래스를 subclass라 부른다
- 자식 클래스에서 처리하는 기능이 부모 클래스에서 똑같이 처리되고 있다면 자식 클래스는 이를 상속 받아 그대로 사용할 수 있으며, 코드의 중복을 막는다
- 상속은 **"extends"** 라는 키워드를 사용한다.

```java
자식클래스 extends 부모클래스

public class Inheritance {

    public class ParentClass {
        String parent = "부모야";

        public void Parent() {
            System.out.println("나는 Parent Class의 Parent() 메소드야");
        }
    }

    // extends를 사용하면 메소드 뿐만 아니라 변수까지 사용이 가능하다
    public class ChildClass extends ParentClass{
        String child = "아이야";

        public void Child() {
            Parent(); // 나는 Parent Class의 Parent 메소드야
            System.out.println("나는 " + parent); // 나는 부모야
            System.out.println("나는 Child Class의 Child() 메소드야");
            System.out.println("나는 " + child); // 나는 아이야
        }
    }

    public static void main(String [] args) {
        Inheritance inheritance = new Inheritance();
        ChildClass childClass = inheritance.new ChildClass();
        childClass.Child();
    }
}

실행순서)
1. Parent() 메소드
자식클래스의 Child() 메소드가 부모클래스로부터 상속받은 Parent() 메소드를 호출한다.

2. parent 변수
자식클래스는 부모클래스로부터 상속받은 String 타입의 parent 변수를 출력한다. 

3. Child Class 출력 실행
자식 클래스가 부모클래스의 속성을 그대로 물려받아 사용한다.
```

**but**, 자바는 **다중상속** 을 지원하지 않는다. 
다중상속이란 부모 클래스가 두 개 이상 존재할 수 있다는 것이다.
그래서 자바에는 implements(인터페이스)가 있다.

# implements
implements를 통해 부모클래스에서 선언한 변수/메소드를 자식클래스에 재정의(오버라이딩)를 통해 인터페이스를 구현하여 상속받을 수 있다.

```java
ex:
public class Son implements Mather, Father {...}

public class Inheritance {

    public interface InterExample {
        void makeThis();
        void makeThisWithParam(String name, int age);
    }

    public static class ImplementInterface implements InterExample {

        // implements를 받으면 인터페이스에서 정의한 메소드를 반드시 구현해야 한다.
        @Override
        public void makeThis() { // 구현하지 않으면 오류
            System.out.println("makeThis.....");
        }

        @Override
        public void makeThisWithParam(String name, int age) {
            System.out.println("makeThisWithParam...." + name + "/" + age);
        }
    }

    public static void main(String [] args) {
        ImplementInterface implementInterface = new ImplementInterface();
        implementInterface.makeThis();
        implementInterface.makeThisWithParam("name", 32);
    }
}
```

### extends vs implements
extends는 클래스를 확장하는 것이며 implements는 인터페이스를 구현하는 것이다.

1. extends는 일반 클래스와 abstract 클래스 상속에 사용되고, implement는 interface 상속에 사용된다.
2. class가 class를 상속 받을 땐 extends를 사용하고, interface가 interface를 상속 받을 땐 extends를 사용한다.
3. class가 interface를 사용할 땐 implements를 사용한다.
4. interface가 class를 사용할 땐 implements를 사용할 수 없다.
5. extends는 클래스 한 개만 상속 받을 수 있다.
6. extends 자신 클래스는 부모 클래스의 기능을 사용한다.
7. implements는 여러개 사용 가능하다.
8. implements는 설계 목적으로 구현이 가능하다.
9. implements한 클래스는 implements의 내용을 전부 사용해야 한다.

# 다형성(Polymorphism)
다형성이란 하나의 객체가 여러가지 타입을 가질 수 있는 것을 의미한다.
자바에서는 이러한 다형성을 부모 클래스 타입의 참조 변수로 자식 클래스 타입의 인스턴스를 참조할 수 있도록 구현하고 있다.
오버라이딩, 오버로딩도 다형성 중 하나이다.

# 다이나믹 메소드 디스패치(Dynamic Method Dispatch)
다이나믹 메소드 디스패치는 자바의 테크닉 중 하나로, 런타임에 오버라이딩 된 메소드가 실행되는 것을 말한다.
참조 타입이 부모 타입인 경우에도 동작하기 때문에 런타임 시점에 다형성을 만족하도록 할 수 있다.

```java
 public static class People {
        public void talk() {
            System.out.println("사람을 말을 해");
        }
    }

    public static class Man extends  People{
        @Override
        public void talk() {
            System.out.println("남자도 말을 해");
        }
    }

    public static class Main {
        public static void main(String [] args) {
            People people = new People();
            People man = new Man();

            people.talk();  // People에 정의된 메소드 실행
            man.talk();     // Man에 정의된 메소드 실행(다이나믹 메소드 디스패치)

            // 런타임에는 JVM이 객체의 타입을 파악하고 그 객체에 정의된 메소드를 실행한다.
        }
    }
```

# 추상클래스
추상클래스는 **abstract** 키워드가 추가된 클래스이다.
이 클래슨느 추상 메소드를 포함하고 있을 수도, 아닐 수도 있다.
허나 클래스에 추상메소드가 포함된 경우에는 반드시 그 클래스는 추상클래스여야만 한다.

```java
abstract void 메소드명(변수1, 변수2 ...)

// 기본 형태
public abstract class AbstractTest {
    abstract void test();
}

// 추상클래스의 상속
// 부모
public abstract class Animal {
    public abstract void move();
    
    public void walk() {
        System.out.println("걷는 중");
    }
}

// 자식
public class monkey extends Animal {
    @Override
    public void move() {
        System.out.println("원숭이");
    }
}

public class Main {
    public static void main(String [] args) {
        Monkey monkey = new Monkey();
        monkey.move();  // 원숭이
        monkey.walk();  // 걷는 중
    }
}

```

### 추상클래스 사용 이유
1. 공통적인 메소드나 필드를 하나로 묶어 유지보수성을 높인다.
2. 규격에 맞춰 클래스를 구현할 수 있다.

### 추상클래스 vs 인터페이스
1. 추상클래스는 필드를 정의할 수 있다. 반면 인터페이스의 모든 필드는 **public static final**이다.
2. 추상클래스는 상속이 가능하다. 하지만 인터페이스는 여러 개의 인터페이스를 구현할 수 있다.

# final
java의 **final** 키워드는 변경불가능의 의미를 가진다.
메소드의 경우에는 오버라이드가 불가하다. 

### final 메소드
```java
// final이 선언된 메소드는 자식 클래스에서 재정의하려 할 때 컴파일 오류가 발생한다.
public class ParentTest {
    public void test1() { ... }
    public final void test2 { ... }
    public static void test3 { ... }
    public static final void test4 { ... }
}

public class ChildTest extends parentTest {
    public void test1() { ... } // 가능
    public void test2() { ... } // 불가능
    public void test3() { ... } // 가능
    public void test4() { ... } // 불가능
}
```

### final 클래스
```java
// 상속 금지
// 본인이 만든 클래스를 다른 곳에서 상속 받아서 사용하는 것을 금지하고 싶을 때 사용
public class Student extends Human { // 컴파일 에러 발생
...
}
```

# Object 클래스
- Object 클래스는 java.lang 패키지에 존재하는 것으로 모든 클래스의 직,간접적 슈퍼클래스이다.
- Object 클래스는 매개변수 없는 생성자를 가지고 있다.
- 최상위 클래스이기 때문에 모든 클래스를 받을 수 있다.
- 모든 클래스에서 Object 클래스의 멤버를 사용할 수 있다.

### Object 클래스의 내장 메소드
![image](https://user-images.githubusercontent.com/53419498/116063946-829a1600-a6c0-11eb-8a58-f70689c4d6cc.png)

# String 클래스
- String 클래스에는 문자열과 관련된 작업을 유용하게 사용할 수 있는 메소드가 있다.
- String 인스턴스는 한 번 생성되면 그 값을 읽기만 할 수 있으며 변경할 수는 없다. **(불변 클래스)**
- 즉, 기존 분자열의 내용이 변경되는 것이 아니라 새로운 String 인스턴스가 생성되는 것이다.
![Uploading image.png…]()









