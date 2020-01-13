# JAVA


### IDE(Integration Development Environment, tool)
 * eclipse - https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2019-12/R/eclipse-inst-win64.exe
 
* intelliIDEA community
    
* Visual Studio Code
    
### IDK
  * openjdk : 무료 - https://github.com/ojdkbuild/ojdkbuild / https://jdk.java.net/java-se-ri/8
  * oraclejdk : 부분 무료, 특정 API를 사용하면 유료
#### eclipse theme 적용
  * 테마 다운로드 - http://www.eclipsecolorthemes.org/?view=theme&id=14105
  * file -> import -> 파일 적용

### 자바 동작원리
* one source multise
  
  * 하나의 소스를 만들면 플랫폼에 상관없이 똑같은 결과를 얻을 수 있다.
  * 플랫폼(Operating System, os)
* 컨셉 - 가전기기 통합 oak 코드명으로 제작이 되었음
* 플랫폼 독립적인 프로그래밍
* Sum Micro Systems -> Oracle
* 만든 사람 : James Gosling(제임스 고슬링)

- HelloWorld.java 파일을 만들고
    - javac HelloWorld.java -> HelloWorld.class 실행파일(Bytecode)
    - 실행 java HelloWorld(.class)

- 함수형 프로그래밍(functional programming) 지원[JDK8/JDK1.8]
    - 람다식
        - 필터링
        - 매핑
        - 집계
    - 변수 값이 변하지 않고 처리됨
    - 한방향으로 진행된다.
    - 대용량 데이터 처리를 하기위해서
    
- multi threading을 사용할 수 있다.
- ctrl + n : 새로운 파일 생성
- ctrl + space : 명령어 자동완성
- ctrl + F11 : 저장 후 실행
- ''와 ""을 구분하여 사용해야한다.

### jvm, jre, jdk
- jdk(java development kit) : 자바 개발할 때 필요한 API
- jre(java runtime environment) : 자바 실행할 때 필요한 프로그램
- jvm(java virtual machine) : 자바 가상 머신
- jre를 설치하면 jvm은 자동으로 설치가 되고, java를 개발하고 싶으면 jdk까지 설치하면 된다.

### 프로그래밍이란?
- data + logic
- 사람이 컴퓨터에 명령을 내려서 동작하게 하는 것
- 언어 : 사람과 컴퓨터가 대화할 수 있도록 해주는 것
- 컴퓨터 언어 : Java, Javascript(ECMAScript), python, c#, c, c++...
- 언어 선택할 때 기준을 정해야함
    - 취업 : Java, Javascript, C#
    - 데이터 분석 : python, R
    - 게임 : C, C++
    
### OOP(Object Oriented Programming)
- 객체지향 프로그래밍
- 객체 : 행위(method)와 속성(attribute)를 갖는 모든 것
- 컴포넌트 단위(객체)로 클래스를 만들어서 필요한 시점에 조합해서 사용할 수 있도록 하는 것
- 각 클래스는 자신의 기능이나 역할을 하도록 구현되며 계층구조를 구성함에 따라서 기능이 실행이 될수도 있고 안될수도 있다.
- 구현된 클래스는 필요한 시점에 호출할 수 있다.
- attribute(속성, member field)
- method(행위, member method)
- member : member field, member method

### 명령법
- 프로그램을 구현하면서 지켜야 할 규칙이나, 오류가 발생하지는 않는다.
- 하지만 프로그래머들의 규약이라서 반드시 지키지 않으면 혼난다!

- 파스칼(pascal) : 처음에 시작할 때 대문자 그 다음 소문자 의미 바뀌면 대문자 소문자
  - ex) class CoffeeMachine 클래스, 인터페이스
- 카멜(camel) : 처음에 시작할 때 소문자 의미 바뀔때 첫글자 대문자 소문자
  - ex) public void makeCoffee(); 메소트, 변수명
- 헝가리안(hungarian) : 타입 축약 + 이름
  - ex) textName, lblNumber 타입을 줄여서 이름과 붙여서 사용, GUI(Swing)
- 전체 대문자 : 상수, 변하지 않는 값을 지정할 때
  - ex) Math.PI = 3.14, System.out.println(Math.PI); 3.14가 나온다.
- 전체 소문자 : 예약어, 키워드, 피키지
  - ex) public, new, void, class, com.sk.sales, ...
  
