## :pushpin: 객체 지향 프로그래밍(Object-Oriented Programming)
### OOP 정의
객체 지향 프로그래밍은 프로그램을 구성하는데 있어 필요한 데이터나 기능을 `객체`라는 단위로 나누고, 여러 객체들 간의 `상호작용`을 통해 로직을 구성하는 프로그래밍 기법이라고 할 수 있습니다.

### OPP의 장점
1. 유지보수하기 용이하다.
2. 코드 재사용이 가능하다.
3. 큰 프로젝트 개발시 적합하다.

### OPP의 단점
1. 속도가 느리다.
2. 객체를 정의하는 클래스가 많아지면 용량이 커진다.
3. 설계시 많은 시간과 노력이 필요하다.

### OPP의 특징
1. **클래스와 인스턴스**
    - 클래스는 자바에서 객체 지향 프로그래밍을 위해 구분하는 **가장 작은 단위**입니다. 

    - 클래스라는건 **객체를 생성하기 위한 설계도**라고 말하고 싶습니다. 공통적인 상태나 기능을 소화하는 객체를 생성하는데 있어서 하나의 클래스로 미리 정의해 둔다면, 해당 클래스의 특징을 활용할 수 잇는 객체는 생성만 해서 활용할 수 있고 여러개의 객체를 생산할 때도 용이한 구조를 가질 수 있습니다.

2. **추상화**
    - 여러 코드를 조합하고 구성해서 추상적인 기능을 할 수 있는 코드를 만들고 이를 하나의 클래스로 정의한다면, 코드의 구성을 사용자가 직접 보고 이해하지 않아도 클래스 그 자체로 하나의 기능을 소화시킬 수 있습니다.

3. **캡슐화**
    - 복잡한 기능들은 `Class`안으로 숨기고, 사용자가 알아보기 쉬운것만 바깥으로 꺼내놓는 것을 캡슐화라고 한다.

    - 클래스 내부에 선언된 변수나 메소드 중 외부로 노출시키면 안되는 내용은 숨기고, 접근을 제한시킬 수 있습니다. 이를 통해 코드의 보안성을 보장해 줄 수 있습니다.

4. **상속**
    - 클래스 간에 상속이 가능합니다. 클래스 간에도 관계성에 따라 중복적으로 사용되는 코드들의 경우에는 상위 계층의 클래스로 묶어서 관리하면서 중ㅇ복 코드를 줄이고 필수 코드를 재사용할 수 있습니다.

5. **다형성**
    - 같은 이름의 변수나 메소드라도 클래스의 용도에 따라 다른 결과를 리턴할 수 있도록 코드를 수정할 수 있습니다. 이는 프로그램 구성에 있어 유연성을 증가시켜 주는 장점이 있다고 할 수 있습니다.

