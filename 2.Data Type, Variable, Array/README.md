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
```java
pulbic class Test {
	int num = 10; // 멤버 변수
	static int num2 = 20; // static 변수
	public static void main(String[] args) {
		int number = 1; // 지역 변수
		int number2 = 1;
		System.out.println(number + number2); // 2
		add();
	}

	public static void add() {
		int number = 3;
		int number2 = 4;
		System.out.println(number + number2); // 7
	}
}
```

- 만약 변수의 스코프가 없다면 불가능한 소스
- 같은 이름의 변수가 다른 메소드에서 각각 형성되었지만 스코프가 있기에 가능
- 스코프는 {} / () 를 벗어나면 소멸되는 특징을 가지고 있음

#### 멤버 변수(Instance variable)
- 클래스 내부와 모든 메소드 및 블록 외부에 선언된 변수
- static 메소드를 제외한 클래스 어디서든 사용 가능
- 라이프타임은 객체가 메모리에 남아있을 때까지

#### static 변수(Class Variable)
- 클래스 내부와 모든 메소드 및 블록 외부에서 static으로 선언된 변수
- 클래스 어디에서나 사용 가능
- 라이프타임은 프로그램이 끝날 때까지, 또는 클래스가 메모리에 로드되는 동안

#### 지역 변수(Local Variable)
- 멤버 변수와 static 변수를 제외한 모든 변수
- 선언 된 블록 내에서 사용 가능
- 라이프타임은 컨트롤이 선언된 블록을 떠날 때까지

# 타입변환
- Java의 타입 변환에는 자동 타입 변환(promotion)과 강제 타입 변환(casting)

### 자동 타입 변환(Promotion)
- 크기가 작은 자료형을 큰 자료형에 대입할 때, 자동으로 작은 자료형이 큰 자료형으로 변환되는 현상
- 타입 크기 (byte < short < int < long < float < double)

```java
public class promotionTest {
	public static void main(String [] args) {
		byte bVal = 4;
		int intVal = bVal;	// 자동으로 변환되어 int 타입으로 변함
		double dVal = intVal;	// 실수형으로 바뀌어 .0이 뒤에 붙음
		char charVal = 'A';
		intVal = charVal;	// 문자 타입을 int로 바꾸면 유니코드 값이 저장됨
	}
}
</code>
</pre>

### 강제 타입 변환(Casting)
- 크기가 큰 자료형을 작은 자료형으로 변환할 때는 강제로 변환을 해야 함(Casting)

<pre>
<code>
public class CastingTest {
	public static void main(String [] args) {
		int intVal = 103029770;
		byte bVal = intVal; 	// 컴파일 에러 발생
		byte bVal2 = (byte)intVal;
	}
}
```

# 1차 배열, 2차 배열 선언
- 배열이란 같은 자료형의 데이터들을 연속된 공간에 저장하기 위한 자료구조
- 연관된 데이터를 그룹핑하는 역할을 하며, 중복된 변수의 선언을 줄이고 반복문과 같은 복잡한 계산 과정을 편하게 처리해줌
- 1차원 배열은 스택 영역에 배열의 주소값이 담겨있고 힙영역부터 배열의 길이만큼 할당되어 있음
- 2차원 배열은 스택 영역에 배열의 주소값이 담겨있고 주소값이 가리키고 있는 힙영역부터 배열의 길이만큼 하위 배열의 주소값이 담겨있음

```java
public class ArrayTest {
	public static void main(String [] args) {
		int [] arr;
		int arr2[];
		int [] arr3 = new int[3];
		arr[0] = 1;
		arr[1] = 2;
		arr[2] = 3;
		int [] arr4 = {1,2,3};
		int [] arr5 = new int[]{1,2,3};
		
		int [][] arrs;
		int arrs2 [][];
		int [][] arrs3 = new int[2][3];
		int [][] arrs4 = {{1,2,3},{4,5,6}};
		int [][] arrs5 = new int [][]{{1,2,3},{4,5,6}};
	}
}
```

# 타입추론
- Java 10에서 var 라는 Local Variable Type-inference 등장
- 코드 작성 시 타입이 정해지지는 않았지만 컴파일러가 그 타입을 유추하는 것
- "var"는 지역변수 이면서 선언과 동시에 초기화가 되어야 함
- 따라서 멤버변수, 메소드의 파라미터, 리턴 타입으로 사용 불가

```java
public Class TypeTest {
	public static void main(String[] arsg) {
		var booleanVal = true;
		var intVal = 1;
		var doubleVal = 10.0;
		var charVal = 'A';
		var strVal = "Hello World";

		Object result = booleanVal;
		System.out.println("boolenVal: " + (result instanceof Boolean)); 	// true

		result = intVal;
		System.out.println("intVal: " + (result instanceof Integer));		// true

		result = doubleVal;
		System.out.println("doubleVal: " + (result instanceof Double));		// true

		result = charVal;
		System.out.println("charVal: " + (result instanceof  Character));	// true

		result = strVal;
		System.out.println("strVal: " + (result instanceof  String));		// true
	}
}
```
