# Data type, Variable, Array
# Data type 이란?
- 해당 데이터가 메모리에 어떻게 저장되고, 프로그램에서 어떻게 처리되어야 하는지를 명시적으로 알려주는 것
- 크게 기본형 타입(primitive type)과 참조형 타입(Reference type)으로 나뉜다

# 기본형(Primitive type)
- 기본값이 있기 때문에 Null이 존재하지 않음, 만약 기본형 타입에 Null을 넣고 싶다면 래퍼 클래스를 활용
- 실제 값을 저장하는 공간으로 스택 메모리에 저장함
- 만약 컴파일 시점에 담을 수 있는 크기를 벗어나면 에러를 발생시키는 컴파일 에러가 발생함

### 논리형 (boolean)
- 길이가 1bit인 논리형 타입으로 true 혹은 false로 나뉨
- default 값은 false이며 Wrapper class는 Boolean

### 정수형
##### byte
- 길이가 8bit인 부호가 있는 정수형 타입으로 범위는 -128 ~ 127
- default 값은 0, Wrapper class는 byte

#### short
- 길이가 18bit인 부호가 있는 정수형 타입으로 범위는 -32768 ~ 32767
- default 값은 0, Wrapper class는 Short

#### int
- 길이가 32bit인 부호가 있는 정수형 타입으로 범위는 -2147483648 ~ 2147483647
- default 값은 0, Wrapper class는 Integer

#### long
- 길이가 64bit인 부호가 있는 정수형 타입으로 범위는 -9223372036854775808 ~ 9223372036854775807
- default 값은 0L, L은 long 타입의 리터럴
- wrapper class는 Long

### 실수형
#### float
- 길이가 32bit인 부호가 있는 실수형 타입으로 범위는 1.40239846e-45f ~3.40282347e+38f
- default 값은 0.0f, f는 float 타입의 리터럴
- wrapper class는 Float

#### double
- 길이가 64bit 인 부호가 있는 실수형 타입으로 범위는 4.94065645841246544e-324~1.79769313486231570e+308
- default 값은 0.0d 이며, d 는 double 타입의 리터럴
- Wrapper class 는 Double

### 문자형
#### char
- 길이가 16bit인 유니코드 문자형 타입으로 범위는 \u0000 ~ \uffff (0 ~ 2^15-1) 
- default 값은 \u0000이며, Wrapper class 는 Character

### 리터럴(Literal)
- 데이터 그 자체
- 변수에 넣는 변하지 않는 데이터를 의미
- String 데이터 타입은 참조형 변수지만 연속적인 문자를 표시하기 위한 리터럴이 제공되고 있음

# 참조형(Reference type)
- 래퍼런스 타입은 new 연산자를 통해 heap 영역에 생성되는 자료형을 의미
- heap 영역에 실제 데이터가 저장되고, 스택 영역에 주소값이 저장됨
- 래퍼런스 타입으로는 클래스, 배열, 인터페이스 등이 있음

### String 클래스
- String 클래스는 참조형에 속하지만 기본형처럼 사용함
- 불변하는 객체이며 데이터를 바꾸는 메소드들은 새로운 String 클래스를 만드는 것
- String 클래스 간의 비교는 equals() 메소드를 사용해야함

### 클래스형 (Class type)

<pre>
<code>
class User {
	private String name;
	User(String name) {
		this.name = name;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
}

public static void main(String[] args) {
    User user1 = new User("yoonsla");
		User user2 = new User("sangyoon");
		System.out.println("1: " + user1);
		System.out.println("2: " + user1.getName());
		user1 = user2;
		System.out.println("3: " + user1.getName());
		user2.setName("yoonsla");
		System.out.println("4: " + user1.getName());
	}
}
</code>
</pre>

- user1을 출력했을 때는 user1의 인스턴스 hashcode값이 출력됨, 주소값이 같으면 해쉬코드 값이 같음
- User 클래스의 데이터 타입은 참조형(class type)
- 주소값을 참조하고 있는 클래스형이기 때문에 user1 = user2를 했을 경우 두 개의 주소값이 같아져, b의 값을 바꿨을 때 a의 값도 변함

### 인터페이스형(Interface type)
- interface는 참조형이기 때문에 자신을 구현한 객체의 주소를 가질 수 있음

### 배열형(Array type)
- 배열형은 기본형 배열, 참조형 배열 모두 만들 수 있음
- 자료형에 대해 []를 선언하여 배열을 지정할 수 있으며 주소값을 가지고 있기 때문에 클래스형과 일치하는 특징을 가지고 있음

# 스코프와 라이프타임
### 스코프
- 스코프 = 영역
- 변수에 대한 접근과 변수가 존재할 수 있는 영역
- 중괄호 { } 로 한 영역이 생성된다면 그 영역에 관한 스코프를 형성함
<pre>
<code>
public static void main(String[] args) {
	int number = 1;
	int number2 = 1;
	System.out.println(number + number2); // 2
	add();
}

public static void add() {
	int number = 3;
	int number2 = 4;
	System.out.println(number + number2); // 7
}
</code>
</pre>

- 만약 변수의 스코프가 없다면 불가능한 소스
- 같은 이름의 변수가 다른 메소드에서 각각 형성되었지만 스코프가 있기에 가능
- 스코프는 {} / () 를 벗어나면 소멸되는 특징을 가지고 있음

#### 멤버 변수(Instance variable)

#### static 변수(Class Variable)

#### 지역 변수(Local Variable)