> [참고사이트](https://m.blog.naver.com/PostView.nhn?blogId=29java&logNo=70187502359&proxyReferer=https:%2F%2Fwww.google.com%2F)

> [참고사이트](https://velog.io/@srparkgogo/%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8DOOP%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%802)

> [참고사이트](https://jeong-pro.tistory.com/95?category=793347)

<br>

## :pushpin: java파일 실행시 파일명만 필요한 이유
JVM을 구동하기 위해 `java filename` 명령어를 실행하는데, 이는 "JVM이 filename에 해당하는 파일을 실행한다"가 아니라 "filename을 가진 바이트코드에 main메소드가 존재한다" 라는 사실을 전달하는 의미입니다.

그래서 확장자명을 포함하여 java.exe 파일을 실행시키면 확장자명까지 파일명으로 인식하여 main 메소드가 없다 또는 해당 파일명을 찾을 수 없습니다 라는 에러가 발생합니다.

> [참고 사이트](https://8iggy.tistory.com/m/233)

<br>

## :pushpin: switch문에서 long이 제외된 이유
`switch문`에 비교대상변수로 지정 가능한 자료형은 **`long`을 제외**한 정수형과 `몇몇 특별한 타입`으로 제한한다.

굳이 `long` 타입만 제외한 이유가 궁금해서 구글링을 해본 결과 stackoverflow에 올라와 있는 몇몇 답변을 참고해봤다.

**답변1** : [링크](https://stackoverflow.com/questions/2676210/why-cant-your-switch-statement-data-type-be-long-java)
> Obviously, one can have a long that has only a few possible values, so that it is reasonable to use it as a switch expression, but that is unusual. Mainly, long is used when there are too many values for int, and so far too many values for a switch expression.

**답변2** : [링크](https://stackoverflow.com/questions/13951419/why-cant-java-switch-over-the-primitive-long)

> A switch can essentially be implemented in two ways (or in principle, a combination): for a small number of cases, or ones whose values are widely dispersed, a switch essentially becomes the equivalent of a series of ifs on a temporary variable (the value being switched on must only be evaluated once). For a moderate number of cases that are more or less consecutive in value, a switch table is used (the TABLESWITCH instruction in Java), whereby the location to jump to is effectively looked up in a table.
>
>Either of these methods could in principle use a long value rather than an integer. But **I think it was probably just a practical decision to balance up the complexity of the instruction set and compiler with actual need**: the cases where you really need to switch over a long are rare enough that it's acceptable to have to re-write as a series of IF statements, or work round in some other way (**if the long values in question are close together, you can in your Java code switch over the int result of subtracting the lowest value**).

결론은 `switch`문은 비교대상변수를 분기하면서 나눠진 값의 범위에 따라 작성할 코드를 나누기 위해 사용되는 조건문인데, 그 변수로 `long` 타입의 **큰 수를 지정할 경우가 거의 없고 비효율적**이라는 판단이다. 

`long` 타입으로 선언해야 하는 매우 큰 정수를 가지고 switch문을 만들어야 한다면 **int타입으로 쪼개서 활용하는 것이 좋을 것**이라는 의견이다.

<br>

## :pushpin: DTO 추가 설명
DAO(Data Access Object)
- DTO로 받은 데이터를 데이터베이스에 저장하거나 가져오는 역할을 수행하는 객체

DTO(Data Transfer Object)
- 계층 간 데이터 교환을 하기 위해 사용하는 객체
- 로직을 가지지 않는 순수한 데이터 객체(getter & setter)

VO(Value Object)
- 값을 위해서만 사용되는 값 오브젝트
- ReadOnly 특징을 가지고 있다.(getter만)

사용자로부터 받아온 데이터를 DTO를 통해 클래스화 한 다음 전송되면, DAO가 DTO에서 저장된 데이터를 가져와 DB에 저장하는 방식으로 작동됩니다.

> [참고 사이트 1(DTO, DAO)](https://java117.tistory.com/8?category=806351)

> [참고 사이트 2(DTO, VO)](https://java117.tistory.com/9?category=806351)

<br>

## :pushpin: System.out.println() 추가 설명
`System.out.println()` 를 좀 더 자세히 분리해서 호출 과정을 살펴보았다.

- `System` 클래스 : **표준 입력과 출력, 에러**와 관련된 필드나 메소드가 선언된 클래스
- `out` : 표준 출력과 관련된 메소드를 가진 `PrintStream` 타입의 **객체**이자 **static 변수(클래스 변수)**
- `println()` : `PrintStream` 클래스에 선언된 메소드로 매개변수에 할당된 데이터값을 콘솔에 출력

클래스 변수를 호출할 때에는 클래스 변수를 선언한 클래스 타입의 객체를 통해서가 아니라, 클래스명을 그대로 가져와 호출한다.
- `System.out` : `System`클래스의 클래스 변수인 `out`을 호출한다.

static으로 선언되지 않은 변수나 메소드는 객체를 통해 호출해온다.
- `System.out.println()` : `out` 객체를 통해 해당 타입(`PrintStream`)에 선언된 public 메소드인 `println()`메소드를 호출한다.

> [참고사이트](https://www.quora.com/Why-is-System-out-written-before-print-in-Java)

<br>