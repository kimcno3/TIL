# :pushpin: 자바의 신 정리
> 상세 내용은 책을 구매하셔서 확인하시기 바랍니다.

<br>

## :pushpin: 목차
**:pushpin: Volume 1**
- [:pushpin: Chapter1](#pushpin-Chapter1)
- [:pushpin: Chapter2](#pushpin-Chapter2)

<br>

## :pushpin: Chapter1
> 프로그래밍이란 무엇인가?

### 직접해 봅시다.
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

### 정리해 봅시다.
#### **1. 클래스가 뭔가요?**
답 : 자바에서 가장 작은 단위로 상태와 행동을 가집니다. 여기서 상태는 변수, 행동은 메소드를 통해 구현할 수 있습니다. 현실의 사물이나 추상적인 개념을 클래스로 표현할 수 있습니다. 이러한 방식의 프로그래밍을 객체 지향 프로그래밍이라고 합니다.

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
답 : 클래스에서 "행동"의 역할을 의미하며 일련의 과정을 통해 새로운 값을 생산, 계산 및 반환합니다.

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
답 : 매개변수는 메소드명 뒤에 오는 소괄호 안에 적습니다.

#### **4. 메소드 이름 앞에 꼭 적어 줘야 하는 건 뭐죠?**
답 : 접근 제어자와 리턴타입입니다.

#### **5. 클래스가 갖고 있어야 한다고 한 두 가지는 뭐죠?**
답 : 상태와 행동, 구체적으로 변수와 메소드입니다.

#### **6. 메소드에서 결과를 돌려주면 어떤 예약어를 사용해야 하나요?**
답 : `return`을 사용합니다.

<br>

***

<br>

## :pushpin: Chapter2
### 직접해 봅시다.
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

### 정리해 봅시다.
#### **1. main() 메소드의 메소드 이름 앞에는 어떤 예약어들이 들어 가나요? (순서대로 쓰세요)**
답 : `public static void` main(String[] args){}
- public : 어떤 클래스에서도 접근 가능
- static : 객체를 생성하지 않아도 접근 가능한 메소드
- void : 리턴값이 없음

#### **2. main() 메소드의 매개변수에는 어떤 값이 들어가나요?**
답 : public static void main(`String[] args`){}

String문자열의 배열이 들어갑니다.

#### **3. 만약 여러분들이 만든 클래스에 main() 메소드가 없다면, java 명령어로 그 클래스를 수행할 수 있나요?**
답 : public static void main(String[] args)로 선언되어 있는 메소드가 클래스에 없으면, 해당 클래스를 실행할 수는 없다.

#### **4. System.out.println() 메소드는 어떤 용도로 사용하나요?**
답 : System.out.println() 메소드는 자바를 실행한 창에서 문자열을 출력하는데 사용됩니다.

#### **5. System.out.print() 메소드는 System.out.println() 메소드와 어떤 차이가 있나요?**
답 :
- System.out.print() -> 줄바꿈 X
- System.out.println() -> 줄바꿈 O

#### **6. `//` 는 무엇을 하는데 사용하는 기호인가요?**
답 : `//`는 한 줄 주석을 의미한다. 따라서, 해당 코드의 `//` 뒤에 있는 모든 내용은 무시된다.

#### **7. `/*` 로 시작하고, `*/`로 끝나는 사이에 있는 소스들을 어떻게 되나요?**
답 : `/*`으로 시작하여 `*/`으로 끝나는 주석은 블록 주석으로, 해당 블록 내의 모든 내용은 컴파일시 무시된다.

#### **8. 메소드를 선언할 때 반드시 꼭 있어야 하는 세가지는 무엇인가요?**
답 : 메소드에는 반드시 "리턴 타입", "메소드 이름", "메소드 내용"이 있어야만 한다.

<br>

### 추가 내용
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