### 주석
- // : 한줄 주석
- /* */ : 여러줄 주석
- /** */ : API Document 만들 때 사용되는 주석

### 패키지
- 비슷한 클래스들의 묶음(모음)
```
www.sk.co.kr (X)
```
```
kr.co.sk.sales (O) 
```
  - 영업파트 관련 코드들이 들어감
``` 
kr.co.sk.common (O) 
```
  - 공통으로 사용하는 코드들이 들어감
``` 
com.medici.java01 
```
- 파일 맨 상단에 작성을 한다.
- 패키지는 .밑으로 하나씩 폴더로 구성되어 있다.

### 타입(type)
- 기본타입(primitive type)
```
byte    정수 (1BYTE)
short   정수 (2BYTE)
int     정수 (4BYTE)
long    정수 (8BYTE)
float   실수 (4BYTE)
double  실수 (8BYTE)
boolean 논리값 (1BYTE)
char    캐릭터 (2BYTE)
enum    열거형 - 값을 저장하는 타입
```
```
int a = 10;
System.out.println(a); // 10
```
- 참조타입(reference type)
  - 배열타입
    - User define(개발자 정의한 타입)
    - API Dovument에 정의된 클래스
       - reference를 저장하는 타입
    - A a = new A();
    - System.out.println(a); - 주소출력

### 변수(명)
- 데이터나 주소값을 저장하는 저장소
- 기본타입은 값을저장하고, 참조타입은 주소를 저장한다.
- 사용할 용도에 맞는 명칭을 정하면 그게 변수명이 된다.
```
int cup; -> attribute
int cup2;
```

### main method
- 순수 자바 애플리케이션을 실행할 때 제일 먼저 호출되는 메소드
- public static void main(String[ ] args){
  }
- 대소문자 구분을 하고, 반드시 위와 똑같이 쓰지 않으면 오류가 발생한다.
- 만들어진 클래스를 실행하고 싶으면 위의 메소드에 객체를 생성해서 실행해야 한다.

### new 키워드
- 객체를 생성할 때 사용하는 키워드
- 객체를 생성하는 이유? 객체를 사용하기 위해서
- 객체를 생성하는 방법
```
      CoffeeMachine   cm    = new CoffeeMachine();
                     주소값
                   (참조변수)
```
- 참조변수는 그 자체가 값이 아니기 때문에 어떤식으로든 가공을 해야한다.
- 예를들면, cm.coffeeMake(); 처럼 만들어진 메소드를 호출해야 내가 작성한 메세지가 출력이 된다.

### method
- 데이터를 가지고 어떤 로직을 만들어서 데이터를 출력하거나 넣을때 사용
```
return O
  int count(){
    int cup = 1000/100;
      return cup;
    }

    int count(){
      return 1;
    }
```
```
return X
  void isSarangOK(){
    System.out.println("...");
    }
```

### Path 설정
```
JAVA_HOME
C:\Program Files\ojdkbuild\java-1.8.0-openjdk-1.8.0.232-2\bin

%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
C:\Program Files\ojdkbuild\java-1.8.0-openjdk-1.8.0.232-2\jre\bin
```

### pbv vs pbr
기본타입은 value를 주고 value를 받는다.
참조타입은 reference를 주고 reference를 받는다.

- pass by value
  - assign by value
  - immitable
```
int a = 10;
int b = a; // a->b
c = a+20;
System.out.println(a); // 10 값이 변하지 않는다.
                       // a값이 변하려면 재할당을 해야한다.
```
- pass by reference
  - assign by reference
  - mutable
```
int[] c = {1,2,3,4,5};
int[] d = new int[5];
d = c;
c[2] = 100;
System.out.println(d[2]);  // 100
```
(F3 - 연관된 명령어로 이동)

### parameter/argument
- 메소드의 괄호안에 타입+변수 명의 형태로 받을 값을 지정해주는 것을 이야기한다.
```
P p = new P();
p.setName(String name); // P클래스에 name 이라는 변수로 값을 넣어준다.
```

