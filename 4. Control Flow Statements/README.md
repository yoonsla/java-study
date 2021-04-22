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
if (num < 0) {
  // if 조건식에 대해 true일 경우 실행되는 영역
} else if (num > 0) {
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
switch (str) {
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
반복문에는 for / while / do-while 문 등이 있음
- 반복 수가 정해진 경우에는 for문을 사용하는 것이 좋으나 수행문을 한 번 이상 사용해야 하는 경우에는 do-while이 적합

#### break
자신이 포함된 하나의 반복문이나 switch문을 빠져 나옴

#### continue
continue 이후의 문장들은 실행되지 않음
해당 반복 부분만 빠져나옴

#### while문
- 특정한 명령들을 반복적으로 처리할 목적으로 사용
- 조건 비교에 만족할 때에만 반복 처리를 할 수 있음
- 조건식에 참여하는 변수의 값이 변화를 가져오지 않으면 무한 루프에 빠질 수 있음
- '선 비교, 후 처리'로 진행되기 때문에 첫 조건 비교에서 false를 받게 되면 한번도 수행하지 않을 수 있음

```java
int i = 1;
while (i <= 10) {
  System.out.println(i + "번 째 진행 중");
}
System.out.println("반복 끝나면 종료");
```

#### do-while문
- '선 처리, 후 비교' 방식
- 조건이 불만족한 경우가 될지라도 처리를 먼저 하고 조건 비교가 이루어지므로 최소 한번은 수행됨

```java
int i = 1;
do {
  System.out.println(i + "번 째 진행 중");
  i++;
  while(i<=10);
  System.out.println("반복 종료");
}
```

#### for문
- 반복횟수를 관리할 수 있음
- for문에서는 조건식이 없을 경우 무한루프에 빠짐

```java
for (초기식; 조건식; 증감식) {
  // 반복 명령 1;
  // 반복 명령 2; 
  //...
}

// 초기식: 가장 먼저 수행하는 부분 (두 번 다시 수행하지 않음)
// 조건식: 초기식 다음으로 수행하는 부분
// 증감식: 루프를 수행할 때마다 조건식에서 비교하기 전에 항상 수행하며 조건식에서 사용되는 변수값을 증가시키거나 감소시킴

for(int i=1; i<10; i++) {
  System.out.println(i + "번째");
}

```

#### 향상된 for문(foreach)
- for문이 배열과 List에 많이 사용되어 개량된 것

```java
for(type var: iterate) {
  // loop..
}

int [] arr = {1,2,3,4,5};
for(int arrVal : arr) {
  System.out.println("너의 값은: " + arrVal);
}
```

#### 다중 for문 / 중첩 for문
반복문 안에 또 반복문이 들어가는 것

```java
for (A) {
// loop...
  for (B) {
    // loop...
  }
}
```
