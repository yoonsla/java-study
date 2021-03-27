* JVM 
jvm 이란
- java virtual machine의 줄임말
- java byte code를 os에 맞게 해석해주는 역할
- java compiler는 .java 파일을 .class 라는 java byte code로 변환 시켜줌

컴파일러란
- 고차원의 언어를 기계어로 옮기는 과정

바이트 코드란
- 특정 하드웨어가 아닌 가상 컴퓨터에서 돌아가는 실행 프로그램을 위한 이진 표현법
- 소프트웨어에 의해 처리되는 만큼 기계어보다 추상적임

jvm 구조
- class loader
	- runtime 시점에 클래스를 로딩하게 해주며 클래스의 인스턴스를 생성하면 클래스 로더를 통해 메모리에 로드하게 된다
- runtime data areas
	- jvm이 프로그램을 수행하기 위해 os로부터 별도로 할당 받은 메모리 공간
	- PC Resister / JVM Stack / Native Method Stack / Method Area / Heap
	- PC Resister
		- Thread가 시작될 때 생성
		- Thread가 어떤 명령어로 실행되어야 할지에 대한 기록
		- 현재 수행중인 JVM 명령의 주소를 가짐
	- JVM Stack
		- Heap 영역에 생성된 Object 타입의 데이터의 참조값이 할당
		- 원시타입(primitive types)의 데이터가 값과 함께 할당
		- 각 Thread는 자신 만의 stack을 가짐
		- 프로그램 실행 과정에서 임시로 할당되었다가 메소드를 빠져나가면 소멸되는 특성의 데이터를 저장하기 위한 영역
		- 변수, 임시 데이터, Thread, 메소드 등의 정보 저장
		- 메소드 호출 시마다 각각의 스택 프레임 생성
		- 메소드 수행이 마무리 되면 프레임 별로 삭제 및 메소드 내 사용되는 값들 저장
		- 호출된 메소드의 매개변수, 지역변수, 리턴 값 및 연산 시 일어나는 값들 임시 저장

	- Native Method Stack

	- Method Area

	- Heap
		- 객체를 저장하는 가상 메모르 공간
		- new 연산자를 통해 객체와 배열 등을 저장, Method Area 영역에 올라온 클래스들만 객체로 생성가능
		- 긴 생명 주기를 가지는 데이터 저장
		- stack 영역에 있는 데이터를 제외한 부분
		- 모든 Object 타입(Integer, String, ArrayList...) 등은 Heap 영역에 생성 
		- 몇 개의 thread가 존재하든 상관없이 단 하나의 heap 영역만 존재
		- Heap 영역에 있는 Object들을 가리키는 레퍼런스 변수가 stack에 올라간다
		- Heap 영역은 3가지 영역으로 나뉜다
			- New / Young Generation
				- Eden 영역에 최초로 생성, 시간이 지나 우선순위가 낮아지면 Old로 이동
				- 이 때 Minor GC 발생
			- Old Generation
				- New / Young에서 저장되었던 객체 중 오래된 객체가 넘어와 저장
				- 객체가 사라질 떄 Major GC 발생
			- Permanent Generation
				- 생성된 객체 정보의 주소값 저장
				- Class Loader에 의해 로드되는 클래스, 메소드 등에 대한 meta 정보가 저장(JVM에 의해 사용)



- execution Engine
	- load된 class의 bytecode를 실행하는 runtime module
	- 실행 엔진은 자바 바이트 코드를 명령어 단위로 읽어서 실행한다
	- 초기 JVM이 나왔을 당시에는 한줄씩 해석하는 Interpreter 방식이었기 때문에 속도가 느리다는 단점이 있었음
	- JIT Compier방식을 도입해 단점을 해결

JIT Compier란
- Just In Time의 약자
- 프로그램을 실제 실행하는 시점에 기계어로 번역하는 컴파일 기법
- bytecode 전체를 컴파일하여 Native Code로 변경하고 캐시에 보관하여 코드 전체를 변환하는 방식
- JIT Compiler가 커마일하는 과정은 bytecode를 인터프리팅 하는 것보다 오래 걸리기 때문에 한번만 실행되는 코드라면 컴파일하지 않고 인터프리팅 하는 것이 유리

컴파일 방법
- $ javac main.java

실행 방법
- $ java main

* JDK와 JRE 차이

JRE란

JDK란

* GC

GC란



https://medium.com/@lazysoul/jvm-%EC%9D%B4%EB%9E%80-c142b01571f2
https://goateedev.tistory.com/197
https://yaboong.github.io/java/2018/05/26/java-memory-management/
