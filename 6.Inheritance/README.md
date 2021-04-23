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



