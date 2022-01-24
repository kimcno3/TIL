# :pushpin: 자바의 신 정리
> 상세 내용은 책을 구매하셔서 확인하시기 바랍니다.

<br>

## :pushpin: 목차
**:pushpin: Volume 1**
- [:pushpin: Chapter1](#pushpin-Chapter1)
- [:pushpin: Chapter2](#pushpin-Chapter2)
- [:pushpin: Chapter3](#pushpin-Chapter3)
- [:pushpin: Chapter4](#pushpin-Chapter4)
- [:pushpin: Chapter5](#pushpin-Chapter5)
- [:pushpin: Chapter6](#pushpin-Chapter6)
- [:pushpin: Chapter7](#pushpin-Chapter7)
- [:pushpin: Chapter8](#pushpin-Chapter8)
- [:pushpin: Chapter9](#pushpin-Chapter9)
- [:pushpin: Chapter10](#pushpin-Chapter10)

<br>

## :pushpin: Chapter1
> 프로그래밍이란 무엇인가?

### ✔ 직접해 봅시다.
#### **문제 설명**
빼기, 곱하기, 나누기 메소드 생성해보기.

#### **작성 코드**
```java
public class Calculator {
    // add(), addAll() 생략

    public int subtract(int num1, int num2) {
        int sub;
        sub = num1 - num2;
        return sub;
    }

    public int multiply(int num1, int num2) {
        int mul;
        mul = num1 * num2;
        return mul;
    }

    public int divide(int num1, int num2) {
        int div;
        div = num1 / num2;
        return div;
    }
}
```

### ✔ 정리해 봅시다.
#### **1. 클래스가 뭔가요?**
자바에서 가장 작은 단위로 상태와 행동을 가집니다. 여기서 상태는 변수, 행동은 메소드를 통해 구현할 수 있습니다. 현실의 사물이나 추상적인 개념을 클래스로 표현할 수 있습니다. 이러한 방식의 프로그래밍을 객체 지향 프로그래밍이라고 합니다.

**클래스 선언 방법** <br>
```java
public class ClassName {
    // 메소드 or 변수 선언;
}
```
- public : 접근 제어자(Access Modifier)
- class : 클래스 선언시 반드시 붙혀야 한다.
- ClassName : 클래스명

#### **2. 메소드가 뭔가요?**
- 클래스에서 "행동"의 역할을 의미하며 일련의 과정을 통해 새로운 값을 생산, 계산 및 반환합니다.

**메소드 선언 방법** <br>
```java
public class ClassName {
    public void methodName(parameterName) {
        // 생략;

        return OOO; // 리턴값 설정
    }
}
```
- public : 접근 제어자(Access Modifier)
- void : 리턴타입, 리턴할 값의 자료형을 표현합니다. (`void`는 리턴값이 없을 경우)
- methodName : 메소드 이름
- parameterName : 매개변수 이름, 매개변수는 몇개가 들어가도 상관없습니다.

#### **3. 메소드의 매개변수는 어디에 적어두나요?**
매개변수는 메소드명 뒤에 오는 소괄호 안에 적습니다.

#### **4. 메소드 이름 앞에 꼭 적어 줘야 하는 건 뭐죠?**
접근 제어자와 리턴타입입니다.

#### **5. 클래스가 갖고 있어야 한다고 한 두 가지는 뭐죠?**
상태와 행동, 구체적으로 변수와 메소드입니다.

#### **6. 메소드에서 결과를 돌려주면 어떤 예약어를 사용해야 하나요?**
`return`을 사용합니다.

<br>

***

<br>

## :pushpin: Chapter2
> Hello God Of Java

### ✔ 직접해 봅시다.
#### **문제 설명**
1. Profile 클래스를 만들고 그 안에 main() 메소드를 만들어보자.

2. "My name is OOO"라는 값을 출력하는 코드 작성

3. "My age is OO"라는 값을 출력하는 코드 작성

4. 다음과 같은 결과값이 출력되도록 코드 작성
    ```java
    My name is OOO
    My age is OO
    ```
#### **작성 코드**
```java
public class Profile{
  public static void main(String[] args){
      System.out.println("My name is Kim");
      System.out.print("My age is 27");
  }
}
```

<br>

### ✔ 정리해 봅시다.
#### **1. main() 메소드의 메소드 이름 앞에는 어떤 예약어들이 들어 가나요? (순서대로 쓰세요)**
- `public static void` main(String[] args){}
- public : 어떤 클래스에서도 접근 가능
- static : 객체를 생성하지 않아도 접근 가능한 메소드
- void : 리턴값이 없음

#### **2. main() 메소드의 매개변수에는 어떤 값이 들어가나요?**
- public static void main(`String[] args`){}
- String 문자열의 배열이 들어갑니다.

#### **3. 만약 여러분들이 만든 클래스에 main() 메소드가 없다면, java 명령어로 그 클래스를 수행할 수 있나요?**
public static void main(String[] args)로 선언되어 있는 메소드가 클래스에 없으면, 해당 클래스를 실행할 수는 없다.

#### **4. System.out.println() 메소드는 어떤 용도로 사용하나요?**
System.out.println() 메소드는 자바를 실행한 창에서 문자열을 출력하는데 사용됩니다.

#### **5. System.out.print() 메소드는 System.out.println() 메소드와 어떤 차이가 있나요?**
- System.out.print() -> 줄바꿈 X
- System.out.println() -> 줄바꿈 O

#### **6. `//` 는 무엇을 하는데 사용하는 기호인가요?**
`//`는 한 줄 주석을 의미한다. 따라서, 해당 코드의 `//` 뒤에 있는 모든 내용은 무시된다.

#### **7. `/*` 로 시작하고, `*/`로 끝나는 사이에 있는 소스들을 어떻게 되나요?**
`/*`으로 시작하여 `*/`으로 끝나는 주석은 블록 주석으로, 해당 블록 내의 모든 내용은 컴파일시 무시된다.

#### **8. 메소드를 선언할 때 반드시 꼭 있어야 하는 세가지는 무엇인가요?**
메소드에는 반드시 "리턴 타입", "메소드 이름", "메소드 내용"이 있어야만 한다.

<br>

### ✔ 추가 내용
#### **1. 사용자변수와 시스템변수의 차이**
- 사용자 변수
    - 로그인된 계정 내에서 사용하는 변수
    - 사용자 계정별로 설정되어 있는 PATH가 다릅니다.

- 시스템 변수
    - 컴퓨터 내에서 사용하는 변수
    - 한번 PATH를 설정해 두면 어떤 계정이든 사용 가능합니다.
> [참고 사이트](https://wikim.tistory.com/232)

#### **2. JVM, JRE, JDK 란?**
- JVC(Java Virtual Machine)
    - 컴파일 이후, 바이트코드로 구성된 자바 파일(`.class` 확장자)을 기계어로 해석하여 운영체제에서 실행시키는 역할을 합니다.

- JRE(Java Runtime Environment)
    - **JVM**을 포함하여 자바 프로그램을 실행시키기 위해 필요한 라이브러리 및 기타 파일이 포함된 **패키지**
    - **자바 실행 환경**이라고 이해할 수 있습니다.
    - **java.exe** 파일이 포함되어 있습니다.(JVM을 구동시키기 위한 명령 프로그램)


- JDK(Java Development Kit)
    - 자바 프로그래밍을 위해 필요한 도구
    - 대표적으로 컴파일러(javac.exe)가 JDK에 포함됩니다.
> [참고 사이트1](https://goodgid.github.io/Java-JDK-JRE/)

> [참고 사이트2](https://velog.io/@ggob_2/java-study-1#7-jvm%EC%9D%98-%EA%B5%AC%EC%84%B1-%EC%9A%94%EC%86%8C)

#### **3. java파일 실행시 파일명만 필요한 이유**
JVM을 구동하기 위해 `java filename` 명령어를 실행하는데, 이는 "JVM이 filename에 해당하는 파일을 실행한다"가 아니라 "filename을 가진 바이트코드에 main메소드가 존재한다" 라는 사실을 전달하는 의미입니다.

그래서 확장자명을 포함하여 java.exe 파일을 실행시키면 확장자명까지 파일명으로 인식하여 main 메소드가 없다 또는 해당 파일명을 찾을 수 없습니다 라는 에러가 발생합니다.
> [참고 사이트](https://8iggy.tistory.com/m/233)

<br>

***

<br>

## :pushpin: Chapter3
> 자바를 제대로 알려면 객체가 무엇인지 알아야 해요

### ✔ 직접해봅시다
#### **1. `Profile` 클래스에 변수 추가(`name`, `age`)**
```java
public class Profile{
  String name; // 이름
  int age; // 나이
  public static void main(String[] args){
  }
}
```

#### **2. `setName()` 메소드 생성**
`setName()` 메소드는 `str`을 매개변수로 받아 `name`으로 지정해 주는 기능

```java
public void setName(String str){
    name = str;
}
```

#### **3. `setAge()` 메소드 생성**
2와 같은 방법으로 `val`을 매개변수로 받아 `age`에 할당
```java
public void setAnge(int val){
    age = val;
}
```

#### **4. `printName()` 메소드 생성**
`name`을 출력해주는 기능

```java
public void printName(){ // 매개변수 불필요
    System.out.println("이름 : " + name);
}
```

#### **5. `printAge()` 메소드 생성**
`age`을 출력해주는 기능

```java
public void printAge(){ // 매개변수 불필요
    System.out.println("나이 : "+ age);
}
```

> 4, 5번 메소드 생성시 매개변수로 name이나 age를 가져오지 않아도 사용할 수 있습니다. (name은 **멤버변수**이기 때문!!)

> 상세설명은 아래 추가 내용에서 자세히 다루겠습니다. [바로 가기](#1-멤버변수)

#### **6.` main()` 메소드에서 profile 이름으로 객체 생성**
```java
public static void main(String args[]){
    Profile profile = new Profile();
}
```

#### **7. `setName()`, `setAge()` 메소드를 사용하여 이름과 나이값을 할당**
```java
public static void main(String args[]){
    Profile profile = new Profile();

    profile.setName("Kim"); // 이름 할당
    profile.setAge(27); // 나이 할당
}
```

#### **8. `printName()` , `printAge()` 메소드를 사용하여 이름과 나이 출력**
```java
public static void main(String args[]){
    Profile profile = new Profile();

    profile.setName("Kim"); // 이름 할당
    profile.setAge(27); // 나이 할당

    profile.printName(); // 이름 출력
    profile.printAge(); // 나이 출력
}
```

#### **전체 코드**
```java
public class Profile{
    // main 함수
    public static void main(String[] args){
        Profile profile = new Profile();
        profile.setName("Kim");
        profile.setAge(27);
        profile.printName();
        profile.printAge();
    }

    // 필드
    String name;
    int age;

    //메소드
    public void setName(String str){
        name = str;
    }
    public void setAge(int val){
        age = val;
    }
    public void printName(){
        System.out.println("이름 : " + name);
    }
    public void printAge(){
        System.out.println("나이 : "+ age);
    }
}
```

#### **최종 결과**
```java
이름 : KIM
나이 : 27
```

<br>

### ✔ 정리해봅시다
#### **1. 클래스와 객체의 차이점을 말해 주세요.**
- 클래스를 통해서 객체를 생성할 수 있다. 즉, 하나의 클래스를 만들면 그 클래스의 모습을 갖는 여러 객체들을 생성 할 수 있다.

- 클래스 범주 안에 객체가 포함되어 있고, 클래스의 복제품 격에 객체라고 할 수 있다.

#### **2. 객체를 생성하기 위해서 꼭 사용해야 하는 예약어는 뭐라고 했죠?**
**new 키워드**를 사용하여 클래스의 객체를 생성한다.

#### **3. 객체를 생성하기 위해서 사용하는 메소드 같이 생긴 클래스 이름에 소괄호가 있는 것을 뭐라고 하나요?**
**생성자(Constructor)** 를 통하여 클래스의 객체를 생성한다.

#### **4. 객체의 메소드를 사용하려면 어떤 기호를 객체이름과 메소드 이름 사이에 넣어주어야 하나요?**
- **마침표(.)** 를 사용합니다.
- 클래스의 변수나 메소드를 호출하려면 "객체이름.변수", "객체이름.메소드이름()"와 같이 사용하면 된다.

#### **5. 여러분들이 메소드를 사용하기 위해서는 어떤 것을 만들어야 하나요?**
클래스의 **객체**를 생성해야만 메소드를 사용할 수 있다.

#### **6. 위의 문제에서 만들어야 하는 것은 어떤 예약어를 사용하고, 클래스의 무엇을 사용해야 하나요?**
**new 키워드**를 사용하여 **생성자**를 호출해야만 된다.

<br>

### ✔ 추가내용
#### **1. 멤버변수**
**멤버변수(Instance Variable)** 는 객체를 생성해야만 사용할 수 있는 변수를 의미하며 **객체 생성시, 해당 객체의 메소드에서 사용가능**합니다.

위에 **직접해봅시다**에서 4,5번 메소드 또한 멤버변수를 사용하는 메소드였기에 따로 매개변수로 지정하지 않아도 사용이 가능했던 것입니다.
> [참고 사이트](https://digiconfactory.tistory.com/entry/%EC%9E%90%EB%B0%94-%ED%8A%9C%ED%86%A0%EB%A6%AC%EC%96%BC-5-9-%EB%B3%80%EC%88%98-%EC%9C%A0%ED%9A%A8%EB%B2%94%EC%9C%84-Scope)

#### **2. main 함수 실행 순서**
자바의 신 Github 저장소에서 찾은 **직접해봅시다** 의 [모범 코드](https://github.com/godofjava/GodOfJava2nd/blob/master/Chapter03/src/Profile.java)와 내가 작성한 코드를 비교해봤을 때, main() 메소드의 위치가 다른 것을 볼 수 있었다.

모범 코드에서는 `main()` 메소드가 가장 먼저 작성되어 있고, 그 이후로 클래스의 필드와 메소드가 선언되어 있었다.

이 부분에서 단순한 생각으로 클래스의 필드와 메소드가 먼저 선언된 다음, main() 메소드가 실행되어야 하는 것이 맞지 않은가 하는 의문이 생겼다.

자바스크립트에서 호이스팅 개념이 있듯이 자바에서도 비슷한 개념이 있나 궁금증이 생겨 찾아본 결과, 간단한 해답을 찾았다.

바로 자바로 구성된 프로그램, 파일을 실행시에는 **main() 메소드가 가장 먼저 실행된다**는 것이다.

즉, `main()` 메소드가 가장 먼저 실행되면서 객체를 생성하고 그 이후로 생성된 객체의 메소드를 호출하는 순서로 코드가 진행되는 것이다.

그렇기 때문에 main 메소드가 클래스 내에서 가장 먼저 작성되어도 문제될 점은 없다.
> [참고사이트](https://codingffler.tistory.com/16)

<br>

***

<br>

## :pushpin: Chapter4
> 정보를 어디에 넣고 싶은데
### ✔️ 직접해 봅시다
#### **1. ProfilePrint 클래스 생성 및 age,name 이름의 인스턴스 변수 선언**
```java
public class ProfilePrint{
    byte age;
    String name; // 또는 String name = new String();
}
```

#### **2. boolean 타입의 "isMarried" 인스턴트 변수 선언**
```java
public class ProfilePrint{
    // 이전 실습코드 생략
    boolean isMarried;
}
```
#### **3, 5, 7. 각 인스턴스 변수의 값을 매개변수로 지정하는 메소드 생성 -> `setOOOO(parameter)`**
```java
public class ProfilePrint{
    // 이전 실습코드 생략
    public void setAge(byte age2){
        age = age2;
    }
    public void setName(String name2){
        name = name2;
    }
    public void setMarried(boolean flag){
        isMarried = flag;
    }
}
```

#### **4, 6, 8. 인스턴트 변수의 값을 리턴하는 메소드 생성 -> `getOOO()`**
```java
public class ProfilePrint{
    // 이전 실습코드 생략
    public byte getAge(){
        return age;
    }
    public String getName(){
        return name;
    }
    public boolean getMarried(){
        return isMarried;
    }
}
```
#### 9. **main()메소드 생성**
```java
public class ProfilePrint{
    public static void main(String args[]){

    }
    // 이전 실습코드 생략
}
```

#### 10. **set메소드를 호출하여 매개변수를 통해 나이, 이름, 결혼여부 설정**
```java
public class ProfilePrint{
    public static void main(String args[]){
        ProfilePrint profile = new ProfilePrint();

        profile.setAge((byte)27);
        profile.setName((String)"김선호");
        profile.setMarried((boolean)false);
    }
    // 이전 실습코드 생략
```

#### 11. **get메소드를 호출하여 결과 출력**
```java
public class ProfilePrint{
    public static void main(String args[]){
        ProfilePrint profile = new ProfilePrint();

        profile.setAge((byte)27);
        profile.setName((String)"김선호");
        profile.setMarried((boolean)false);

        System.out.println("나이: " + profile.getAge());
        System.out.println("이름: " + profile.getName());
        System.out.println("결혼여부: " + profile.getMarried());
    }
    // 이전 실습코드 생략
```

#### **최종 코드**
```java
public class ProfilePrint{
    public static void main(String args[]){
        ProfilePrint profile = new ProfilePrint();

        profile.setAge((byte)27);
        profile.setName((String)"김선호");
        profile.setMarried((boolean)false);

        System.out.println("나이: " + profile.getAge());
        System.out.println("이름: " + profile.getName());
        System.out.println("결혼여부: " + profile.getMarried());
    }
    byte age;
    String name;
    boolean isMarried;

    public void setAge(byte age2){
        age = age2;
    }
    public void setName(String name2){
        name = name2;
    }
    public void setMarried(boolean flag){
        isMarried = flag;
    }
    public byte getAge(){
        return age;
    }
    public String getName(){
        return name;
    }
    public boolean getMarried(){
        return isMarried;
    }
}
```
매개변수 이름을 좀 더 의미있게 설정했으면 좋았을 것 같다...

#### **출력 결과**
```java
나이: 27
이름: 김선호
결혼여부: false
```
<br>

### ✔️ 정리해 봅시다.
#### 1. 네가지 종류 변수는 어떻게 구분할 수 있나요?
- 변수의 유효범위(생명주기)에 따라서 구분할 수 있습니다.
- 지역변수, 매개변수, 인스턴스변수, 클래스변수

#### 2. 일반 변수의 이름을 지을 때 대문자로 시작하는 것은 일반적인 명명규칙이다.
아니오

#### 3. 자료형에는 기본 자료형과 어떤 자료형이 있나요? *
참조 자료형

#### 4. 기본 자료형에는 몇가지가 있나요? *
8가지

#### 5. 기본 자료형 중 정수형에는 어떤 것들이 있나요? *
byte, short, int, long, char

#### 6. byte는 몇 비트(bit)로 되어 있나요? *
8비트

#### 7. byte 타입은 왜 만들었을까요? *
저장공간의 활용을 극대화 하기 위해서
작은 단위의 데이터를 저장할 때, 불필요한 데이터 공간 차지를 방지하기 위해 byte로 저장합니다.

#### 8. int와 long중 어떤 타입이 더 큰 숫자를 처리할 수 있나요? *
long

#### 9. 소수점을 처리하는 타입은 어떤 것이 있나요? *
float, double

#### 10. char는 정수형인가요? *
예

#### 11. a라는 값을 char로 정의할 때 어떤 기호로 감싸주어야 하나요? *
`''`(홀따옴표)

#### 12. true와 false 두개의 값만을 가지는 타입은 어떤 것인가요? *
boolean

<br>

### ✔️ 추가 내용
#### 1. 가비지 콜렉터(Garbage Collector)
- **가비지(Garbage)** 란 객체나 배열을 가르키는 레퍼런스가 없는 경우를 의미합니다.
- 메모리 확보 위해 가비지를 삭제하는 작업 자체는 **가비지 콜렉션**
- 가비지 콜렉션을 하는 것이 **가비지 콜렉터**라고 합니다.
> [참고 사이트](https://madplay.github.io/post/java-garbage-collection)

#### 2. shortMax+1 === 32768???
**4장 89페이지**에서 **shortMax**에서 1을 더하면 최소값이 나와야 하는데 최대값을 넘어선 값이 나와 당황했다. 그 이유를 찾아보니 short 타입의 값에 단순히 1을 더하면 **int 타입으로 타입이 자동 변환된다**고 한다.

구체적으로 설명하면

1. 정수 연산시에 int가 기본 타입이다.
2. 게다가 다른 타입을 연산할 때 큰 타입으로 자동 변환된다고 한다.
3. 또한 피연산자는 4byte 단위로 계산되어 4byte보다 작은 byte, short, char은 int로 자동 변환된다.

그렇기 때문에 계산 오류를 막기 위해서는 (byte), (short) 코드를 연산식 앞에 추가해줘야 자동 타입 변환을 방지하여 예제에서 원하는 값을 구할 수 있습니다.

해당 내용은 **4장 87페이지** 에서도 언급되는 부분입니다.
> [참고 사이트1](https://kephilab.tistory.com/27)

> [참고 사이트2](https://stackoverflow.com/questions/42682558/largest-java-short-32767-plus-1-not-turning-negative)

<br>

***

<br>

## :pushpin: Chapter5
> 계산을 하고 싶어요

### ✔️ 직접해 봅시다
#### 작성코드
```java
public class SalaryManager{
    public static void main(String Args[]){
        SalaryManager person = new SalaryManager();
        // 세후월급 계산 및 결과 출력
        System.out.println("세 후 월 급 : " + person.getMonthlySalary(20000000) + "원");
    }

    // 세후월급 계산 메소드
    public double getMonthlySalary(int yearlySalary){
        // 세전월급 계산
        double monthSalary = yearlySalary / 12.0;
        System.out.println("세 전 월 급 : " + monthSalary + "원");

        // 근로 소득세 계산
        double MonthTax = calculateTax(monthSalary);
        System.out.println("근로 소득세 : " + MonthTax + "원");

        // 국민 연금 계산
        double MonthNationalPersion = calculateNationalPersion(monthSalary);
        System.out.println("국민   연금 : " + MonthNationalPersion + "원");

        // 건강 보험료 계산
        double MonthHealthInsurance = calculateHealthInsurance(monthSalary);
        System.out.println("견강 보험료 : " + MonthHealthInsurance + "원");

        // 세전월급에서 세금 총액 차감
        monthSalary -= (MonthTax + MonthNationalPersion + MonthHealthInsurance);

        // 계산완료된 세후월급 return
        return monthSalary;
    }

    // 근로 소득세 계산 메소드
    public double calculateTax(double monthSalary){
        double tax = monthSalary * 0.125;
        return tax;
    }

    // 국민 연금 계산 메소드
    public double calculateNationalPersion(double monthSalary){
        double nationalPersion = monthSalary * 0.081;
        return nationalPersion;
    }

    // 건강 보험료 계산 메소드
    public double calculateHealthInsurance(double monthSalary){
        double healthInsurance = monthSalary * 0.135;
        return healthInsurance;
    }
}
```

#### 출력 결과
```
근로 소득세 : 208333.33333333334원
국민   연금 : 135000.0원
견강 보험료 : 225000.00000000003원
월       급 : 1098333.3333333335원
```

<br>

### ✔️ 정리해 봅시다.
#### 1. 값을 할당할 때 사용하는 연산자의 기호는 무엇인가요? *
- `=`
- 우항의 값을 좌항의 변수에 할당한다는 의미

#### 2. 기본적인 덧셈, 뺄셈, 곱셈, 나눗셈, 나머지를 계산할 때 사용하는 연산자의 기호는 순서대로 각각 무엇인가요? *
`+`, `-`, `*`, `/`, `%`

#### 3. += 는 무엇을 할 때 사용하는 연산자 인가요? *
좌항의 변수에 우항의 값을 더할 때

#### 4. 연산의 순서를 모르거나 확실히 하고 싶을 때에는 어떤 기호를 사용해야 하나요? *
소괄호

#### 5. ==와 !=의 차이는 무엇인가요? *
- `==` : 좌항과 우항이 같다면 true
- `!=` : 좌항과 우항이 같다면 false

#### 6. <와 <=의 차이는 무엇인가요? *
- `<` : 두 값이 같은 경우에는 false
- `<=` : 두 값이 같은 경우에도 true
#### 7. ! 연산자는 어떤 타입에 사용 할 수 있나요?
boolean

#### 8. `? :` 로 표시하는 삼항 연산자의 `?`와 `:` 뒤에 명시해 주는 값은 무엇을 의미 하나요?
(조건식) `?` true일때값 `:` false일때값

#### 9. 자바는 형변환을 한다고 했는데, short의 값을 long에 할당할 때에는 어떤 것을 해 주어야 하나요?
(long) 추가

#### 10. 반대로 long값을 short에 할당할 때에는 어떤 것을 해 주어야 하나요?
(short) 추가

#### 11. 위의 두 문제에서 어떤 경우가 기존 값이 사라지고, 엉뚱한 값으로 바뀔 수 있나요?
10번 문제의 경우 오버플로우나 언더플로우가 발생할 가능성이 있다.

<br>

### ✔️ 추가 내용
#### 1. 오버플로우(Intager Overflow)
- 데이터 유형별 범위를 초과한 값을 할당한 경우 발생
- `최대값+1`을 하면 `최소값`이 되는 경우를 의미합니다.
- `최소값-1`을 하면 `최대값`이 되는 경우는 언더플로우라고 합니다.

121 ~ 122페이지에 나오는 예제에서 short의 값으로 할당한 `256`과 `255`를 byte로 캐스팅 하는 경우, 0과 -1값이 나오는데 이런 경우를 오버플로우라고 하고, 두 경우를 자세히 살펴보면 다음과 같습니다.

- (short)256 -> (byte)256
```
0000 0001 0000 0000 -> short일때 256이지만

          0000 0000 -> byte로 형변환을 하면 0이 된다.
```

- (short)255 -> (byte)255
```
0000 0000 1111 1111 -> short일때 255의 모습

          1111 1111 -> byte로 형변환을 했을 때
```
근데 위처럼 `1111 1111`이 `-1`이 되는 이유를 이해하지 못했다.

개인적으로 생각해낸 해답은 최소값인 `-128`을 이진수로 표현하면 `1000 0000`이니까 이 점을 이용해서 `1111 1111`을 다시 표현해보면
```
1111 1111 -> 256
= 1000 0000 + 0111 1111
= -128 + 127
= -1
```
그래서 `(byte)255`가 `-1`이 나오는 것이 아닐까 싶었다.

<br>

하지만 위와같은 계산법이 아니라 처음부터 컴퓨터는 **2진법에서 음수**를 **2의 보수**로 표현하기 때문이였다.

**2의 보수**란 **양수를 표현하는 2진수에서 0과 1을 뒤집은 다음, +1을 해주는 방법**을 뜻하는데

이를 예시로 자세히 살펴보면
```
(byte)1은 2진수로
0000 0001 로 표현한다.

그렇다면 (byte)-1을 2의 보수를 활용한 2진수로 표현할 때

1. 0과 1의 위치를 뒤집는다.
1111 1110

2. +1을 해준다.
1111 1111

즉 8비트에서 1111 1111 은 -1이다.
```

**그렇기 때문에 255(2진수로 1111 1111)를 byte로 표현했을 때 -1값이 나오는 것이다.**

좀 더 자세한 설명은 아레 참고 사이트에 잘 설명되어 있다.


> [참고사이트](https://wikidocs.net/81918)

<br>

***

<br>

## :pushpin: Chapter6

### ✔️ 직접해봅시다.

#### 작성코드
```java
public class InterestManager{
    public static void main(String[] args){
        InterestManager sample = new InterestManager();
        // 1 ~ 365일 for구문
        for (int day=1; day<=365; day++){
            // 해당 일자의 이자율 계산
            double sampleRate = sample.getInterestRate(day);
            // 100만원 기준 일자별 예치금액 계산
            double sampleTotalAmount = sample.calculateAmount(day , 1000000);
            // 10일 단위로 이자율, 예치금액 출력
            if(day%10 == 0){
                System.out.println(day + "일 차, 이자율: " + (sampleRate*100) + "% , 예치금+이자: " + sampleTotalAmount + "원");
            }
        }
    }
    // 이자율 계산 메소드
    public double getInterestRate(int day){
        double rate;
        if(day>=1 && day<=90){
            rate = (0.005);
        } else if(day <= 180){
            rate = (0.01);
        } else if(day <= 364){
            rate = (0.02);
        } else {
            rate = (0.056);
        }
        return rate;
    }
    // 총액 계산 메소드
    public double calculateAmount(int day, long amount){
        double rate = getInterestRate(day);
        double totalAmount = amount + (amount*rate);
        return totalAmount;
    }
}
```
#### 실행 결과
```java
10일 차, 이율: 0.5% , 예치금+이자: 1005000.0원

// 생략

90일 차, 이율: 0.5% , 예치금+이자: 1005000.0원
100일 차, 이율: 1.0% , 예치금+이자: 1010000.0원

// 생략

180일 차, 이율: 1.0% , 예치금+이자: 1010000.0원
190일 차, 이율: 2.0% , 예치금+이자: 1020000.0원

// 생략

360일 차, 이율: 2.0% , 예치금+이자: 1020000.0원
```

<br>

### ✔️ 정리해봅시다.
#### 1. if 문장의 소괄호 안에는 어떤 타입의 결과가 제공되어야 하나요?
boolean

#### 2. if 조건에 맞지 않는 모든 경우를 처리할 때 사용하는 예약어는 뭔가요?
else

#### 3. switch를 사용할 수 있는 기본 자료형의 타입에는 어떤 것들이 있나요?
- long을 제외한 정수형(byte, short, int, long, char)
- 추가로 Enum, Character, Byte, Short, Integer도 가능
- Java 7 부터 String도 가능

#### 4. switch블록 안에서 비교 대상값 앞에 사용하는 예약어는 무엇인가요?
case

#### 5 switch 조건을 빠져나가도록 하는 예약어는 무엇인가요?
break

#### 6. switch 조건들에 맞지 않을 때 기본 처리를 하기 위한 예약어는 무엇인가요?
default

#### 7. while 문의 소괄호 안에는 어떤 형태의 결과가 제공되어야 하나요?
boolean

#### 8. while 문을 무조건 한번은 실행하게 하려면 어떻게 해야 하나요?
```java
do{

    // 무조건 한번 실행

}while(조건식){

    // 조건식이 true일 때까지 실행

}
```
#### 9. while문을 마음대로 빠져나가게 하려면 어떤 예약어를 사용하면 되나요?
break

#### 10. while문의 중간에 while문의 소괄호 점검 구문으로 건너뛰도록 할 때 사용하는 예약어는 무엇인가요?
continue

#### 11. for루프의 소괄호안의 가장 첫 구문(첫 세미 콜론 앞의 문장)은 for루프가 수행되는 동안 몇 번 수행되나요?
1번

#### 12. for루프의 소괄호 안의 중간에 있는 구문은 어떤 타입의 결과가 제공되어야 하나요?
boolean(treu면 반복문 실행)

#### 13. for루프의 소괄호 안의 마지막에 있는 구문에서는 어떤 작업을 수행하나요?
첫 구문에서 선언한 변수의 값을 증가 혹은 감소

<br>

***

<br>

## :pushpin: Chapter7

### ✔️직접해봅시다.
#### 작성 코드
```java
public class ManageHeight{
    // 인스턴스 변수 선언 : 반은 5개, 학생수는 미정
    int[][] gradeHeights = new int[5][];

    // main 함수
    public static void main(String[] args){
        // 객체 생성
        ManageHeight sample = new ManageHeight();
        // 2번 메소드 실행 : 반별 학생들의 키 데이터 지정
        sample.setData();
        // Loop를 위한 반번호 변수 생성
        int classNo=1;
        // 3~4번 메소드 실(for문) : 반별 학생들의 키 출력
        for (classNo=1; classNo<=sample.gradeHeights.length; classNo++){
            sample.printHeight(classNo);
        }
        // 반번호 초기화
        classNo = 1;
        // 5~6번 메소드 실행(while문) : 반별 학생들의 키 평균 출력
        while (classNo<=5){
            sample.printAverage(classNo);
            classNo++;
        }
    }
    // 2번 메소드 : 반별 학생의 키값 지정
    public void setData(){
        int [][] allHeights =  {{170,180,173,175,177},
                                {160,165,167,186},
                                {158,177,187,176},
                                {173,182,181},
                                {170,180,165,177,172}};

        for (int i=0; i<allHeights.length; i++){
            // 1차원 배열 선언(인스턴스 변수의 i번째 배열을 allHeights의 i번쨰 배열의 길이만큼 선언)
            gradeHeights[i] = new int[allHeights[i].length];
            for (int j=0; j<allHeights[i].length; j++){
                // 값 지정(두 변수의 i번째 배열의 j번쨰 위치에 값을 할당)
                gradeHeights[i][j] = allHeights[i][j];
            }
        }
    }
    // 3~4번 메소드  : 반별 학생들의 키를 출력
    public void printHeight(int classNo){
        // 해당 반에 해당하는 인덱스값 계산
        int classIdx = classNo-1;
        System.out.println("Class No." + classNo);
        // 계산한 인덱스에 해당하는 배열을 loop하면서 데이터 출력
        for(int StudentHeight : gradeHeights[classIdx]){
            System.out.println(StudentHeight);
        }
        System.out.println();
    }
    // 5~6번 메소드 : 반별 학생들의 키평균값 출력
    public void printAverage(int classNo){
        // 필요한 변수 생성(배열의 인덱스, 합계, 평균)
        int classIdx = classNo-1;
        double sum = 0.0;
        double average = 0.0;

        System.out.println("Class No." + classNo);
        // 계산한 인덱스에 해당하는 배열을 Loop하면서 합계 계산
        for(int studentHeight : gradeHeights[classIdx]){
          sum += studentHeight;
        }
        // 합계와 배열의 길이를 나눠 평균 계산
        average = (double)(sum/gradeHeights[classIdx].length);
        // 평균값 출력
        System.out.println("Height Average : " + average);
    }
}
```

#### 실행 결과
```
Class No.1
170
180
173
175
177

Class No.2
160
165
167
186

Class No.3
158
177
187
176

Class No.4
173
182
181

Class No.5
170
180
165
177
172

Class No.1
Height Average : 175.0
Class No.2
Height Average : 169.5
Class No.3
Height Average : 174.5
Class No.4
Height Average : 178.66666666666666
Class No.5
Height Average : 172.8
```
#### 아쉬운점
2차원 배열에 값을 지정하는 과정에서 배열을 초기화하는데 많이 미숙했다.(`setData()`메소드)

해설코드에서 값을 지정한 방법은 아래와 같다.
```java
//인스턴트 변수 선언
int gradeHeights[][];

public void setData() {
    // 2차원 배열 초기화
    gradeHeights = new int[5][];
    // 각 배열 초기화 및 값 지정(중괄호 활용)
    gradeHeights[0] = new int[] { 170, 180, 173, 175, 177 };
    gradeHeights[1] = new int[] { 160, 165, 167, 186 };
    gradeHeights[2] = new int[] { 158, 177, 187, 176 };
    gradeHeights[3] = new int[] { 173, 182, 181 };
    gradeHeights[4] = new int[] { 170, 180, 165, 177, 172 };
}
```
책을 다시 보면서 위 해설코드처럼 배열 선언을 중괄호를 활용해서 해보려했지만 계속 에러가 나와서 결국 반복문을 통해 값을 지정하는 방법을 선택했는데, 원했던 방법을 해설코드를 보고서 찾았다는 점이 아쉽다.

<br>

### ✔️정리해봅시다.
#### 1. 배열을 선언할 때 어떤 기호를 변수명의 앞이나 뒤에 사용해야 하나요?
[], 대괄호

#### 2. 배열의 첫번째 위치는 0인가요? 1인가요?
배열의 위치는 0부터 시작합니다.

#### 3. 배열을 선언할 때 boolean 배열의 크기만 지정했다면 boolean 배열의 [0] 위치에 있는 값은 무엇인가요?
false값이 기본값으로 설정됩니다.

#### 4. ArrayIndexOutOfBoundsException 이라는 것은 언제 발생하나요?
배열의 범위를 벗어난 위치값이 발견되었을 때 발생하는 에러메세지 입니다.

> 더 정확하게는 배열의 범위를 벗어난 위치를 참조하려 할 때 발생하는 에러 메세지입니다.

#### 5. 중괄호를 이용하여 배열을 초기화 할 때 중괄호 끝에 반드시 어떤 것을 입력해 주어야 하나요?
세미콜론(;) , 보통 중괄호 뒤에 세미콜론을 붙이는 일이 없기 때문에 빼먹지 않도록 주의해야 합니다.

#### 6. 2차원 배열을 정의할 때에는 대괄호를 몇 개 지정해야 하나요?
두개 지정합니다.

##### 예시
```java
int [][] arr = new int[5][5];
```

#### 7. 배열을 쉽게 처리해주는 for 문의 문법은 어떻게 되나요?
`for(자료형 변수 이름 : 배열 이름){}`

배열의 값들을 선언한 변수 이름에 하나씩 **순서대로 할당**하고 loop합니다.

##### 예시
```java
int [] array = {0, 1, 2, 3, 4, 5};

for(int index : array){
    System.out.println(index);
}
```
##### 실행결과
```
0
1
2
3
4
5
```

#### 8. 자바 프로그램에 데이터를 전달해 주려면 클래스 이름 뒤에 어떻게 구분하여 나열하면 되나요?
문자열 사이사이에 공백을 주면 이 공백을 기준으로 데이터를 나눠 전달합니다.

##### 예시
```java
public class className{
    public static void main(String[] args){
        for (String arg : args){
            System.out.println(arg);
        }
    }
}
```

##### 실행결과
```
$ java className a b c d e
a
b
c
d
e
$
```

#### 9. 자바 프로그램이 시작할 때 전달 받는 내용은 어떤 타입의 배열인가요?
String 배열입니다.


### ✔️추가 내용
#### 1. toSting()
- `toSting()` 메소드는 객체가 가지고 있는 정보를 문자열로 리턴하는 메소드
- Java의 모든 클래스 중 가장 최상위 클래스인 'Object' 클래스의 메소드로서 사용자가 생성하는 클래스가 기본적으로 상속받게 되는 메소드
- 객체가 가지고 있는 `toSting()` 메소드의 기본값은 '타입이름@고유번호'의 형태
- 이를 재정의(오버라이딩)을 통해 바꿀 수 있다.

> [참고사이트](https://selfdevelope.tistory.com/560)

<br>

***

<br>

## :pushpin: Chapter8

### ✔️직접해봅시다.
#### Student 클래스
```java
public class Student{
    // 1번, 인스턴스 변수 선언
    String name;
    String address;
    String phone;
    String email;

    // 2번, 생성자 선언(name만)
    public Student(String name){
        this.name = name;
    }
    // 3번, 생성자 선언(모든 변수)
    public Student(String name, String address, String phone, String email){
        this.name = name;
        this.address = address;
        this.phone = phone;
        this.email = email;
    }
    // 4번, toString 메소드 오버라이딩(재정의)
    public String toString(){
        return name + " " + address + " " + phone + " " + email;
    }
}
```
4번에서 선언한 toString() 메소드는 선언이 아닌 오버라이딩이다. toString은 상위 객체에서 이미 생성되어 있는 메소드고 Student 객체에서 메소드 실행 결과를 다르게 하기 위해 재정의한 것으로 이해해야 한다.

#### ManageStudent 클래스
```java
// 5번, 클래스 선언
public class ManageStudent{
    // 6번, main 메소드 생성
    public static void main(String[] args){
        // 8번, 객체 생성(초기화X, 기본값 null)
        Student[] student;
        // 9번, 7번 메소드 호출
        ManageStudent manage = new ManageStudent();
        student = manage.addStudent();
        // 12번, 10번 메소드 호출
        manage.printStudents(student);
    }
    // 7번, 메소드 생성(배열에 객체 생성)
    public Student[] addStudent(){
        Student[] student = new Student[3];
        student[0] = new Student("Kim");
        student[1] = new Student("Lee");
        student[2] = new Student("Park", "Icheon", "010-xxxx-xxxx", "kimcno3@naver.com");
        return student;
    }
    // 10번, 메소드 생성(배열값 출력)
    public void printStudents(Student[] student){
        // 11번, for문으로 배열내 값을 순서대로 출력
        for(int i=0; i< student.length; i++){
            System.out.println(student[i]);
        }
    }
}
```
8번에서 배열만 생성하고 초기화하지 않았다. 이렇게 초기화하지 않으면 배열의 기본값은 null로 설정된다.

11번에서 for문의 조건식은 아래와 같이 `:`(콜론)을 이용해서 설정할 수도 있다.
```java
    public void printStudents(Student[] student){
        for(Student info : student){
            System.out.println(student[i]);
        }
    }
```

#### 결과값
```
Kim null null null
Lee null null null
Park Icheon 010-xxxx-xxxx kimcno3@naver.com
```
<br>

### ✔️정리해봅시다.
#### 1. 생성자는 반드시 만들어야 하나요?
X, 생성자 선언은 필수가 아닙니다. 필요에 따라 매개변수를 설정한 생성자를 선언하고 그렇지 않다면 매개변수가 없는 생성자가 자동으로 선언됩니다.

#### 2. 만약 매개변수가 있는 생성자를 만들고, 매개변수가 없는 기본 생성자를 호출하면 어떻게 될까요?
에러가 발생합니다. 기본생성자가 자동으로 생성되는 경우는 선언된 생성자가 없을 경우만 해당하기 때문에 매개변수가 있는 생성자를 선언했다면 매개변수를 설정해야 합니다.

#### 3. 생성자의 개수는 제한이 있나요?
X, 같은 이름의 생성자를 선언할 수 있고 각 생성자에 매개변수를 다르게 선언할 수 있습니다. 이와 같은 방식을 **오버로딩**이라고 합니다.

#### 4. 인스턴스의 변수와 매개변수나 메소드 내에서 생성한 변수와 구분하기 위해서 사용하는 키워드는 무엇인가요?
`this` 키워드를 활용할 수 있습니다.

##### 예제
```java
public class ClassName{
    int var; // 인스턴스 변수
    public void methodName(int var){ // 매개변수
        this.var = var;
        // 인스턴스변수 = 매개변수
    }
}
```
위 예제처럼 this뒤에 나온 변수는 인스턴스변수를 가르키며 같은 변수명의 매개변수와 구분할 수 있습니다.

#### 5. 메소드 선언시 리턴 타입으로 지정한 데이터를 넘겨줄 때 사용하는 키워드는 무엇인가요?
`return`

#### 6. 메소드 선언시 아무 데이터도 리턴 타입으로 넘겨주지 않겠다는 것을 지정하는 키워드는 무엇인가요?
`void` , 메소드명 앞에 void를 추가하면 해당 메소드는 리턴값없이 메소드가 종료된다는 의미를 가집니다.

#### 7. 메소드 선언에 static 이 있는 것과 없는 것의 차이는 무엇인가요?
`static`이 있는 메소드는 객체를 생성하지 않아도 메소드를 호출할 수 있습니다.

또한! static 메소드는 static이 추가된 **클래스변수만을 사용**할 수 있습니다.

#### 8. 필자가 엄청나게 중요하다고 한 것 중 메소드의 이름은 같으나 매개변수를 다르게 하는 것의 명칭은 무엇인가요?
오버로딩(Overloading)

#### 9. 기본 자료형을 매개변수로 넘겨 줄 때 Pass by value인가요? 아니면 Pass by reference인가요?
Pass by value , 값 자체를 넘겨주는 것

#### 10. 참조 자료형을 매개변수로 넘겨 줄 때 Pass by value인가요? 아니면 Pass by reference인가요?
Pass by reference , 값이 저장된 메모리 주소를 넘겨주는 것

#### 11. 매개변수의 수가 가변적일 때 메소드 선언시 타입과 변수 이름 사이에 어떤 것을 적어줘야 하나요?
(변수타입...변수명)(마침표 3개를 공백없이!)
##### 예시
```java
public class ClassName{
    public static void main(String[] args){
        ClassName sample = new ClassName();
        numbers.methodName(1,2,3,4,5); // 매개변수값들이 배열의 값으로 할당
    }
    public void methodName(int...numbers){ // 호출시 numbers를 배열로 인식
    }
}
```

<br>

### ✔️추가내용
#### 1. DTO 추가 설명
DAO(Data Access Object)
- DTO로 받은 데이터를 데이터베이스에 저장하거나 가져오는 역할을 수행하는 객체

DTO(Data Transfer Object)
- 계층 간 데이터 교환을 하기 위해 사용하는 객체
- 로직을 가지지 않는 순수한 데이터 객체(getter & setter)

VO(Value Object)
- 값을 위해서만 사용되는 값 오브젝트
- ReadOnly 특징을 가지고 있다.

#### 2. static 변수 추가 설명
##### P.204 ~ 205의 예제 코드
```java
public class ReferenceStaticVariable{
    static String name; // 클래스변수 name
    public ReferenceStaticVariable(){}
    public ReferenceStaticVariable(String name){
        this.name = name; // 매개변수를 클래스변수에 할당해라! 라는 의미
    }
    public static void main(String[] args){
        ReferenceStaticVariable sample = new ReferenceStaticVariable();
        sample.checkName();
    }
    public void checkName(){
        ReferenceStaticVariable reference1 = new ReferenceStaticVariable("Kim");
        System.out.println(reference1.name); // Kim
        ReferenceStaticVariable reference2 = new ReferenceStaticVariable("Lee");
        System.out.println(reference1.name); // Lee
    }
}
```
위 예제를 보면 같은 `reference1`객체의 `name`값을 출력했는데 출력값은 다른 것을 확인할 수 있다.(객체의 변수를 출력한 것처럼 보인다.)

이는 매개변수값을 할당하는 변수 `name`이 클래스변수, 즉 **static**변수이기 때문에 위와 같은 결과값을 가지게 된건데, 자세히 설명하면 클래스 변수는 객체에 상관없이 하나의 메모리 주소만을 가지게 된다. 그렇기에 위 예제는 `reference1`만의 **인스턴스 변수**인 `name`에 매개변수값을 할당한 것이 아니라, 클래스 전체에 하나만 존재하는 **클래스변수**인 `name`에 매개변수 값을 할당한 것이다.(객체와는 무관하게 name이라는 변수는 해당 클래스에서 하나라는 뜻!)

그러므로 `name`은 `Kim`으로 한번, `Lee`로 한번씩 값을 할당받은 것이다.

> [참고 사이트](https://wikidocs.net/228)

<br>

***

<br>

## :pushpin: Chapter9

### ✔️직접해봅시다.
#### 1. godofjava 폴더 아래에 b 폴더 생성
```
C:\godofjava>mkdir b
```

#### 2. b 폴더 아래 array, control, operator, variable 폴도 생성
```
// b 폴더로 이동
C:\godofjava>cd b

// 폴더 생성
C:\godofjava\b> mkdir array
C:\godofjava\b> mkdir control
C:\godofjava\b> mkdir operator
C:\godofjava\b> mkdir variable
```

#### 3. Array.main.java 파일을 godofjava/b/array 폴더로 이동
```
C:\godofjava> mv ArrayMain.java b/array
```

#### 4. ArrayMain.java package 선언
```java
package b.array;

public class ArrayMain{
    public static void main(String[] args){
            for(String arg : args){
                System.out.println(arg);
            }
    }
}
```

#### 5. ArrayMain.java 컴파일
```
// 컴파일
C:\godofjava> javac b/array/ArrayMain.java

// 실행
C:\godofjava> java b/array/ArrayMain a b c d
a
b
c
d
```

#### 6. ControlIf 파일은 b.control , OperatorConditional 파일은 b.operator , VariableTypes 파일은 b.variable 폴더로 이동 후 컴파일
```
// 파일이동
C:\godofjava> mv ControlIf.java b/control
C:\godofjava> mv OperatorConditional.java b/operator
C:\godofjava> mv VariableTypes.java b/variable

// 컴파일
C:\godofjava> javac b/control/ControlIf.java
C:\godofjava> javac b/operator/OperatorConditional.java
C:\godofjava> javac b/variable/VariableTypes.java

// 실행결과
C:\godofjava> java b/control/ControlIf
It's smaller or equal than 5.
It's smaller than 5.

C:\godofjava> java b/operator/OperatorConditional
80 : true
30 : false

C:\godofjava> java b/variable/VariableTypes
It's VariableTypes Class
```


<br>

### ✔️정리해봅시다.
#### 1. 패키지를 선언할 때 사용하는 예약어는 무엇인가요?
package

#### 2. 패키지 선언은 클래스 소스 중 어디에 위치해야 하나요?
가장 위에 위치해야 합니다.

package 예약어 위에 주석이나 공백은 상관없지만, 다른 자바 문장 하나라도 포함되어 있으면 안된다.

#### 3. 패키지를 선언할 때 가장 상위 패키지의 이름으로 절대 사용하면 안되는 단어는 무엇인가요?
java

java는 Oracle에서 사용하는 패키지 이름이기 때문에 그외 사용자에게는 제한되어 있다.

#### 4. 패키지 이름에 예약어가 포함되어도 되나요?
아니오

#### 5. import는 클래스 내에 선언해도 되나요?
아니오

예시로 AccessCall.java에서 import 선언을 class 내에 선언해 봤다.
```java
package c.javapackage;

public class AccessCall{

  import c.javapackage.sub.AccessModifier; // 클래스내에 import 선언

    public static void main(String[] args){
        AccessModifier accessModifier = new AccessModifier();
        accessModifier.publicMethod();
        accessModifier.protectedMEthod();
        accessModifier.packagePrivateMethod();
        accessModifier.privateMethod();
    }
}
```
이후 컴파일 해보니 다음과 같은 에러가 발생했다.
```
$ javac c/javapackage/AccessCall.java
c\javapackage\AccessCall.java:5: error: illegal start of type // 문법적
  import c.javapackage.sub.AccessModifier;
  ^
c\javapackage\AccessCall.java:5: error: ';' expected // 세미콜론 미작성
  import c.javapackage.sub.AccessModifier;
        ^
c\javapackage\AccessCall.java:5: error: illegal start of type
  import c.javapackage.sub.AccessModifier;
          ^
c\javapackage\AccessCall.java:5: error: ';' expected
  import c.javapackage.sub.AccessModifier;
                      ^
c\javapackage\AccessCall.java:5: error: <identifier> expected // 식별자 미작성
  import c.javapackage.sub.AccessModifier;
                                         ^
5 errors
```
간단하게 말해서 문법적으로 허용되지 않는 에러를 발생시킨다.

#### 6. 같은 패키지에 있는 클래스를 사용할 때 import를 해야 하나요?
아니오

주의할 점은 상위 패키지에 있는 클래스라도 하위 패키지에서 선언해야 할 때 import 선언을 해야한다. 다시 말해 같은 패키지가 아니라면 무조건 import를 해야한다.

#### 7. 특정 패키지에 있는 클래스들을 모두 import할 때 사용하는 기호는 무엇인가요?
*

##### 사용 예시
```java
import c.javapackage.sub.*
```
위와 같이 선언하면 해당 패키지의 모든 클래스를 import 할 수 있다.

#### 8. 클래스에 선언되어 있는 static한 메소드나 변수를 import하려면 어떻게 선언해야 하나요?
import static

#### 9. 접근 제어자 중 가장 접근 권한이 넓은 (어떤 클래스에서도 접근할 수 있는) 것은 무엇인가요?
public

#### 10. 접근 제어자 중 가장 접근 권한이 좁은 (다른 클래스에서는 접근할 수 없는) 것은 무엇인가요?
private

#### 11. 접근 제어자 중 같은 패키지와 상속관계에 있는 클래스만 접근할 수 있도록 제한하는 것은 무엇인가요?
protected

#### 12. Calculate.java라는 자바 소스가 있을 경우, 그 소스 내에는 Calculate라는 클래스외에는 ( )으로 선언된 클래스가 있으면 안된다. 여기서 괄호 안에 들어가야 하는 것은 무엇인가요?
public

<br>

***

<br>

## :pushpin: Chapter10


### ✔️직접해봅시다.


<br>

### ✔️정리해봅시다.


<br>

### ✔️추가내용
#### 1. super() 상세 내용
p.245 ~ 247에 super()에 대한 설명이 나오는데 몇몇 문장들이 이해가 안가서 추가 설명을 찾아봤다.

super()가 정확히 어떤 의미를 가지는지 간단하게 설명하자면 **부모 클래스**를 가르킨다고 말할 수 있다. 반대의 개념으로는 this가 될 것이다.

##### 예시
```java
public class PrintInfo{
    public static void main(String[] args){
        Child child = new Child(); // 자식 클래스 생성

        child.printParentAge(); // 부모클래스의 변수를 출력
        child.printChildAge(); // 자식클래스의 변수를 출력
    }
}
// 부모 클래스
class Parent{
    public Parent(){}
    String name = "Kim";
    int age = 56;
}
// 자식 클래스
class Child extends Parent{
    public Child(){}
    String name = "Lee";
    int age = 27;
    // 자식클래스에서 부모클래스 변수 지정(super)
    public void printParentAge(){
        System.out.println(super.name + "의 나이는" + super.age + "입니다.");
    }
    // 자식클래스에서 자식클래스 변수 지정(this)
    public void printChildAge(){
        System.out.println(this.name + "의 나이는" + this.age + "입니다.");
    }
}
```
##### 실행결과
```
Kim의 나이는56입니다.
Lee의 나이는27입니다.
```

위 예시에서 보면 자식 클래스에서 `super.변수명`의 형식으로 코드를 작성하면 **부모클래스의 인스턴스변수를 지정**할 수 있다.

반대로 `this.변수명`은 **해당 클래스의 인스턴스 변수를 지정**하게 된다.

`자식 클래스를 컴파일할 때, 자동으로 super()이란 코드가 추가되어 컴파일한다??`

super에 대한 개념을 간단하게 이해했어도 위 문장은 이해되지 않았는데 천천히 읽어보니 말 그대로 자식클래스를 컴파일할 때 코드 작성자가 적지 않아도 `super()`라는 코드가 추가된다는 말이였다. 이 말을 코드로 표현해보면 아래 예시와 같다.

##### 예시
```java
// 위 코드 생략

class Child extends Parent{
    public Child(){
        // super();  -> 이 코드가 자동으로 추가된다.
    }

    // 아래 코드 생략
}
```

그렇다면 부모 클래스의 생성자가 매개변수를 가지고 있다면 당연히 문제가 생기는 구조였다.

자식 클래스에서 자동으로 생성되면서 부모클래스의 생성자를 가르키는 `super()` 코드는 매개변수값이 지정되어있지 않기 때문에 부모 클래스에서 매개변수를 가진 생성자를 선언했다면 자식 클래스에서도 매개변수값을 지정해줘야 하는 것이 맞다.

##### 예시
```java
// 위 코드 생략

class Parent{
    // 매개변수를 가진 생성자 선언
    public Parent(String name){
        this.name = name; // 매개변수를 인스턴스 변수로 지정
    }
    String name;
    int age = 56;
}

class Child extends Parent{
    public Child(){
        // 부모클래스의 매개변수값 지정
        super("Kim");
    }

    // 아래 코드 생략

}
```

위 예제처럼 부모 클래스에서 매개변수를 가진 생성자를 선언했다면 자식클래스의 생성자에서 super() 를 사용해 매개변수값을 동일한 자료형으로 지정해줘야 한다.

<br>
