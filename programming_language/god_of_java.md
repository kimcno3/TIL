# :pushpin: 자바의 신 정리
> 상세 내용은 책을 구매하셔서 확인하시기 바랍니다.

<br>

## :pushpin: 목차
**:pushpin: Volume 1**
- [:pushpin: Chapter1](#pushpin-Chapter1)
- [:pushpin: Chapter2](#pushpin-Chapter2)
- [:pushpin: Chapter3](#pushpin-Chapter3)
- [:pushpin: Chapter4](#pushpin-Chapter4)
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
- 자바에서 가장 작은 단위로 상태와 행동을 가집니다. 여기서 상태는 변수, 행동은 메소드를 통해 구현할 수 있습니다. 현실의 사물이나 추상적인 개념을 클래스로 표현할 수 있습니다. 이러한 방식의 프로그래밍을 객체 지향 프로그래밍이라고 합니다.

**클래스 선언 방법** <br>
답 :
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
답 :
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
- 매개변수는 메소드명 뒤에 오는 소괄호 안에 적습니다.

#### **4. 메소드 이름 앞에 꼭 적어 줘야 하는 건 뭐죠?**
- 접근 제어자와 리턴타입입니다.

#### **5. 클래스가 갖고 있어야 한다고 한 두 가지는 뭐죠?**
- 상태와 행동, 구체적으로 변수와 메소드입니다.

#### **6. 메소드에서 결과를 돌려주면 어떤 예약어를 사용해야 하나요?**
- `return`을 사용합니다.

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

String문자열의 배열이 들어갑니다.

#### **3. 만약 여러분들이 만든 클래스에 main() 메소드가 없다면, java 명령어로 그 클래스를 수행할 수 있나요?**
- public static void main(String[] args)로 선언되어 있는 메소드가 클래스에 없으면, 해당 클래스를 실행할 수는 없다.

#### **4. System.out.println() 메소드는 어떤 용도로 사용하나요?**
- System.out.println() 메소드는 자바를 실행한 창에서 문자열을 출력하는데 사용됩니다.

#### **5. System.out.print() 메소드는 System.out.println() 메소드와 어떤 차이가 있나요?**
답 :
- System.out.print() -> 줄바꿈 X
- System.out.println() -> 줄바꿈 O

#### **6. `//` 는 무엇을 하는데 사용하는 기호인가요?**
- `//`는 한 줄 주석을 의미한다. 따라서, 해당 코드의 `//` 뒤에 있는 모든 내용은 무시된다.

#### **7. `/*` 로 시작하고, `*/`로 끝나는 사이에 있는 소스들을 어떻게 되나요?**
- `/*`으로 시작하여 `*/`으로 끝나는 주석은 블록 주석으로, 해당 블록 내의 모든 내용은 컴파일시 무시된다.

#### **8. 메소드를 선언할 때 반드시 꼭 있어야 하는 세가지는 무엇인가요?**
- 메소드에는 반드시 "리턴 타입", "메소드 이름", "메소드 내용"이 있어야만 한다.

<br>

### ✔ 추가 내용
#### **사용자변수와 시스템변수의 차이**
> [참고 사이트](https://wikim.tistory.com/232)
- 사용자 변수
    - 로그인된 계정 내에서 사용하는 변수
    - 사용자 계정별로 설정되어 있는 PATH가 다릅니다.

- 시스템 변수
    - 컴퓨터 내에서 사용하는 변수
    - 한번 PATH를 설정해 두면 어떤 계정이든 사용 가능합니다.

#### **JVM, JRE, JDK 란?**
> [참고 사이트1](https://goodgid.github.io/Java-JDK-JRE/)

> [참고 사이트2](https://velog.io/@ggob_2/java-study-1#7-jvm%EC%9D%98-%EA%B5%AC%EC%84%B1-%EC%9A%94%EC%86%8C)

- JVC(Java Virtual Machine)
    - 컴파일 이후, 바이트코드로 구성된 자바 파일(`.class` 확장자)을 기계어로 해석하여 운영체제에서 실행시키는 역할을 합니다.

- JRE(Java Runtime Environment)
    - **JVM**을 포함하여 자바 프로그램을 실행시키기 위해 필요한 라이브러리 및 기타 파일이 포함된 **패키지**
    - **자바 실행 환경**이라고 이해할 수 있습니다.
    - **java.exe** 파일이 포함되어 있습니다.(JVM을 구동시키기 위한 명령 프로그램)


- JDK(Java Development Kit)
    - 자바 프로그래밍을 위해 필요한 도구
    - 대표적으로 컴파일러(javac.exe)가 JDK에 포함됩니다.

#### **java파일 실행시 파일명만 필요한 이유**
> [참고 사이트](https://8iggy.tistory.com/m/233)

JVM을 구동하기 위해 `java filename` 명령어를 실행하는데, 이는 "JVM이 filename에 해당하는 파일을 실행한다"가 아니라 "filename을 가진 바이트코드에 main메소드가 존재한다" 라는 사실을 전달하는 의미입니다.

그래서 확장자명을 포함하여 java.exe 파일을 실행시키면 확장자명까지 파일명으로 인식하여 main 메소드가 없다 또는 해당 파일명을 찾을 수 없습니다 라는 에러가 발생합니다.

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

클래스 범주 안에 객체가 포함되어 있고, 클래스의 복제품 격에 객체라고 할 수 있다.

#### **2. 객체를 생성하기 위해서 꼭 사용해야 하는 예약어는 뭐라고 했죠?**
- **new 키워드**를 사용하여 클래스의 객체를 생성한다.

#### **3. 객체를 생성하기 위해서 사용하는 메소드 같이 생긴 클래스 이름에 소괄호가 있는 것을 뭐라고 하나요?**
- **생성자(Constructor)** 를 통하여 클래스의 객체를 생성한다.

#### **4. 객체의 메소드를 사용하려면 어떤 기호를 객체이름과 메소드 이름 사이에 넣어주어야 하나요?**
- **마침표(.)** 를 사용합니다.

클래스의 변수나 메소드를 호출하려면 "객체이름.변수", "객체이름.메소드이름()"와 같이 사용하면 된다.

#### **5. 여러분들이 메소드를 사용하기 위해서는 어떤 것을 만들어야 하나요?**
- 클래스의 **객체**를 생성해야만 메소드를 사용할 수 있다.

#### **6. 위의 문제에서 만들어야 하는 것은 어떤 예약어를 사용하고, 클래스의 무엇을 사용해야 하나요?**
- **new 키워드**를 사용하여 **생성자**를 호출해야만 된다.

<br>

### ✔ 추가내용
#### **1. 멤버변수**
> [참고 사이트](https://digiconfactory.tistory.com/entry/%EC%9E%90%EB%B0%94-%ED%8A%9C%ED%86%A0%EB%A6%AC%EC%96%BC-5-9-%EB%B3%80%EC%88%98-%EC%9C%A0%ED%9A%A8%EB%B2%94%EC%9C%84-Scope)

**멤버변수(Instance Variable)** 는 객체를 생성해야만 사용할 수 있는 변수를 의미하며 **객체 생성시, 해당 객체의 메소드에서 사용가능**합니다.

위에 **직접해봅시다**에서 4,5번 메소드 또한 멤버변수를 사용하는 메소드였기에 따로 매개변수로 지정하지 않아도 사용이 가능했던 것입니다.

#### **2. main 함수 실행 순서**
> [참고사이트](https://codingffler.tistory.com/16)

자바의 신 Github 저장소에서 찾은 **직접해봅시다** 의 [모범 코드](https://github.com/godofjava/GodOfJava2nd/blob/master/Chapter03/src/Profile.java)와 내가 작성한 코드를 비교해봤을 때, main() 메소드의 위치가 다른 것을 볼 수 있었다.

모범 코드에서는 `main()` 메소드가 가장 먼저 작성되어 있고, 그 이후로 클래스의 필드와 메소드가 선언되어 있었다.

이 부분에서 단순한 생각으로 클래스의 필드와 메소드가 먼저 선언된 다음, main() 메소드가 실행되어야 하는 것이 맞지 않은가 하는 의문이 생겼다.

자바스크립트에서 호이스팅 개념이 있듯이 자바에서도 비슷한 개념이 있나 궁금증이 생겨 찾아본 결과, 간단한 해답을 찾았다.

바로 자바로 구성된 프로그램, 파일을 실행시에는 **main() 메소드가 가장 먼저 실행된다**는 것이다.

즉, `main()` 메소드가 가장 먼저 실행되면서 객체를 생성하고 그 이후로 생성된 객체의 메소드를 호출하는 순서로 코드가 진행되는 것이다.

그렇기 때문에 main 메소드가 클래스 내에서 가장 먼저 작성되어도 문제될 점은 없다.
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
#### **3, 5, 7. 각 인스턴스 변수으 값을 매개변수로 지정하는 메소드 생성 -> `setOOOO(parameter)`**
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
- 아니오

#### 3. 자료형에는 기본 자료형과 어떤 자료형이 있나요? *
- 참조 자료형

#### 4. 기본 자료형에는 몇가지가 있나요? *
- 8가지

#### 5. 기본 자료형 중 정수형에는 어떤 것들이 있나요? *
- byte, short, int, long, char

#### 6. byte는 몇 비트(bit)로 되어 있나요? *
- 8비트

#### 7. byte 타입은 왜 만들었을까요? *
- 저장공간의 활용을 극대화 하기 위해서
- 작은 단위의 데이터를 저장할 때, 불필요한 데이터 공간 차지를 방지하기 위해 byte로 저장합니다.

#### 8. int와 long중 어떤 타입이 더 큰 숫자를 처리할 수 있나요? *
- long

#### 9. 소수점을 처리하는 타입은 어떤 것이 있나요? *
- float, double

#### 10. char는 정수형인가요? *
- 예

#### 11. a라는 값을 char로 정의할 때 어떤 기호로 감싸주어야 하나요? *
- ''(홀따옴표)

#### 12. true와 false 두개의 값만을 가지는 타입은 어떤 것인가요? *
- boolean

<br>

### ✔️ 추가 내용
#### 1. 가비지 콜렉터(Garbage Collector)
> [참고 사이트](https://madplay.github.io/post/java-garbage-collection)

- **가비지(Garbage)** 란 객체나 배열을 가르키는 레퍼런스가 없는 경우를 의미합니다.
- 메모리 확보 위해 가비지를 삭제하는 작업 자체는 **가비지 콜렉션**
- 가비지 콜렉션을 하는 것이 **가비지 콜렉터**라고 합니다.

#### 2. shortMax+1 === 32768???
> [참고 사이트1](https://kephilab.tistory.com/27)

> [참고 사이트2](https://stackoverflow.com/questions/42682558/largest-java-short-32767-plus-1-not-turning-negative)

**4장 89페이지**에서 **shortMax**에서 1을 더하면 최소값이 나와야 하는데 최대값을 넘어선 값이 나와 당황했다. 그 이유를 찾아보니 short 타입의 값에 단순히 1을 더하면 **int 타입으로 타입이 자동 변환된다**고 한다.

구체적으로 설명하면

1. 정수 연산시에 int가 기본 타입이다.
2. 게다가 다른 타입을 연산할 때 큰 타입으로 자동 변환된다고 한다.
3. 또한 피연산자는 4byte 단위로 계산되어 4byte보다 작은 byte, short, char은 int로 자동 변환된다.

그렇기 때문에 계산 오류를 막기 위해서는 (byte), (short) 코드를 연산식 앞에 추가해줘야 자동 타입 변환을 방지하여 예제에서 원하는 값을 구할 수 있습니다.

해당 내용은 **4장 87페이지** 에서도 언급되는 부분입니다.