### 접근제한자(access modifier)
```
private		~ : 같은 클래스 내에서만 접근 가능
(default)	  : 같은 패키지 내에서만 접근 가능
protected	# : 상속 O public, 상소 X default
public		+ : 모든 곳에서 접근이 가능
```
```
package.com.medici.testa;
public class A(
	private in money = 10;
	public void sendMoney(){
		System.out.println("돈을 보냈습니다.");
	}
)
```
```
package.com.medici.testb;
public class B(
	int money2 = 20;
	void getMoney(){
		System.out.println("돈을 받습니다.")
	}
)
```
### OOP의 3대 특징
- 은닉성(encapsulation) : member field private, member method private
- 상속성(inheritance) : 부모에 있는 member를 물려 받는 것
- 다형성(polymorphism) : 다양한 형태를 나타내는 성질, 부모에 있는 메소드가 자식의 형태에 따라 다양하게 호출되는 것

member field에 값을 선언하지 않으면 참조차입은 null로 초기화가 되고, 기본타입은 기본타입의 기본값으로 초기화가 된다.
```
	class A(
		int sum; // member field, 전역 변수
		// sum = 0;
	)
```

### 은닉성(encapsulation)

- member field private, member method private
```
	class People{
		private in age;
		public void setAge(int age){
			this.age = age;
		}
		public int getAge(){
			return age;
		}
	}
```
```
	class Main{
		public static void main(String[] args){
			People p = new People();
			p.age = 10; // X
			p.getAge(); // O
		}
	}
```

### 상속성(inheritance)
- 부모에 있는 member(method, field)를 물려 받는 것
- 상속 키워드 extends
	자식 클래스 extends 부모 클래스
```
	  class Student extends People(
	  	...
	  )
```
- 상속이 되는 의미는 is 관계이다.
```
    Student is People이 true 인 관계이다. 
    (자식)	 	 (부모)
```

### class(클래스)
- 속성(attribute)과 행위(method)가 들어 있는 설계도
- 설계도, 붕어빵 틀
- 블루프린트(청사진)
- java

### Object(.class)
- instance, 오브젝트, 객체
- 붕어빵
- .class

## 메모리 4대 특징
- 자식이 생성되면 부모가 생성된다.
- 자식이 설계도에 올라가면 부모도 설계도에 올라간다.
- 생성된 주소는 부모의 주소를 가리킨다.
- 설계도에 공개된 메소드만 사용이 가능하다.

### if문
```
	- if(조건식){
		// 조건식이 참일 경우 실행되는 문장
	  }
	  else{
	  	// 조건식이 거짓일 경우 실행되는 문장
	  }
```
```
	- if(조건식1){
	 	조건식1이 만족할 경우 실행되는 문장
	  }
	  else if(조건식2){
	  	조건식2가 만족할 경우 실행되는 문장
	  }
	  else{
	  	조건식1도 만족 X, 조건식2도 만족 못할 경우 실행되는 문장
	  }
```
```
	- if(조건식){
		조건식이 만족할 경우 실행하는 문장
	  }
	  조건식이 만족하지 않을 경우에는 여기가 실행
```

local variable(지역변수)은 초기값을 설정해 주어야 한다.
```
	public void localVar(){
		int a;
		int b =10;
		int c = b+a; // a는 오류가 발생 한다.
					 // a에 초기값을 지정해 줘야한다.
	}
```

### String class(문자열 클래스)
- 문자열을 받을 때 사용하는 참조타입 클래스
- 참조타입이지만 기본타입의 성질을 갖고 있는 클래스
- 특징
  - immutable
    - 값을 재할당 하기 전까지는 값이 변하지 않는다.
  - concatenation
    - String 타입을 만나는 순간 String 타입이 된다.
- String s = new String("음동하"); // 참조타입
- String s1 =  "음동하"; // 기본타입
```
System.out.println(s==s1); // false
System.out.println(s.equals(s1)); // true
System.out.println(s.equalsIgnoreCase(s1)); // true
```
- immutable, 다시 할당할 때 까지
```
String str = "배새연";		// int a = 10
str.replace("배","임");	// int c = a+20
System.out.println(str);	// System.out.println(a);
// 배새연
```
- concatenation, String 타입을 만나는 순간 String 타입이 된다.
```
System.out.println(1+2+3+"유창용"); 	// 6유창용
System.out.println("유창용"+1+2);		// 유창용12
System.out.println("유창용"+1+(2+3));	// 유창용15
System.out.println(1+"유창용"+2+3);	// 1유창용23
System.out.println((1+2)+3+"유창용");	// 6유창용
```
