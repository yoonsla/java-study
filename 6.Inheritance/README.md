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



