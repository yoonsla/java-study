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

# 참조형(Reference type)




https://gbsb.tistory.com/6#:~:text=%ED%83%80%EC%9E%85(Data%20type)%EC%9D%B4%EB%9E%80%20%ED%95%B4%EB%8B%B9,%EC%B0%B8%EC%A1%B0%ED%98%95%20%ED%83%80%EC%9E%85%EC%9D%B4%20%EC%9E%88%EB%8B%A4.
