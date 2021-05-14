# Package
# Package란?
비슷한 성격의 자바 클래스들을 모아놓은 자바의 디렉토리로
폴더를 만들어 파일을 저장하듯, 패키지를 만들어 클래스를 저장 / 관리한다.
클래스의 전체 이름은 "패키지명 + 클래스명" 이다.

```java
package 상위패키지명.하위패키지;

public class Test1() {...}
public class Test2() {...}
```

### 패키지 선언
- 패키지는 숫자로 시작해서는 안된다.
- $ , _를 제외한 특수 문자는 사용 할 수 없다.  
- java로 시작하는 패키지는 자바 표준 API에서만 사용하므로 사용해서는 안된다.
- 모두 소문자로 작성하는 것이 관례이다.

### 주요 package
- java.applet : Java Appet Package
- java.awt : Java Abstract Windowing Toolkit Package
- java.awt.datatransfer : Java Data Transfer Package
- java.awt.event : Java AWT Event Package
- java.awt.image : Java AWT Image Package
- java.awt.peer : Java AWT Peer Package
- java.beans : Java Beans Package
- java.io : Java Input/Output Package
- java.lang : Java Language Package(기본 패키지로 import문 없이 사용)
- java.lang.reflect : Java Core Reflection Package
- java.net : Java Networking Package
- java.rmi : Java Remote Method Invocaion Package
- java.security : Java Database Connectivity Package
- java.text : Java Text Package
- java.util : Java Utilities Package

### complie with package
- 일반 컴파일: javac 클래스파일명.java
- 패키지 컴파일: javac -d 클래스 저장위치 클래스 파일명
```
ex: javac -d . HelloWorld.java

javac -d . 클래스명.java                  // 현재 폴더에 생성
javac -d ../bin 클래스명.java             // 현재 폴더와 같은 레벨 bin 폴더에 생성
javac -d ~/Desktop/test 클래스명.java     // 지정 폴더에 생성
```
**패키지 실행**
- 일반 실행: java클래스 파일명
- 패키지 실행: java 패키지명.클래스 파일명
```
(ex)
java test.sy.HelloWorld
```

# import
