# **:pushpin:트랜지스터(Transistor)**

</br>

## **1. 트랜지스터란?**
- 트랜지스터는 쉽게 말해 컴퓨터의 가장 기본적인 요소를 의미한다.(마치 생물의 기본 요소가 단백질(→ 탄소)인 것처럼)
- 컴퓨터의 구성요소 중 하나인 CPU는 트랜지스터 덩어리라고 생각하면 된다. 

</br>

## **2. 트랜지스터 구성요소**
- N(-) P(+) N(-) 으로 구성되어 있으며 P에 전압이 가해져야만 (-)전류가 통과하는 원리로 작동한다.
- 전압이 가해지지 않은 P는 벽과 같은 존재이며 base라고 부른다. 이 base에 input을 걸어서 **논리소자(0 or 1)** 생성

</br>

## **3. 트랜지스터 기능**
#### **- 스위치 기능** 
- 컴퓨터의 0과 1을 표현하는 물리적인 방법 = **2진수 기법**을 활용할 수 있는 방법
- P에 전압을 가하거나 안가하거나로 0과 1을 표현
#### **- 증폭 기능**
- 컴퓨터에서는 거의 사용하지 않음

</br>

## **4. 트랜지스터 용량**
- 트랜지스터 1개 = 1bit = 0 or 1 표현
- 트랜지스터 8개 = 1byte
- 트랜지스터 8 X 1024 = 1Kbyte
- 트랜지스터 8 X 1024 X 1024 = 1Mbyte

</br>

***

</br>

# **:pushpin:논리소자(Logic Element)**

</br>

## **1. 논리소자 종류**
#### **AND : A,B 모두 1일 경우만 결과값 1**
|A|논리소자|B|결과|
|:--:|:--:|:--:|:--:|
|0|AND|0|0|
|0|AND|1|0|
|1|AND|0|0|
|1|AND|1|1|

</br>

#### **OR : A, B 둘 중 하나라도 1일 경우 결과값 1**
|A|논리소자|B|결과|
|:--:|:--:|:--:|:--:|
|0|OR|0|0|
|0|OR|1|1|
|1|OR|0|1|
|1|OR|1|1|

</br>

#### **XOR : A,B 가 다를 경우 결과값 0**
|A|논리소자|B|결과|
|:--:|:--:|:--:|:--:|
|0|XOR|0|0|
|0|XOR|1|1|
|1|XOR|0|1|
|1|XOR|1|0|

</br>

#### **NOT : 입력값과 반대되는 결과값 산출**
|A|논리소자|결과|
|:--:|:--:|:--:|
|0|NOT|1|
|1|NOT|0|

</br>

## **2. 옴의 법칙(Ohm's law)**

</br>

> ### *V = IR  ,  I(전류) = V(전압)/R(저항)*

</br>

- 저항이 높으면 전류는 낮아지고, 저항이 낮으면 전류는 높아진다.
- 트랜지스터 base에 전압을 가하면(**input =1**) 저항이 O에 가까워져 전류가 흐르고(**도체**), base에 전압을 가하지 않으면(**input = 0**) 저항이 무한에 가까워 전류가 흐르지 않는다.(**부도체**)

</br>

## **3. 도체, 부도체, 반도체**

- **도체** : 전기가 흐르는 물체 /  R = 0에 가까움
- **부도체** : 전기가 흐르지 않는 물체 / R = ∞에 가까움
- **반도체** : 상황에 따라 전기가 흐르거나 흐르지 않는 물체(=트렌지스터)

</br>

## **4. 논리소자로 계산기 만들기**

### **가산기(1bit)**
|input1|input2|C|S|
|:--:|:--:|:--:|:--:|
|0|0|0|0|
|0|1|0|1|
|1|0|0|1|
|1|1|1|0|  
- C = AND / S = XOR 이며 이를 조합하여 "가산기" 를 만들 수 있다.
- 또한 C와 또 다른 1bit 가산기와 결합하면 2bit 가산기도 생산 가능(연산 가능 단위 증가)
- 가산기 뿐만 아니라 다른 논리소자 조합으로 감산기, 곱셈, 나눗셈 만들 수 있다.  

</br>

***

</br>


# **:pushpin:컴퓨터(Computer)**

</br>

## **1. 컴퓨터란?**
 - 컴퓨터란 명령(CPU 시선에선 사칙연산같은 단순 명령)을 하나씩 순서대로 수행하는 기계를 의미
- 어떤 명령을 어떤 순서로 수행할 건지를 기술해 놓은 것이 프로그램
- 문자, 그림, 음악 모두 숫자로 표현 가능하다.(A:1, B:2)
    - **문자**
        - **ASCⅡ코드** : 255개까지의 문자 개수에 대해 부여된 코드
            - 1byte규모 : 8bit이므로 2의 8제곱 개의 문자를 표현 가능(0 ~ 255)
        - **UNICODE** : 2byte내에서 전세계 모든 문자에 코드를 할당한 문자 전산 처리 방식
            - 2의 16제곱 개의 문자 표현 가능
    - **그림(색)**
        - R(0~255) G(0~255) B(0~255)로 할당(각각 1Byte)
    - **소리**
        - 주파수에 따른 파장의 크기를 각각 숫자에 할당

