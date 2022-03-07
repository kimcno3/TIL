# :pushpin: JAVA
> 자바 주요 개념들을 모아놓은 파일입니다.

## :pushpin: 자바의 신 정리
[요약 정리글](https://github.com/kimcno3/godofjava)

## :pushpin: 환경변수 설정
환경변수란 운영체제가 컴퓨터를 동작시키는데 참조하는 변수를 의미한다.

그리고 PATH를 설정한다는 것은 운영체제가 컴퓨터 내 어떠한 디렉토리에 위치하고 있어도 특정 디렉토리 내 파일을 인식시키기 위해 해당 디렉토리를 가르키는 경로를 설정한다는 의미이다. 그래서 PATH로 설정된 경로(특정 디렉토리)에 저장된 파일은 cmd나 터미널가 어느 위치에 있더라도 실행시킬 수 있다.

**그럼 자바에서 환경변수 설정이 왜 필요한건가?**

Java 디렉토리에는 JDK와 JDE로 나눌 수 있다. JDK는 프로그램 개발 및 실행을 위한 파일들이 저장된 디렉토리라면 JDE는 오직 실행만을 위한 파일들이 저장된 디렉토리다.

그렇기 때문에 자바는 JDK를 환경변수로 설정해야 되고 그 중에서도 bin 디렉토리를 PATH로 설정해야 한다.

bin 디렉토리에는 자바의 컴파일러인 `javac.exe` 파일과 컴파일된 `.class` 파일을 실행시키는 `java.exe` 파일이 있는데, 위 두 실행파일을 통해 자바 파일을 실행시킬 수 있으므로 두 실행파일은 어떤 위치에서도 실행시킬 수 있어야 한다(실행시키고자 하는 클래스파일이 저장된 디렉토리에서 실행시켜야 하기 때문에). 그러므로 bin 디렉토리로 PATH를 설정하는 것이 일반적이다.

-  `windows`에서 PATH 설정 시에는 제어판에서 환경변수 설정을 손쉽게 설정할 수 있게끔 기능을 지원해주기 때문에 이를 활용하여 설정할 수 있다.

- 다만 `MacOS`의 경우에는 터미널을 통해서 `.bash_profile` 이라는 파일에 환경변수를 추가해준다.

> [참고사이트](https://shinjekim.github.io/java/2020/01/03/%EC%9E%90%EB%B0%94-%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0/)

<br>

## :pushpin: 사용자변수와 시스템변수의 차이
- 사용자 변수
    - 로그인된 계정 내에서 사용하는 변수
    - 사용자 계정별로 설정되어 있는 PATH가 다릅니다.

- 시스템 변수
    - 컴퓨터 내에서 사용하는 변수
    - 한번 PATH를 설정해 두면 어떤 계정이든 사용 가능합니다.
> [참고 사이트](https://wikim.tistory.com/232)

<br>

## :pushpin: JVM, JRE, JDK
- JVM(Java Virtual Machine)
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

<br>

## :pushpin: JVM 구성요소
JVM은 크게 **네가지 구성요소**로 나눌 수 있다.

![](https://blog.kakaocdn.net/dn/pjywN/btqSduBXLIK/2QEL5c2nEJXRm0cyhvwxF1/img.png)

출처 : https://steady-coding.tistory.com/305

1. **클래스 로더(Class loader)**
    - JVM 내로 클래스 파일을 로딩하는 역할을 수행하는 모듈로써 런타임 내에서 동적으로 파일을 로딩합니다.
    - JVM이 동작하는 중에 클래스 파일을 참조하는 순간 클래스 로더를 통해 파일을 로딩해 온다고 이해할 수 있다.

2. **실행 엔진(Execution Engine)**
    - 클래스 로더를 통해 메모리에 할당된 클래스 파일들에 담긴 바이트 코드를 컴퓨터가 이해할 수 있는 네이티브 코드로 변환하는 역할을 한다. 
    - 변환하는 과정에서 **인터프리터**와 **JIT 컴파일러**가 사용 목적에 맞게 사용된다.

    - **인터프리터(Interpreter)**
        - 바이트 코드를 한 행씩 읽고 해석
        - 중복된 코드를 구분하지 않고 해석하기 때문에 속도가 느린 단점이 있다.
    - **JIT 컴파일러("Just In Time" Compiler)**
        - 인터프리터의 단점을 보안하기 위해 만들어진 컴파일러
        - JIT가 먼저 중복 코드에 대해서 네이티브 코드로 변환시킨다.
        - 코드 변환 시, 코드의 결과값을 캐싱하고 이를 활용해 중복코드를 변환한다.
        - 코드 변환 과정에서 바이트코드를 바로 네이티브 코드로 변환하는 것이 아니라 IR(Intermediate Representation)코드를 거쳐 최적화한 다음 네이티브 코드로 변환한다. 

3. **가비지 콜렉터(Garbage Collector)**
    - 메모리 영역 중 힙 메모리 영역에서 더 이상 사용되지 않는 메모리를 삭제하는 역할을 수행합니다.
    - GC의 존재로 인해 개발자가 직접 메모리 정리에 대한 고민을 하지 않아도 되게 되었다.

4. **런타임 데이터 영역(Runtime Data Area)**
    - JVM 동작 시 로딩 및 생성되는 데이터를 목적에 맞게 구분하여 저장하는 공간을 의미한다.
    
    - **Method Area**
        - 모든 쓰레드가 공유하는 공간
        - 기본형 변수, static 변수, 클래스, 메소드, 인터페이스 등의 바이트 코드를 저장하는 공간
    - **Heap Area**
        - 모든 쓰레드가 공유하는 공간
        - new 예약어로 생성된 객체 또는 배열의 바이트코드가 저장되는 공간
        - 참조하는 변수나 배열이 없다면 GC의 대상이 된다.
        - 메소드 영역에 로드된 클래스만 생성 가능하다.
    - **Stack Area**
        - 스택 구조로 구성된 메모리 공간으로 호출된 메소드에 대한 코드들을 저장하고 수행이 끝나면 해당 메소드의 스택 메모리는 삭제한다.
    - **PC register**
        - 쓰레드가 시작할 때 생성되며, 쓰레드가 현재 수행할 명령을 임시로 저장해두는 공간
        - JVM이 현재 수행하는 명령의 주소를 가진다.
    - **Native Method Stack**   
        - 바이트 코드 외 네이티브 코드를 저장하는 공간

> [참고사이트 1](https://steady-coding.tistory.com/305)

> [참고사이트 2](https://coding-nyan.tistory.com/85)

> [참고사이트 3](https://joomn11.tistory.com/15?category=854732#recentComments)

> [참고사이트 4](https://catch-me-java.tistory.com/11)
<br>

## :pushpin: JVM 클래스 로더
### :heavy_check_mark: 특징
1. **계층 구조**
    - JVM 내 클래스 로더의 종류도 여러가지인에 이 클래스 로더들 사이에는 계층이 존재한다.
    - `부모-자식관계`를 생성
    - 부트스트랩 클래스 로더 > 확장 클래스 로더 > 어플리케이션 클래스 로더 순으로 계층이 구성되어 있다.
2. **위임 모델**
    - 계층 구조를 바탕으로 클래스 로더끼리 클래스 확인을 위임한다.
    - 하나의 클래스 로딩과정
        1. 최하위 클래스 로더에서 최상위 클래스 로더까지 발견된 클래스 확인을 위임
        2. 최상위 클래스 로더부터 클래스명 존재 여부를 확인
        3. 클래스 파일이 존재하다면 해당 클래스 로더에서 클래스를 로딩
        4. 최하위 클래스 로더에서도 클래스가 발견되지 못하면 예외 발생
3. **가시성 제한(Visiblility)**
    - 하위 클래스 로더에선 상위 클래스 로더의 클래스를 찾을 수 있다.
    - 상위 클래스 로더에선 하위 클래스 로더의 클래스를 찾을 수 없다.
4. **유일성(Uniqueness)**
    - 상위 클래스 로더에 로딩된 클래스는 하위 클래스 로더에서 로딩하지 못한다.
    - 이를 바탕으로 클래스 로더 간의 유일성을 보장한다.
5. **언로드 불가(Unload)**
    - 로드는 가능하지만 언로더는 불가능하다.
    - 대신, 현재 클래스 로더를 삭제하고 새로운 클래스 로더를 생성하는 방법을 사용할 수 있다.

### :heavy_check_mark: 클래스 로더 위임 모델
1. **부트스트랩 클래스 로더(Bootstrap Class Loader)**
    - JDK의 기본 API를 로딩한다.
    - 기본 API는 `jre/lib/rt.jar`(JRE 기본 API) 또는 `JAVA_HOME/lib`(JDK 기본 API)에 저장되어 있다.
2. **확장 클래스 로더(Extension Class Loader)**
    - 자바 기본 API의 확장 클래스를 로딩한다.
    - 확장 클래스는 `jre/lib/ext` 폴더 또는 `java.ext.dirs` 환경변수로 지정된 폴더에 저장되어 있다.
3. **애플리케이션 클래스 로더(Application Class Loader)**
    - 지정된 `classpath`에 위치한 유저 클래스를 로딩한다.
    - 개발자가 만든 클래스들이 여기서 로딩된다고 보면 된다.
    - `classpath`란 말 그대로 클래스가 저장된 경로라는 의미이며 이를 따로 지정하지 않을 경우에는 클래스파일이 위치한 현재 디렉토리가 기본 `classpath`로 설정된다.

### :heavy_check_mark: 로딩 과정
1. **로딩**
    - 읽어온 `.class` 파일 내 바이트코드를 내용에 따라 적절한 바이너리코드로 변환한 다음, 메모리 영역 내 `메소드 영역`에 저장한다.
    - 메소드 영역에는 `FQCN(Full Quallified Class Name)`, 클래스, 인터페이스, enum, 메소드, 변수 가 저장된다.
    - 해당 클래스 타입에 해당하는 객체는 Heap 영역에 저장한다.
2. **링크**
    - 링크는 세 단계로 나뉜다.

        - 검증(Verify)
            - .class 파일 형식이 유효한지 확인한다.
        - 준비(Preparation)
            - 클래스 변수와 기본값이 필요한 메모리를 준비한다.
        - Resolve
            - `심볼릭 메모리 레퍼런스`를 메모리 영역에 있는 실제 레퍼런스와 연결한다.
3. **초기화**
    - static 변수 값들을 할당한다.

> **용어 설명**
>
> FQCN : 변수, 객체, 함수 등의 계층적 구조를 모두 포함하여 표현한 것으로, `클래스가 속한 패키지명`을 모두 포함한 이름을 의미한다.
>
> 예시 : `String` 클래스 => `java.lang.String`로 표현하는 것이 `FQCN`
>
> 심볼릭 메모리 레퍼런스 : 실제로 메모리 주소를 참조한 변수가 아닌 참조하는 대상의 이름만을 지칭한 변수

<br>

> [참고사이트 1](https://catsbi.oopy.io/df0df290-9188-45c1-b056-b8fe032d88ca)

> [참고사이트 2](https://hbase.tistory.com/174)

> [참고사이트 3](https://parkadd.tistory.com/112)

> [참고사이트 4](https://beststar-1.tistory.com/17)

> [참고사이트 5](https://dydwnsekd.tistory.com/85)

> [참고사이트 6](https://inspirit941.tistory.com/296)

> [참고사이트 7](https://happy-coding-day.tistory.com/123)

<br>

## :pushpin: java파일 실행시 파일명만 필요한 이유
JVM을 구동하기 위해 `java filename` 명령어를 실행하는데, 이는 "JVM이 filename에 해당하는 파일을 실행한다"가 아니라 "filename을 가진 바이트코드에 main메소드가 존재한다" 라는 사실을 전달하는 의미입니다.

그래서 확장자명을 포함하여 java.exe 파일을 실행시키면 확장자명까지 파일명으로 인식하여 main 메소드가 없다 또는 해당 파일명을 찾을 수 없습니다 라는 에러가 발생합니다.

> [참고 사이트](https://8iggy.tistory.com/m/233)

<br>

## :pushpin: 형변환 추가설명
short 타입 변수의 최대값에서 1을 더하면 최소값이 나오는 오버플러우 현상을 보기 위해 다음과 같은 예제를 작성했다.
```java
short shortMax = 32767;
System.out.println(shortMax+1); // 32767
```

하지만 위 예제처럼 연산을 하면 기대값이였던 -32768이 아닌 32768이 출력된다. short 타입에서 표현할 수 있는 최대값은 32767이기 때문에 32768은 short의 범위를 넘어선 숫자이다.

위와 같은 결과가 나오는 이유는 short 타입의 값에 단순히 1을 더하면 **int 타입으로 타입이 자동 변환된다**고 한다.

**구체적으로 설명하면**

1. 정수 연산시에 int가 기본 타입이다.
2. 게다가 다른 타입을 연산할 때 큰 타입으로 자동 변환된다고 한다.
3. 또한 피연산자는 4byte 단위로 계산되어 4byte보다 작은 byte, short, char은 int로 자동 변환된다.

```java
short shortMax = 32767;
System.out.println((short)(shortMax+1)); // -32768
```
위 예제처럼 자동 형변환을 제어하기 위해서는 형변환을 직접 명시해야 한다.

> [참고 사이트1](https://kephilab.tistory.com/27)

> [참고 사이트2](https://stackoverflow.com/questions/42682558/largest-java-short-32767-plus-1-not-turning-negative)

<br>

## :pushpin: 오버플로우(Intager Overflow)
- `오버플로우` : 데이터 유형별 범위를 초과한 값을 할당한 경우 발생
    - `최대값+1`을 하면 `최소값`이 되는 경우를 의미합니다.
- `최소값-1`을 하면 `최대값`이 되는 경우는 **언더플로우**라고 합니다.

short 타입으로 생성된 `256`과 `255`를 byte로 캐스팅 하는 경우, 0과 -1값이 나오는데 이런 경우도 오버플로우라고 하고, 두 경우를 자세히 살펴보면 다음과 같습니다.

`(short)256 -> (byte)256`
```
0000 0001 0000 0000 -> 2바이트인 short일때는 256이지만

          0000 0000 -> 1바이트인 byte로 형변환을 하면 0이 된다.
```

`(short)255 -> (byte)255`
```
0000 0000 1111 1111 -> short일 때는 255

          1111 1111 -> byte로 형변환을 했을 때 -1이 된다.
```

이처럼 큰 범위의 자료형에서 작은 범위의 자료형으로 형변환을 할 때 예상치 못한 값이 나오지 않도록 오버 or 언더플로우를 유의해야 한다.

<br>

## :pushpin: 2의 보수

위의 설명에서  `255(1111 1111)`가 byte 타입에서는 `-1`인 이유를 이해하지 못했다.

개인적으로 생각해낸 해답으로는 최소값인 `-128`을 이진수로 표현하면 `1000 0000`인 점을 이용해서 생각해봤다.

 `1111 1111`을 다시 표현해보면
```
1111 1111(256)
= 1000 0000(-128) + 0111 1111(127)
= -128 + 127
= -1
```

그래서 `(byte)255`가 `-1`이 나오는 것이 아닐까 싶었다.🥲

하지만 위와같은 계산법이 아니라 처음부터 컴퓨터는 **2진법에서 음수**를 **2의 보수**로 표현하기 때문이였다.

**2의 보수**란 **양수를 표현하는 2진수에서 0과 1을 뒤집은 다음, +1을 해주는 방법**을 뜻하는데

이를 예시로 자세히 살펴보면
```
(byte) 1
= 0000 0001
```

그렇다면 (byte)-1을 2진수로 표현하면?

```
1. (byte)1의 2진수 표기법에서 0과 1의 위치를 뒤집는다.
0000 0001 -> 1111 1110

2. +1을 해준다.
1111 1110 -> 1111 1111
```

이처럼 2의 보수를 통해 8비트에서 `-1`을 표현하면 `1111 1111`이 된다.

좀 더 자세한 설명은 아레 참고 사이트에 잘 설명되어 있다.
> [참고사이트](https://wikidocs.net/81918)

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

## :pushpin: Collection Framework
`Collection FrameWork`는 다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미합니다.

`Collection Framework`의 구성요소는 자료구조에 따라 인터페이스로 구분하고, 이를 구체적인 클래스들로 구현되어 있습니다.

핵심 인터페이스는 다음과 같습니다.
- `List` : 순서가 있는 데이터 집합, 중복 허용
- `Set` : 순서가 없는 데이터 집합, 중복 혀용하지 않음
- `Map` : 키와 값으로 구분된 데이터 집합

이 중에서 `List`와 `Set`인터페이스는 같은 `Collection` 인터페이스를 상속받지만, `Map` 인터페이스는 자료 구조상 차이점으로 인해 별도로 정의되어 있습니다. 

### ✔️ Collection Framework 구조
![](https://blog.kakaocdn.net/dn/4wkUX/btq44bqazqr/80s6KaCrGqfETw4Pk5CGqK/img.png)
<br> 출처 : https://crazykim2.tistory.com/557

위 인터페이스들을 구현한 클래스는 다양하며 클래스마다 차이점이 존재합니다.

배열이 아닌 `Collection Framework`를 활용하는 이유는 배열의 크기를 정해두지 않고 활용하기 위해서(= 동적 메모리 할당)입니다.

> [참고사이트 1](http://www.tcpschool.com/java/java_collectionFramework_concept)

> [참고사이트 2](https://www.crocus.co.kr/1553)

> [참고사이트 3](https://crazykim2.tistory.com/557)

<br>

## :pushpin: toSting()
- `toSting()` 메소드는 객체가 가지고 있는 정보를 문자열로 리턴하는 메소드
- Java의 모든 클래스 중 가장 최상위 클래스인 'Object' 클래스의 메소드로서 사용자가 생성하는 클래스가 기본적으로 상속받게 되는 메소드
- 객체가 가지고 있는 `toSting()` 메소드의 기본값은 '타입이름@고유번호'의 형태
- 이를 재정의(오버라이딩)을 통해 바꿀 수 있다.

> [참고사이트](https://selfdevelope.tistory.com/560)

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

## :pushpin: static 변수 추가 설명
**예제 코드**
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

이는 매개변수값을 할당하는 변수 `name`이 클래스변수, 즉 **static**변수이기 때문에 위와 같은 결과값을 가지게 된건데, 자세히 설명하면 클래스 변수는 객체에 상관없이 하나의 메모리 주소만을 가지게 된다.

그렇기에 위 예제는 `reference1`만의 **인스턴스 변수**인 `name`에 매개변수값을 할당한 것이 아니라, 클래스 전체에 하나만 존재하는 **클래스변수**인 `name`에 매개변수 값을 할당한 것이다.(객체와는 무관하게 name이라는 변수는 해당 클래스에서 하나라는 뜻!)

그러므로 `name`은 `Kim`으로 한번, `Lee`로 한번씩 값을 할당받은 것이다.

> [참고 사이트](https://wikidocs.net/228)

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

## :pushpin: super() 상세 내용
`super()`가 정확히 어떤 의미를 가지는지 간단하게 설명하자면 **부모 클래스**를 가르킨다고 말할 수 있다. 반대의 개념으로는 `this`가 된다.

**예제 코드**
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
**실행결과**
```
Kim의 나이는56입니다.
Lee의 나이는27입니다.
```

위 예시에서 보면 자식 클래스에서 `super.변수명`의 형식으로 코드를 작성하면 **부모클래스의 인스턴스변수를 지정**할 수 있다.

반대로 `this.변수명`은 **해당 클래스의 인스턴스 변수를 지정**하게 된다.

### 자동으로 super()이란 코드가 추가되어 컴파일?

말 그대로 자식클래스를 컴파일할 때 코드 작성자가 굳이 적지 않아도 `super()`라는 코드가 추가된다는 말이였다. 이 말을 코드로 표현해보면 아래 예시와 같다.

**예제 코드**
```java
// 위 코드 생략

class Child extends Parent{
    public Child(){
        super();  // 가장 첫 줄에 자동으로 추가된다.
        String name = "Lee";
    }

    // 아래 코드 생략
}
```

그렇다면 부모 클래스의 생성자가 매개변수를 가지고 있다면 당연히 문제가 생기는 구조였다.

자식 클래스에서 자동으로 생성되면서 부모클래스의 생성자를 가르키는 `super()` 코드는 매개변수값이 지정되어있지 않기 때문에 부모 클래스에서 매개변수를 가진 생성자를 선언했다면 자식 클래스에서도 매개변수값을 지정해줘야 하는 것이 맞다.

**예제 코드**
```java
class Parent{
    String name;

    // 매개변수를 가진 생성자 선언
    public Parent(String name){
        this.name = name; // 매개변수 -> 인스턴스 변수로 지정
    }
}

class Child extends Parent{
    String name;

    public Child(String name){
        super("Kim"); // 부모클래스의 매개변수값 지정
        this.name = name;
    }
}
```

위 예제처럼 부모 클래스에서 매개변수를 가진 생성자를 선언했다면 자식클래스의 생성자에서 `super()`를 사용해 매개변수값을 동일한 자료형으로 지정해줘야 한다.

> [참고사이트](https://crazykim2.tistory.com/551)

<br>

## :pushpin: 부모객체 메소드 호출 시 주의사항
상속관계에서 부모 클래스에만 선언된 메소드를 자식 클래스에서도 호출해 올 수 있다고 했다.

이는 위에서 설명한대로 자식 클래스를 생성할 때, 자식 클래스 생성자 코드의 가장 첫 줄에 부모 생성자를 의미하는 **super()가 자동으로 추가**되면서 부모 생성자가 자식 생성자와 함께 호출되기 때문에 가능하다.

그래서 자식 객체에서 호출한 메소드가 자식 클래스에 선언되어 있지 않다면, 자식 클래스에 호출되어있는 부모 클래스에서 호출해온다.

### 예제
```java
public class Sample{
    public static void main(String[] args){
        Child child = new Child("BABY", 20); // 자식 객체 생성
        System.out.println(child.getParentName()); // PAPA(부모객체 name 출력)
        System.out.println(child.getChildName()); // BABY(자식객체 name 출력)
    }
}

class Parent{
    String name;
    int age;

    public Parent(String name, int age){
        this.name = name;
        this.age = age;
    }

    public String getParentName(){
        return this.name;
    }
}

class Child extends Parent{
    String name;
    int age;

    public Child(String name, int age){
        super("PAPA", 50); // 부모 객체 생성 -> 부모 클래스에만 선언된 메소드는 이 객체에서 호출해온다.
        this.name = name;
        this.age = age;
    }

    public String getChildName(){
        return this.name;
    }
}
```

위 예제에서 보면 호출된 메소드가 자식 클래스에 선언되어 있지 않다면 부모 클래스에서 호출해온다. 이때 부모 클래스의 메소드를 호출하는 것이기 때문에 메소드에서 가르키는 **this의 대상은 부모 클래스**가 된다.

이처럼 부모 클래스에만 선언된 메소드를 통해 자식 클래스의 변수를 가져오려 하는 것이 불가능하기 때문에 **오버라이딩**을 활용해야 한다.

<br>

## :pushpin: this와 super의 활용법 추가 설명

**부모 클래스**
```java
class Animal {
    String name;
    int legCount;
    boolean hasWing;
    // 매개변수를 지정한 부모 생성자 선언
    public Animal(String name, int legCount, boolean hasWing){
        this.name = name;
        this.legCount = legCount;
        this.hasWing = hasWing;
    }
    public void printInfo(){
        System.out.println("Name : " + name);
        System.out.println("LegCount : " + legCount);
        System.out.println("HasWing : " + hasWing);
    }
}
```
부모 클래스에서는 기본생성자가 아닌 인스턴스 변수에 매개변수로 받아온 값을 할당하는 생성자를 선언합니다.

**자식 클래스**
```java
class Dog extends Animal {
    // 새로운 변수 선언
    String breed;

    // 매개변수를 지정한 자식 생성자 선언
    public Dog(String name, int legCount, boolean hasWing, String breed){
        // 부모 생성자 호출, 상속받은 변수는 super()을 통해 부모 생성자를 호출하여 할당
        super(name, legCount, hasWing);

        // 상속받지 않은 변수는 this로 지정
        this.breed = breed;
    }
    // 오버라이딩
    public void printInfo(){
        System.out.println("Name : " + name);
        System.out.println("LegCount : " + legCount);
        System.out.println("HasWing : " + hasWing);
        // 추가코드
        System.out.println("breed : " + breed);
    }
}
```
자식클래스 또한 매개변수값을 받는 생성자를 선언하고, 그 안에 super()를 통해 상속받은 인스턴스 변수에 할당할 매개변수는 부모 클래스 생성자로 넘겨줍니다. 그리고 자식 클래스에서 새로 선언한 인스턴스 변수값은 this 예약어로 지정합니다.

**메소드 실행**
```java
public class Sample{
    public static void main(String[] args){
        // 부모타입 객체 생성
        Animal animal = new Animal("heri", 4, false);
        System.out.println("<Animal class>");
        // 매개변수값 출력1
        animal.printInfo();

        System.out.println();

        // 자식타입 객체 생성
        Dog dog = new Dog("coco", 4, false, "cocker");
        System.out.println("<Dog class>");
        // 매개변수값 출력2
        dog.printInfo();
    }
}
```
**출력 결과**
```
<Animal class>
Name : heri
LegCount : 4
HasWing : false

<Dog class>
Name : coco
LegCount : 4
HasWing : false
breed : cocker
```

<br>

## :pushpin: `instanceof` 예약어 추가 설명
- 자식객체 `instanceof` 부모클래스 : 이 객체가 부모클래스를 대신할 수 있는가? -> `return true`
- 부모객체 `instanceof` 자식클래스 : 이 객체가 자식클래스를 대신할 수 있는가? -> `return false`

<br>

## :pushpin: 상속 클래스 형변환 추가 설명
### 참조자료형 형변환
- 자식 객체를 부모 객체로 형변환은 가능
- 부모 객체를 자식 객체로 형변환하는 것은 불가능

### 예제 코드
아래 예제에 example() 메소드에는 세가지 경우로 생성한 객체가 존재한다.

```java
class Sample{
	public static void main(String[] args){
		Sample sample = new Sample();
        sample.example();
    }
    // 예제 실행 메소드
    public void example(){
        // 1. 부모타입 객체 - 부모 생성자
        Parent parent1 = new Parent();
        parent1.printByParent(); // 결과 : This str is from Parent

        // 2. 부모타입 객체 - 자식 생성자
        Parent parent2 = new Child();
        parent2.printByParent(); // 결과 : This str is from Parent with Overriding method

        // 3. 자식타입 객체 - 부모생성자(처럼 보이는 자식 생성자)
        Child child1 = (Child)parent2;
        child1.printByChild(); // 결과 : This str is from Child with Only child method
	}
}
// 부모 클래스
class Parent{
    // 변수
    String str = "Parent";

    // 메소드
    public void printByParent(){
        System.out.println("This str is from " + str);
    }
}
// 자식 클래스
class Child extends Parent{
    // 자식 클래스에 새로 선언한 메소드
    String str2 = "Child";

    // 오버라이딩 메소드
    public void printByParent(){
        System.out.println("This str is from " + str + " with Overrinding method");
    }
    // 자식 클래스에 새로 선언한 메소드
    public void printByChild(){
        System.out.println("This str is from " + str2 + " with Only child method");
    }
}
```

객체 타입과 생성자에 따라 3가지 경우로 나눴다.

### 1. 부모 클래스 생성자로 부모타입의 객체를 생성한 경우
이런 경우는 자식 클래스에 어떠한 영향을 받지 않는다.

### 2. 자식 클래스 생성자로 부모타입 객체를 생선한 경우
이런 경우에 자식 클래스에서 부모 클래스로부터 상속받은 변수나 메소드만 호출할 수 있다.

즉, 자식 클래스에만 선언된 `str2` 변수나 `printByChild()` 메소드는 호출이 불가능하다.

```java
Parent parent2 = new Child();
parent2.printByChild(); // 에러 발생(결국 부모타입이라)
```

또한 오버라이딩되어 자식 클래스에 재선언된 메소드나 변수는 오버라이딩된 상태로 호출된다.
> 이런 현상을 책에서는 폴리몰피즘(다형성)이라고 한다.

### 3. 자식타입 객체 - 부모생성자(처럼 보이는 자식 생성자)
자식 클래스 타입의 객체를 생성하는데 **그 생성자를 자식생성자로 만든 부모타입의 객체로 만든 경우**이다.

말이 많이 어렵지만 사실상 자식클래스 객체이지만 부모클래스 타입으로 보이는 객체로 이해하면 되겠다.

이 경우에 결국 실생성자의 출신이 어디냐를 본다면 **자식클래스**이지만 겉모습은 부모클래스를 타입으로 가지고 있기때문에 형변환을 통해 객체를 생성해줘야 한다.

```java
Child child2 = parent2; // 에러발생(겉보기는 부모타입)
```

하지만 형변환을 통해 객체를 생성했다면 자식클래스의 변수와 메소드를 호출한다.

### 정리하자면
- 결국 생성자에 따라 호출되는 변수나 메소드가 결정된다.
- 그렇기에 오버라이딩된 변수나 메소드는 그 상태로 호출된다.
- 자식 생성자로 만든 부모 객체는 겉으로는 부모의 형상을 띄기 때문에 이 객체를 이용해 자식 객체를 만들려면 형변환이 필요하다.
- **겉** : 부모클래스 타입의 객체 / **안** : 오버라이딩되었거나 부모객체로부터 상속된 변수와 메소드만 호출 가능

<br>

## :pushpin: BigDecimal 클래스를 사용하는 이유
JAVA에서 기본자료형으로 활용되는 float나 double을 사용하지 않고 BigDecimal 클래스를 사용하는 이유는 BigDecimal 클래스를 활용하면 실수를 계산하는데 더 정확한 계산이 가능하다 한다.

이를 자세히 알아보기 위해 먼저 기본 자료형으로 실수 계산시 발생할 수 있는 문제점을 보자.

```java
double num1 = 3.1254;
double num2 = 2.2376;
System.out.println(num1 + num2); // 5.3629999999999995
```
위 예제에서 두 double 타입의 값을 더했을 때 정확히 기대값이 아닌 기대값의 매우 가까운 근사치가 나오는 것을 볼 수 있다.(2진법 사용)

매우 작은 차이이기에 가볍게 넘길 수 있다고 생각할 수 있지만 돈계산과 같은 오차가 허용되지 않는 상황일 땐 매우 치명적인 오류를 범할 수 있다.

다음은 BigDecimal 타입으로 같은 값을 계산했을 경우다.(10진법 사용)
```java
BigDecimal num1 = BigDecimal.valueOf(3.1254);
BigDecimal num2 = BigDecimal.valueOf(2.2376);
System.out.println(num1.add(num2)); // 5.3630
```

`valueOf()` 메소드는 인자로 받은 값을 원하는 클래스로 변경하는 역할을 수행한다.

즉, double타입의 변수를 BigDecimal 타입으로 형변환을 한 이후 두 값을 더했을 때 우리가 기대했던 값이 나온 것을 알 수 있다.

이처럼 자바에서 기본자료형으로 실수를 연산하기보단 BigDecimal 타입을 활용하는 것이 필수적이다.

<br>

## :pushpin: equals() 오버라이딩 코드 추가 설명
```java
@Override
public boolean equals(Object obj){
    if(this == obj) return true;
    if(obj == null) return false;
    if(this.getClass() != obj.getClass()) return false;
    Student other = (Student) obj; // ??? 부모객체 생성자로 자식객체를 생성한다?? 에러가 왜 안나지???

    if(name == null){
        if(other.name != null) return false;
    } else if(!name.equals(other.name)) return false;

    if(address == null){
        if(other.address != null) return false;
    } else if(!address.equals(other.address)) return false;

    if(phone == null){
        if(other.phone != null) return false;
    } else if(!phone.equals(other.phone)) return false;

    if(email == null){
        if(other.email != null) return false;
    } else if(!email.equals(other.email)) return false;

    return true;
}
```
주석이 달린 코드를 보면 부모객체인 Object의 생성자를 자식객체로 형변환하여 자식객체를 생성한다. 이러면 에러가 발생할텐데(참조자료형 형변환시 주의점) 에러발생이 안한다.

차근차근 코드를 살펴보니 그 이유를 알았다.

먼저 equals() 에서 매개변수로 받는 객체는 어떤 클래스의 생성자로 만들어진 객체인지 모르기 때문에 가장 최상위 객체인 Object 타입으로 받아야만 한다. 이렇게 되면 어떠한 객체 타입이 매개변수로 오더라도 Object보단 하위 클래스이기 때문에 문제가 생길 일이 없다.

하지만 equals() 메소드가 사용되는 경우는 사실상 받아온 객체가 Object 객체의 하위객체, 즉 상속된 또 다른 클래스이거나 같은 클래스의 객체이다. 그리고 형변환 전에 getClass()를 활용해서 두 객체 타입이 다르다면 false를 리턴하고 메소드를 종료하게 설계되어 있다.

그렇기 때문에 형변환 코드가 실행되는 경우는 **this와 obj 객체가 같은 클래스일 경우**에만 실행된다. 기본 예외 발생 상황에 대한 대비가 되어 있게 기본 오버라이딩 코드는 설계되어 있었다.

<br>

## :pushpin: hashcode()메소드 추가 설명
hashCode() 메소드는 Java에서 Object 객체에 선언된 메소드 중 하나로 객체의 **주소값을 int 타입의 16진수로 리턴**하는 메소드이다.

hashCode() 메소드는 equals()와 함께 Overriding 하여 사용하는 것이 일반적인데 이는 비교하는 두 객체의 값을 equals()로 비교하여 같다는 것을 확인했어도 그 객체들이 할당된 주소값은 다른 것을 방지하기 위함이다.

즉 두 객체가 가진 값이 같다면, 두 객체가 저장된 위치값도 같아야 한다는 것이다.

위와 같은 설정을 위해 대부분의 IDE에서 제공해주는 hashcode()의 오버라이딩 기본코드가 있다.

### hashcode() 오버라이딩 코드
```java
@Override
public int hashCode() {
    final int prime = 31;
    int result = 1;
    result = prime * result + ((variableValue1 == null) ? 0 : variableValue1.hashCode());
    result = prime * result + ((variableValue2 == null) ? 0 : variableValue2.hashCode());
    result = prime * result + ((variableValue3 == null) ? 0 : variableValue3.hashCode());
    return result;
}
```
### 코드 구동 순서 설명
1. hashcode로 전환할 변수의 값을 `variableValue1 ~ 3`으로 정한다.
2. variableValue1의 값이 null 이라면 result에 0을 더한다.
3. 그렇지 않다면 variableValue1의 hashCode()값을 result에 더한다.
4. 모든 변수가 2~3번 과정을 반복한다.
5. 최종 result 값을 리턴한다.

위 코드가 호출되는 상황은 **이미 eqauls()를 통해 비교할 두 객체의 값이 동일하다는 것을 확인한 이후**이다. 그래서 두 객체에 선언된 변수나 메소드의 hashCode값들의 총합을 result로써 리턴하여 두 합계를 같게 만들어 주는 것이다. 그래야 두 객체의 hashcode, 즉 두 객체의 위치값이 같다고 말할 수 있다.

### 31을 사용하는 이유
Prime 변수에 31을 할당하고 result에 이 값을 곱하여 합계를 구한다. 그냥 null값이 아니면 해당 hashcode값만 더해서 result를 구해도 무방할 것처럼 보이는데 굳이 31이라는 값을 곱하는 이유는 무엇일까?

이는 result값을 구할 때 생겨날 에러를 방지하기 위해 상수로 곱해주는 것인데 자바의 hashCode()를 오버라이딩할 때는 주로 31을 사용할 뿐이다. 31이 에러를 방지할 수 있는 이유는 31이 **홀수**이자 **소수**이기 때문이다.

만약 31과 같은 홀수가 아닌 짝수를 곱한다면 비트를 왼쪽으로 Shift하는 것과 같기 때문에 에러를 발생할 수 있다.

#### 비트 이동 예시
|num1|X|num2|==|result|shift|
|:--:|:--:|:--:|:--:|:--:|:--:|
|0001(1)|X|0010(2)|==|0010(2)|0001(1) -> 0010(2)|
|0010(2)|X|0010(2)|==|0100(4)|0010(2) -> 0100(4)|
|0011(3)|X|0010(2)|==|0110(6)|0011(3) -> 0110(6)|

가장 오른쪽 2진수를 보면 2를 곱했을경우 1의 위치가 왼쪽으로 한칸씩 이동한 것을 볼 수 있다. 이처럼 짝수를 곱할 경우 비트가 이동함과 동시에 오버플로우가 발생하면 값이 사라질 수 있기 때문에 짝수를 선택할 수 없다.

그렇다면 홀수를 사용하는 것은 이해했는데 왜 굳이 소수인 것일까??

소수를 사용하는 이점은 따로 알려진 것이 없지만 통상적으로 그렇게 사용된다고 한다. 약간 미신과 같은 이유라고 생각하면 된다.

소수를 사용하지 않아도 hashCode값 생성에는 큰 문제가 생기지 않지만, 짝수를 피해야하는 것은 명백한 이유가 존재한다는 것을 기억하면 좋을 듯 하다.

> [참고사이트](https://johngrib.github.io/wiki/Object-hashCode/#%EC%9D%B4%EC%83%81%EC%A0%81%EC%9D%B8-%ED%95%B4%EC%8B%9C-%ED%95%A8%EC%88%98%EC%97%90-%EA%B0%80%EA%B9%8C%EC%9A%B4-%ED%95%A8%EC%88%98-%EB%A7%8C%EB%93%A4%EA%B8%B0)

<br>

## :pushpin:enum 생성자
enum 클래스는 객체를 생성할 때는 다음과 같이 상수를 지정해줘야만 생성이 된다.

`enum 클래스명.상수명`

### 예제코드
```java
public class Sample{
    public enum EnumName{
        PRIME_ONE,
        PRIME_TWO;
    }
    public static void main(String[] args){
        EnumName primeNumber = EnumName.PRIME_ONE; // PRIME_ONE
        EnumName primeNumber2 = EnumName; // 에러 발생
    }
}
```

또한 각 상수 선언시, 각 상수에 대응하는 매개변수를 지정할 수 있고 해당 매개변수를 활용한 생성자를 private나 package-protect 로 선언할 수 있다.

`상수명(매개변수값)`

### 예제코드2
```java
public class Sample{
    public enum EnumName{
        PRIME_ONE(1), // 상수에 대응하는 매개변수값을 소괄호에 지정
        PRIME_TWO(2);

        private final int number;

        // 생성자 선언
        EnumName(int number){
            this.number = number; // 매개변수값을 인스턴스 변수에 지정
        }
    }
    public static void main(String[] args){
        EnumName primeNumber = EnumName.PRIME_ONE;
        System.out.println(primeNumber.number); // 1
    }
}
```
출력된 값은 상수인 PRIME_ONE의 인스턴스 변수인 number의 값이라고 할 수 있다.

> [참고사이트](https://seeminglyjs.tistory.com/257)

<br>

## :pushpin: gitignore 파일 활용법
### gitignore 파일이란?
원격 저장소에서 사용되지 않는 파일들을 지정하여 커밋하지 못하게 설정하는 파일로 설정된 확장자 파일은 commit track에 올라오지 않는다.

자바의 경우, `.metadata` 파일들이 commit track에 올라오는 것을 막기 위해 생성하는 파일이다.

### 설정 순서
1. gitignore 파일을 생성한다.
    - 파일 생성시 최상위 디렉토리에 위치해야 한다.
    - [https://www.gitignore.io/](https://www.toptal.com/developers/gitignore)을 이용하면 사용하는 OS, 프로그래밍 언어, IDE에 맞는 gitingore파일을 생성할 수 있다.
2. 생성한 gitignore 파일을 commit 및 원격저장소에 push한다.
3. 이후 커밋할 때 설정한 파일들은 track에 올라오지 않는다.

**windows, java, eclipse 전용 gitignore 파일**
```

# Created by https://www.toptal.com/developers/gitignore/api/eclipse,java,windows
# Edit at https://www.toptal.com/developers/gitignore?templates=eclipse,java,windows

### Eclipse ###
.metadata
bin/
tmp/
*.tmp
*.bak
*.swp
*~.nib
local.properties
.settings/
.loadpath
.recommenders

# External tool builders
.externalToolBuilders/

# Locally stored "Eclipse launch configurations"
*.launch

# PyDev specific (Python IDE for Eclipse)
*.pydevproject

# CDT-specific (C/C++ Development Tooling)
.cproject

# CDT- autotools
.autotools

# Java annotation processor (APT)
.factorypath

# PDT-specific (PHP Development Tools)
.buildpath

# sbteclipse plugin
.target

# Tern plugin
.tern-project

# TeXlipse plugin
.texlipse

# STS (Spring Tool Suite)
.springBeans

# Code Recommenders
.recommenders/

# Annotation Processing
.apt_generated/
.apt_generated_test/

# Scala IDE specific (Scala & Java development for Eclipse)
.cache-main
.scala_dependencies
.worksheet

# Uncomment this line if you wish to ignore the project description file.
# Typically, this file would be tracked if it contains build/dependency configurations:
#.project

### Eclipse Patch ###
# Spring Boot Tooling
.sts4-cache/

### Java ###
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

# virtual machine crash logs, see http://www.java.com/en/download/help/error_hotspot.xml
hs_err_pid*
replay_pid*

### Windows ###
# Windows thumbnail cache files
Thumbs.db
Thumbs.db:encryptable
ehthumbs.db
ehthumbs_vista.db

# Dump file
*.stackdump

# Folder config file
[Dd]esktop.ini

# Recycle Bin used on file shares
$RECYCLE.BIN/

# Windows Installer files
*.cab
*.msi
*.msix
*.msm
*.msp

# Windows shortcuts
*.lnk

# End of https://www.toptal.com/developers/gitignore/api/eclipse,java,windows
```
> [참고사이트](https://velog.io/@psk84/.gitignore-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0#gitignore%EC%9D%B4%EB%9E%80)

<br>

## :pushpin: constant pool
JAVA에서 String 객체를 생성하는 방법은 두가지가 있다.

1. `new` 예약어 사용하는 방법
2. `""`(큰따옴표) 사용하는 방법

두 방법의 차이점은 객체 생성시 **참조하는 메모리 주소**에 있다.

먼저 1번 방법으로 객체를 생성하면 같은 문자열이라도 서로 다른 메모리 주소를 참조하게 된다. 즉 같은 문자열을 가지고 있더라도 서로 다른 곳에 개별적으로 저장된다는 뜻이다.

반대로 2번 방법으로 객체를 생성하게 되면 같은 내용의 문자열을 생성할 때, 기존에 생성되어 있던 객체의 메모리 주소를 그대로 참조한다. 즉 새로운 메모리에 객체를 생성하는 것이 아니라 같은 내용의 문자열이 저장된 메모리 주소를 그대로 사용한다는 뜻이다.

이처럼 큰따옴표로 생성한 String 객체를 생성한 경우, 그 객체가 저장되는 메모리 구역을 **Constant Pool** 이라고 하고 Constant Pool은 해당 공간에 이미 저장된 메모리가 또 다시 생성될 경우에 다른 메모리 주소에 객체를 또 생성하는 것이 아니라 이미 생성된 메모리의 주소만 참조하면서 메모리 공간의 효율성을 높이는 역할을 한다.

> [참고사이트](https://starkying.tistory.com/entry/what-is-java-string-pool)


<br>

## :pushpin: 객체를 비교할 때 `==`는 사용하지 말아야 하는 이유

`==`는 두 객체의 메모리 주소를 비교하여 메모리 주소가 다르다면 false를 결과로 내놓는다. 근데 만약 두 객체에 할당된 값은 같다면 에러를 발생시킬 수 있다. 두 값이 완전히 같다고 표현할 수 없기 때문이다.

하지만 `eqauls()` 메소드는 객체에 할당된 값을 비교하기 때문에 `==` 보다 높은 안정성을 가질 수 있는 것이다.

위와 같은 맥락으로 객체 생성시 new 예약어를 활용해 객체를 생성한다면 그 값이 같더라도 Constant Pool을 활용하지 못하고 서로 다른 메모리 주소를 가지기 때문에 똑같은 에러를 발생시킬 수 있다.

이러한 위험요소를 제거하기 위해 대부분
- String 객체 생성시에는 ""를 사용할 것
- 객체를 비교할 땐 equals()를 사용할 것

을 권장하는 것이다.

## :pushpin: String, CharSequence 추가 설명
### String 객체 리터럴 생성 방법(`""` 사용)으로 CharSequence 객체도 선언 가능

CharSequence는 인터페이스이며 String은 클래스이다. 그리고 String은 CharSequence를 구현한 클래스이다.

그렇기 때문에 **CharSequence 타입의 객체를 선언할 때, 생성자는 String 클래스의 생성자를 사용할 수 있는 것**이다.

상속은 아니지만 비유를 하자면 부모가 CharSequence, 자식이 String인 셈이다. 그래서 범주가 더 넓은 String으로 CharSequence 객체를 선언할 수 있다.

또한 String 외에도 StringBuffer, StringBuilder 클래스도 CharSequence를 구현한 클래스들이기 때문에 위 세가지 클래스 생성자로 CharSequence 객체를 생성할 수 있다.

그래서 한 메소드에서 매개변수로 위 세 클래스의 객체를 활용하는 경우, CharSequence 객체로 매개변수 객체를 지정해 주는 것이 좋다. 객체는 CharSequence여도 호출되는 **변수나 메소드는 생성자의 클래스로 결정**되기 때문에 오히려 메소드에 유연성을 제공할 수 있다.

**예제**
```java
public class Sample{
    public static void main(String[] args){
        // String 객체 생성
        String str = "I'm String";
        // String 객체를 매개변수로 전달
        Sample.callStr(str);
    }
    // CharSequence 객체를 매개변수로 지정한 메소드
    public static void callStr(CharSequence str){
        // 매개변수에 저장된 값과 클래스를 출력
        System.out.println(str + " | " + str.getClass()); // I'm String | java.lang.String
    }
}
```

예제 결과를 보면 `callStr()`메소드는 CharSequence타입 객체를 매개변수로 받지만 String 객체가 넘어가도 에러없이 코드가 작동한다. 그리고 매개변수의 클래스도 String으로 생성자에 따라 결정되는 것을 볼 수 있다.

<br>

## :pushpin:String, StringBuffer, StringBuilder 추가 설명
### String
String은 불변한 성격(immutable)을 가지고 있습니다. 즉 한번 생성한 문자열은 수정이 불가능합니다.

이러한 특성때문에 이미 생성된 String 객체에 문자열을 수정할 경우, 같은 메모리에 저장된 값만 수정되는 것이 아니라 통째로 새로운 메모리 주소에 저장됩니다.

```java
String str = "안녕하세요."; // 문자열 생성
str = str + " 반갑습니다."; // 문자열 수정(?)
System.out.println(str); // output : 안녕하세요. 반갑습니다.
```

위 예제에서 출력 결과는 두 문자열이 합쳐진 결과로 나오지만, 문자열에 연산을 통해 새로운 값을 추가하면 새로운 객체로 다시 생성된다고 생각하면 됩니다. 그리고 이전의 문자열이 저장되어 있는 메모리는 GC(가비지 콜렉터)의 대상이 됩니다.

그래서 String 클래스는 문자열에 대한 수정 작업이 일어나지 않는 경우에 사용하는 것이 효율적입니다.

### StringBuffer, StringBuilder
StringBuffer와 StringBuilder 클래스는 String과 다르게 mutable한 성격을 가진 클래스입니다. 즉, **문자열의 수정이 가능한 클래스**입니다.

그래서 두 클래스는 문자열에 대한 수정이 빈번한 경우에 사용하는 것이 좋고 연산이 아닌 `append()`, `delete()`와 같은 메소드를 사용하여 수정할 수 있습니다.

```java
StringBuffer str = new StringBuffer("안녕하세요."); // 문자열 생성
str.append(" 반갑습니다."); // 문자열 수정
System.out.println(str); // output : 안녕하세요. 반갑습니다.
```

### StringBuffer와 StringBuilder 차이점
StringBuffer와 StringBuilder의 차이점은 **쓰레드 동기화 지원** 유무이며 StringBuffer가 쓰레드 동기화를 지원하는 클래스입니다.

> **용어 설명**
> - **쓰레드** : 프로세스의 실행 단위
> - **쓰레드 동기화** : 하나의 프로세스에 여러 쓰레드가 접근해야 하는 경우, 접근 순서에 대한 질서, 규칙을 정하는 것

> 즉 **쓰레드 동기화가 된다**는 것은 멀티 쓰레드 환경에서 수행이 가능하다는 뜻

그래서 동기화를 지원해주는 클래스인 StringBuffer가 하나의 변수에 여러 쓰레드가 동시에 접근할 경우가 있는 경우에 높은 안정성을 가집니다.

그렇지 않은 경우에는 StringBuilder가 쓰레드 동기화에 대한 고려하지 않아도 되기에 StringBuffer보다 성능이 뛰어납니다.

그리고 String 클래스 또한 문자열에 대한 수정이 불가능하기 때문에 멀티 쓰레드 환경에서 안정성을 가집니다.

> [참고 사이트 1](https://ifuwanna.tistory.com/221)

> [참고 사이트 2](https://popcorntree.tistory.com/65)

<br>

## :pushpin: String 주요 메소드 정리
> **자세한 설명 및 매개변수 종류는 [API](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html#matches(java.lang.String)) 참고**

### 비교 & 검색
|Return Type|Method Name|Description|
|--|--|--|
|int|length()|문자열 길이를 출력|
|boolean|isEmpty()|문자열이 비어있는지 확인. 비어있다면 true|
|boolean|equals()|대상이 되는 문자열과 매개변수로 받아온 문자열이 동일한지 확인|
|boolean|equalsIgnoreCase()|equals()와 같은 기능이지만 대소문자를 구분하지 않고 비교|
|int|compareTo()|두 문자열이 같은지 확인하고 상대적인 위치값을 리턴|
|int|compareToIgnoreCase()|compareTo()와 같은 기능이지만 대소문자를 구분하지 않고 비교|
|boolean|contentEquals()|매개변수로 받는 CharSequence와 StringBuffer 객체가 String 객체와 같은지 비교|
|boolean|startsWith()|String 객체가 매개변수로 시작하는지 여부를 확인|
|boolean|endsWith()|String 객체가 매개변수로 끝나는지 여부를 확인|
|boolean|contains()|String 객체에 매개변수가 포함되어 있는지 여부를 확인|
|boolean|matches()|contains()와 같은 기능을 하지만 매개변수가 **정규표현식**인 점이 contains()와 차이점|
|boolean|regionMatches()|문자열 중 특정 영역이 매개변수로 넘어온 값과 동일한지 확인|

### 위치 탐색
|Return Type|Method Name|Description|
|--|--|--|
|int|indexOf()|매개변수로 받는 값(String, char 등)과 동일한 문자열 중 가장 앞에 있는 위치값을 리턴|
|int|lastIndexOf()|매개변수로 받는 값(String, char 등)과 동일한 문자열 중 가장 마지막에 있는 위치값을 리턴|

> 두 메소드는 탐색 시작 위치를 매개변수를 통해 설정할 수 있고, 시작 위치값은 문자열의 가장 왼쪽부터 계산한다.

### 추출
|Return Type|Method Name|Description|
|--|--|--|
|char|charAt()|특정 위치의 문자열에 해당하는 char을 리턴|
|void|getChars()|문자열에 해당하는 char값들을 매개변수로 지정한 char배열에 저장|
|int|codePointAt()|특정 위치의 문자열에 해당하는 유니코드값을 리턴|
|int|codePointBefore()|특정 위치 앞에 있는 문자열의 유니코드값을 리턴|
|int|codePointCount()|지정 범위 안의 유니코드 개수를 리턴|
|int|offsetByCodePoints()|지정된 index부터 offset(상대주소)이 설정된 인덱스를 리턴|
|static String|copyValueOf()|매개변수로 받아온 char배열을 문자열로 변환|
|char[]|toCharArray()|String 객체를 char 배열로 변환|
|String|subString()|매개변수값으로 지정된 위치의 문자열을 잘라내서 Sting 객체로 리턴|
|CharSequence|subSequence()|매개변수값으로 지정된 위치의 문자열을 잘라내서 CharSequence 객체로 리턴|
|String[]|split()|매개변수값(정규표현신)을 기준으로 문자열을 나눠, String 배열로 리턴|

### 변경
|Return Type|Method Name|Description|
|--|--|--|
|String|trim()|문자열 맨 앞과 맨 뒤에 있는 공백을 제거|
|String|replace()|특정 문자열을 다른 문자열로 교체|
|String|replaceAll()|정규표현식에 해당되는 모든 문자열 원하는 문자열로 교체|
|String|replaceFirst()|정규표현식에 해당되는 문자열 중 가장 첫 번째 문자열만 원하는 문자열로 교체|
|static String|format()|특정 조건에 해당되는 문자열(`%s`, `%d`, `%f`, `%%`)을 매개변수값으로 변경|
|static String|valueOf()|매개변수값을 String 객체로 변환|

<br>

## :pushpin: Reflection API(리플렉션)
Reflection은 자바에서 기본으로 제공해주는 API로 클래스, 메소드 인터페이스 등의 정보를 클래스를 생성하지 않고 확인할 수 있습니다.

Reflection에서 가져올 수 있는 클래스 종류는 대표적으로 아래 4개의 클래스로 분류할 수 있다.
- Class : 클래스 정보를 담은 클래스
- Constructor : 생성자 정보를 담은 클래스
- Method : 메소드 정보를 담은 클래스
- Field : 상수 정보를 담은 클래스

Class 클래스는 `java.lang.Class`로 선언되어 있기 때문에 따로 import할 필요 없이 모든 클래스에서 Class 클래스를 호출할 수 있다.

하지만 다른 세개의 클래스(`Constructor`, `Method`, `Field`)는 `java.lang.reflect` 패키지에 선언되어 있기 때문에, 해당 클래스 객체를 생성해야 할 때 따로 import해야만 해당 클래스를 호출하여 사용할 수 있다.

### Dog 클래스
```java
public class Dog {
	// Fields
	String name = "coco";
	int age = 5;

	// Constructors
	public Dog() {

	}
	public Dog(String name, int age) {
		this.name = name;
		this.age = age;
	}
	// Methods
	public void move(String name) {
		System.out.println(name + "is moving");
	}
	public void bark() {
		System.out.println("mungmmung");
	}
}
```
구체적인 설명을 위해 Dog 클래스를 생성하고 Dog 클래스의 정보를 Reflection을 통해 가져와 보면서 알아보자

<br>

### Class 클래스
#### 예제코드
```java
Class classOfDog = Dog.class; // Dog 클래스 정보를 담은 Class 객체 생성
System.out.println(classOfDog.getName()); //생성한 Dog 타입 객체의 클래스 이름을 출력
```
#### 출력결과
```java
패키지명.Dog
```
위 코드처럼 `클래스명.class`으로 코드를 작성하면 해당 클래스에 대한 정보들을 하나의 객체로 선언할 수 있다.

그 다음 생성한 객체(위 코드에서는 `classOfDog`)에 다양한 메소드를 사용하여 클래스, 메소드, 필드명을 필요에 따라 가져올 수 있다. (`getName()`, `getDeclaredMethods` 등)

<br>

### Constructor, Method, Field 클래스
생성자, 메소드, 필드 정보는 위에서 생성한 클래스 타입 객체에서 Class 클래스에 선언된 메소드를 사용해서 정보를 가져올 수 있다.

#### 예제코드 - Constuctor 클래스
```java
// 기본 생성자 정보
Constructor constructorOfDog = classOfDog.getDeclaredConstructor();
// 매개변수가 있는 생성자 정보
constructorOfDog2 = classOfDog.getDeclaredConstructor(String.class, int.class);
// 모든 생성자 정보
Constructor[] constructorsOfDog = classOfDog.getDeclaredConstructors();

System.out.println(constructorOfDog);
System.out.println(constructorOfDog2);
System.out.println(constructorsOfDog.length);
```
#### 출력 결과
```
public 패키지명.Dog()
public 패키지명.Dog(java.lang.String,int)
2 // 선언된 생성자의 개수
```
`getDeclaredConstructor()` 메소드는 Dog클래스 정보 중 생성자 하나에 대한 정보를 보여준다.

기본 생성자는 매개변수가 없이 메소드를 선언하면 되지만, 매개변수가 지정되어 있는 생성자의 경우에는 매개변수의 클래스를 지정해줘야 한다.

만약 선언되어 있는 모든 생성자를 한번에 가져와야 할 때에는 `getDeclaredConstructors()` 메소드를 통해 Constructor 타입의 배열 형태로 생성자 정보를 가져올 수 있다.

<br>

#### 예제코드 - Method 클래스
```java
// 메소드 정보(매소드명, 매개변수 타입)
Method methodOfDog = classOfDog.getDeclaredMethod("move", String.class);
// 모든 메소드 정보
Method[] methodsOfDog = classOfDog.getDeclaredMethods();

System.out.println(methodOfDog);
System.out.println(methodsOfDog.length);
```
#### 출력 결과
```
public void 패키지명.Dog.move(java.lang.String)
2 // 선언된 메소드 개수
```
`getDeclaredMethod()` 클래스 객체에서 원하는 메소드 정보를 가져올 수 있는 기능을 수행하는데 매개변수로 `메소드명`과 `매개변수의 클래스`를 지정해야 한다.

만약 매개변수가 없는 메소드라면 매개변수 클래스를 null로 지정하면 된다.

모든 메소드 정보를 가져오고 싶을 때는 `getDeclaredMethods()` 메소드를 통해 배열 형태로 가져올 수 있다.

<br>

#### 예제코드 - Field 클래스
```java
// 변수 정보(변수명)
Field fieldOfDog = classOfDog.getDeclaredField("name");
// 모든 변수 정보
Field[] fieldsOfDog = classOfDog.getDeclaredFields();

System.out.println(fieldOfDog);
System.out.println(fieldsOfDog.length);
```
#### 출력 결과
```
java.lang.String 패키지명.Dog.name
2 // 선언된 변수 개수
```
`getDeclaredField()` 메소드도 객체의 클래스에서 원하는 변수 정보를 가져오는 기능을 하는데 매개변수로 `변수명`을 지정해주면 된다.

모든 변수를 가져오고 싶을 때는 생성자나 메소드 정보를 가져올 때와 마찬가지로 `getDeclaredFields()` 메소드를 통해 배열 형태로 가져오는 것이 가능하다.

> [참고 사이트](https://codechacha.com/ko/reflection/)

> tes test branch
<br>
