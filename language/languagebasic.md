# **:pushpin: 목차**
1. [프로그램 / 프로그래밍 언어란?](#1.-프로그램-/-프로그래밍-언어란?)
2. [저수준 vs 고수준 프로그래밍 언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#2-%EC%A0%80%EC%88%98%EC%A4%80-vs-%EA%B3%A0%EC%88%98%EC%A4%80-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4)
    - [그 전에!! 기계어란?](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EA%B7%B8-%EC%A0%84%EC%97%90-%EA%B8%B0%EA%B3%84%EC%96%B4%EB%9E%80)
    - [저수준 프로그래밍 언어(=어셈블리어)](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EC%A0%80%EC%88%98%EC%A4%80-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%EC%96%B4)
    - [고수준 프로그래밍 언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EA%B3%A0%EC%88%98%EC%A4%80-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4)
3. [정적(Static)언어 vs 동적(Dynamic)언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#3-%EC%A0%95%EC%A0%81static%EC%96%B8%EC%96%B4-vs-%EB%8F%99%EC%A0%81dynamic%EC%96%B8%EC%96%B4)
    - [정적 언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EC%A0%95%EC%A0%81-%EC%96%B8%EC%96%B4)
    - [동적언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EB%8F%99%EC%A0%81-%EC%96%B8%EC%96%B4)
4. [컴파일(Compile)언어 vs 인터프리터(Interpreter)언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#4-%EC%BB%B4%ED%8C%8C%EC%9D%BCcompile%EC%96%B8%EC%96%B4-vs-%EC%9D%B8%ED%84%B0%ED%94%84%EB%A6%AC%ED%84%B0interpreter%EC%96%B8%EC%96%B4)
    - [컴파일 언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EC%BB%B4%ED%8C%8C%EC%9D%BC-%EC%96%B8%EC%96%B4)
    - [인터프리터 언어](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#%EC%9D%B8%ED%84%B0%ED%94%84%EB%A6%AC%ED%84%B0-%EC%96%B8%EC%96%B4)
- [참고자료](https://github.com/kimcno3/TIL/blob/main/language/languagebasic.md#pushpin-%EC%B0%B8%EA%B3%A0%EC%9E%90%EB%A3%8C)


</br>

## **1. 프로그램 / 프로그래밍 언어란?**
- 프로그램이란 명령과 순서를 쓴 **문서**이며, 여기서 말하는 **문서**를 쓰는 언어가 **프로그래밍 언어**이다.
- 프로그램을 컴퓨터가 바로 읽을 수 없으니 이 문서를 0이나 1의 형태(기계어)로 바꿔주는 것도 프로그래밍 언어의 범주, 역할에 속한다.

</br>

## **2. 저수준 vs 고수준 프로그래밍 언어**

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
- "정적언어와 동적언어" 또는 "컴파일 언어와 인터프리터 언어"로 구별이 된다.

</br>

> 동적 언어 / 정적언어의 차이: 자료형 결정 시기에 따른 구분 
> 
> 컴파일 언어 / 인터프리터 언어의 차이 : 실행 방법에 따른 구분

</br>

## **3. 정적(Static)언어 vs 동적(Dynamic)언어**

### **정적 언어**
- 컴파일 전 변수에 들어갈 값의 자료형을 미리 지정하는 언어
- **정적 언어의 장점**
    - 변수의 자료형을 이미 정해진 상태에서 실행되기 때문에 컴파일 시 다른 자료형끼리의 연산으로 인한 오류가 발생할 가능성이 낮다.
    - 실행속도가 동적 언어보다 빠르다.
- **정적 언어의 단점**
    - 컴파일 전 모든 변수값의 자료형을 직접 확인해야 한다.

</br>

### **동적 언어**
- 실행 전 변수에 들어갈 값의 자료형을 미리 지정하지 않고 변수에 따라 형이 결정되는 언어
- **동적 언어의 장점**
    - 자료형에 대한 제약이 적어 유연한 코드를 작성할 수 있다.
- **동적 언어의 단점**
    - 실행해보기 전 자료형에 의한 오류를 발견하기 어렵다.
    - 실행속도가 정적 언어보다 느리다.


</br>

## **4. 컴파일(Compile)언어 vs 인터프리터(Interpreter)언어**


### **컴파일 언어**
- 전체 코딩을 한꺼번에 기계어로 변환해서 명령을 실행하는 프로그래밍 언어
- 문서 생성(코딩) -> 빌드(기계어로 변환) -> 실행파일 생성(기계어로 구성)
- **컴파일 언어의 장점**
    - 실행 속도가 빠르다(기계어로 변환이 완료된 채로 명령을 실행하기 때문에)
- **컴파일 언어의 단점**
    - 운영체제에 대한 유연함이 낮다. 다시 말해, 플랫폼별 호환되는 컴파일러의 변환 과정이 달라 각 플랫폼에 맞는 실행파일을 따로 만들어야 하는 불편함이 생겨난다.

</br>

### **인터프리터 언어**
- 중간언어를 실행하는 중간에 한줄 한줄 기계어로 변환해서 명령을 실행하는 프로그래밍 언어
- 문서생성(코딩) → 빌드(매우 짧음 / C#, Java) → 중간언어(문서형태) → 기계어
- **인터프리터 언어의 장점**
    - 운영체제에 대한 유연함이 높다.
- **인터프리터 언어의 단점**
    - 컴파일 언어에 비해 실행 속도가 느리다

</br>

# **:pushpin: 참고자료**
[tucker님의 유튜브 강의 1~6편](https://www.youtube.com/watch?v=Tq3W8UyltFs&list=PLy-g2fnSzUTAaDcLW7hpq0e8Jlt7Zfgd6)

[또리장군님의 블로그](https://m.blog.naver.com/PostList.naver?blogId=parkjy76&categoryNo=13&logCode=0&categoryName=CSE,%20Etc.#postlist_block)