</br>

## **2. 컴퓨터 구성품(요리과정에 비유)**
- **CPU** = 쉐프 : 요리(연산)를 준비하도록 지시하고 실시하는 역할
- **하드디스크** = 마트 : 요리에 필요한 재료가 저장되어있는 공간
- **메모리** = 냉장고 : 필요한 재료를 보관해두는 공간
- **레지스터** = 도마+보조쉐프 : 쉐프가 요리를 할 수 있도록 필요한 재료를 도마 위에 올려다 주는 역할
- **캐시메모리** = 요리대 옆 공간 : 자주쓰는 재료를 쉐프와 더 가까운 곳에 보관해두는 공간(4Kbyte 용량)

</br>

***

</br>


# **:pushpin:프로그래밍 언어(Programming Language)**

</br>

## **1. 프로그램 / 프로그래밍 언어란?**
- 프로그램이란 명령과 순서를 쓴 **"문서"**이며, 여기서 말하는 **"문서"**를 쓰는 언어가 **"프로그래밍 언어"**이다.
- 프로그램을 컴퓨터가 바로 읽을 수 없으니 이 문서를 0,1 형태(기계어)로 바꿔주는 것도 프로그래밍 언어의 범주, 역할에 속한다.
    - 사람  프로그래밍 언어  기계어  컴퓨터

</br>

## **2. 프로그래밍 언어 종류**

### **그 전에!! 기계어란?**
- 기계어란 이진법을 활용해 0과 1만을 조합하여 컴퓨터가 직접적으로 이해할 수 있는 언어를 의미한다.
- 프로그래밍을 통해 사용자가 원하는 작업을 컴퓨터에게 시키기 위해선 결국 최종적으로 기계어로 번역이 완료되어야 한다.

### **저수준 프로그래밍 언어(=어셈블리어)**
- 기계어로 쉽게 변환이 가능한 저급 언어
- 명령어(OP) :단순 연산만 처리하는 명령

        ex) ADD, SUB, MUL, JMP 등
- **OPCODE** : 각 명령어(OP)에 숫자를 부여한 코드

        ex) ADD = 0001 , SUB = 0010 . MUL = 0011 , JMP = 0100

> 즉, " ADD 3,4 " 라는 실행 코드를 "0001 0011 0100" 으로 변환해야 컴퓨터가 이해할 수 있다.

</br>

### **고수준 프로그래밍 언어**
- 기계어로 쉽게 변환이 불가능해 변환기(컴파일러)가 필요한 언어
- C언어, JAVA, Python 등 우리가 널리 사용하는 언어들이 바로 고수준 프로그래밍 언어이다.
- "동적언어와 정적언어" 또는 "[컴파일 언어]()와 [인터프리터 언어]()"로 구별이 된다.

</br>

#### **컴파일(Compile) 언어**
- 전체 코딩을 한꺼번에 기계어로 변환해서 명령을 실행하는 프로그래밍 언어
- 문서 생성(코딩) -> 빌드(기계어로 변환) -> 실행파일 생성(기계어로 구성)
- 컴파일 전 변수에 들어갈 값의 자료형을 미리 지정해야 한다.
- **컴파일 언어의 장점**
    - 실행 속도가 빠르다
        - 기계어로 변환이 완료된 채로 명령을 실행하기 때문에
        - 변수의 자료형을 이미 정해진 상태에서 실행되기 때문에
- **컴파일 언어의 단점**
    - 운영체제에 대한 유연함이 낮다. 다시 말해, 플랫폼별 호환되는 컴파일러의 변환 과정이 달라 각 플랫폼에 맞는 실행파일을 따로 만들어야 하는 불편함이 생겨난다.

</br>

### **인터프리터(InterPreter) 언어**
- 중간언어를 실행하는 중간에 한줄 한줄 기계어로 변환해서 명령을 실행하는 프로그래밍 언어
- 문서생성(코딩) → 빌드(매우 짧음 / C#, Java) → 중간언어(문서형태) → 기계어
- 실행 전 변수에 들어갈 값의 자료형을 미리 지정하지 않는다. 
- **인터프리터 언어의 장점**
    - 운영체제에 대한 유연함이 높다.
- **인터프리터 언어의 단점**
    - 컴파일 언어에 비해 실행 속도가 느리다
    - 자료형에 대한 정보가 없는 상태로 실행되다 보니 예상하지 못한 변수의 자료형으로 인한 오류가 발생하기 쉽다.