# Control Flow Statements
# 제어문이란?
프로그램 실행 흐름을 개발자가 원하는 방향으로 바꿀 수 있도록 하는 것
일반적으로 조건식과 실행 구문인 중괄호(블록, {})으로 구성되어 있음

### 조건문
주어진 조건에 따라 애플리케이션을 다르게 동작하도록 하는 것

#### if문
```java
if(조건식) {
  // 조건식이 true일 경우 실행 되는 영역
}

int number = 0;
if (number < 0) {
...
}
```

#### if-else문
if = 만약
else = 그밖에, 그외에

```java
int num = 0;
if(num < 0) {
  // true일 경우 실행 되는 영역
} else {
  // 이외의 경우 실행 되는 영역
}
```

#### if-else if-else문
```java
int num = 0;
if(num < 0) {
  // if 조건식에 대해 true일 경우 실행되는 영역
} else if (num > 0{
  // else if 조건식에 대해 true일 경우 실행되는 영역
} else {
  // 그 외에 실행되는 영역
}
```

### 중첩 if문
```java
int num = 2;
if (num > 0) {
  // 첫 번째 조건식을 만족할 때 
  if (num % 2 == 0) {
    // 두개의 조건 모두를 만족할 때
  }
}
```

### switch문
- 하나의 조건에 따라 여러 방향으로 분기하고자 하는 경우
코드의 가독성을 높일 수 있음
- break를 사용하여 끝냄 (break를 만날 때까지 계속 실행)

```java
String str = "hello";
switch(str) {
  case "hi" : 
  ...
  break;
  case "bello" : 
  ...
  break;
  case "hello" :
  // 이곳 실행
  break;
  default :
  ...
}
```

### 반복문
조건에 따라서 특정 실행문을 계속 반복하는 것
반복문에는 for / while / do-while 문 등이 

#### break
자신이 포함된 하나의 반복문이나 switch문을 빠져 나옴

#### continue
continue 이후의 문장들은 실행되지 않음
해당 반복 부분만 빠져나옴

#### while문

#### do-while문

#### for문

#### 향상된 for문
