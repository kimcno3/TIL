# :pushpin: 목차
### [:pushpin: 함수 모음](#pushpin-함수-모음) 
- [includes()](#includes) 
- [replace()](#replace) 
- [isNAN()](#isNAN)
- [push() , pop()](#push--pop) 
- [unshift() , shift()](#unshift--shift)
- [concat()](#concat)
- [join()](#join)
- [indexOf() , lastIndexOf()](#indexOf--lastIndexOf)
- [slice()](#slice)
- [splice()](#splice)
- [split()](split)

### [:pushpin: 개념 정리](#pushpin-개념-정리) 
- [배열(Array)](#배열Array)
- [함수(Function)](#함수Function)
- [객체(Object)](#객체Object)
<br>

# :pushpin: 함수 모음

## **includes**()
문자열이 특정 문자열을 포함하는지 확인하는 메서드

```jsx
string.includes(searched_string, start_index)

// searched_string : 검색할 문자열로 필수 요소. 대소문자를 구분
// start_index : 검색을 시작할 index 값. 선택 요소. 값이 없으면 문자열 전체 대상 지정
```

**예시**
```jsx
let string = 'hello world'
string.includes('h')

// 'hello world' 전체 문자열에서 'h'의 유무를 검사
// 포함한다면 true, 미포함한다면 false 반환

// 결과 값 : true


string.includes('h', 2)

// 'llo world' 에서 'h'의 유무를 검사

// 결과 값 : false
```
<br>

## **replace**()
특정 문자열을 원하는 문자열로 바꿔주는 메서드
```jsx
string.replace(delete_string, new_string)

// delete_string : 삭제되는 문자열
// new_string : delete_string 대신 추가되는 문자열
```
**예시**
```jsx
let string = '010-1234-5678'
string.replace('-', '')

// replace 메서드는 제일 먼저 일치하는 문자열 하나만 바꿔준다.

// 결과 값 : 0101234-5678
```
- 모든 문자열을 한번에 교체하고 싶다면 **정규표현식**을 사용해야 한다.
> 정규표현식**: 문자열에 나타나는 특정 문자 조합과 대응시키기 위해 사용되는 패턴

```jsx
let string = '010-1234-5678'
string.replace(/-/gi, '') 

// g : 전체 모든 문자열을 변경 global
// i : 영문 대소문자를 무시, 모두 일치하는 패턴 검색 ignore

// 결과 값 : 01012345678


sting.replace(/\-/g,'');

// 정규식으로 특수문자 제거하는 방식

// 결과 값 : 01012345678
```

<br>

## **isNAN**()
문자열이 숫자인지 체크하기 위해서 사용하는 함수 <br>


```jsx
isNAN()

// NAN은 'Not a Number'의 약자입니다.
```
**예시**
```jsx
let string = 'hello world'
isNAN(string)

// 결과물 : true

===============================

let number = '1234'
isNAN(number)

// 결과물 : false

```

<br>

## **push**() , **pop**()
배열 가장 뒷 순서에서 값을 추가, 삭제하는 기능 <br>


```jsx
push(value) // 추가
pop() // 삭제
```

**예시**
```jsx
let arr = [];

arr.push(1);
arr.push(2);

arr // [1,2]

arr.pop();

arr // [1]
```

<br>

## **unshift**() , **shift**()
배열 가장 앞 순서에서 값을 추가, 삭제하는 기능 <br>


```jsx
unshift(value) // 새로운 값 추가
shift() // 가장 맨 앞의 값 삭제
```

**예시**
```jsx
let arr = [];

arr.unshift(1);
arr.unshift(2);

arr // [2,1]

arr.shift();

arr // [1]
```

<br>

## **concat**()
concat: 배열 합치기, 문자열도 가능
```jsx
value1.concat(value2) // value1에 value2를 합친다. 
```

**예시**
```jsx
let arr1 = [1,2,3,4];
let arr2 = [5,6,7,8];

let result = arr1.concat(arr2);
console.log(result); // [1, 2, 3, 4, 5, 6, 7, 8]
```

<br>

## **join**()
기능 설명
```jsx
// 문법
```

**예시**
```jsx

```

<br>

## **indexOf**() , **lastIndexOf**()
기능 설명
```jsx
// 문법
```

**예시**
```jsx

```

<br>

## **slice**()
기능 설명
```jsx
// 문법
```

**예시**
```jsx

```

<br>

## **splice**()
기능 설명
```jsx
// 문법
```

**예시**
```jsx

```

<br>

## **split**()
기능 설명
```jsx
// 문법
```

**예시**
```jsx

```

<br>

***

<br>

# :pushpin: 개념 정리

## 배열(Array)
### 배열이란?
- 배열(array)는 자바스크립트에서 가장 많이 사용하는 자료구조 종류 중 하나
- 주로 같은 종류의 값을 여러개 묶어서 저장
- 배열은 '객체'이다.

### 배열 생성 방법
``` jsx
var scores = [50, 60, 70];
console.log(scores);
console.log(scores.length);
```

### 배열의 마지막 원소를 읽을라면?(배열이 너무 길 경우) 
``` jsx
scores[scores.length - 1];
```

### 문자열과 배열
- 문자열과 배열은 비슷한 성질을 많이 가지고 있습니다.
    - 문자열: Immutable 
    - 배열: Mutable
```jsx
// 배열의 속성과 메소드를 문자열에도 테스트

var hi = 'hello';
hi[0];

hi[0]; = 'k';
console.log(hi);
```
> **결론 : 문자열은 배열과 달리 원하는 인덱스값만 바꿀 수 없다.**

<br>

## 함수(Function)
### 함수 특징
- return값이 있는 함수를 호출하는 경우, 변수에 값을 할당하기 위해 사용한다.
    ```jsx
    var five = function() {
        return 5;
    }

    var n = five(); // 변수 n에 return값 5 할당
    console.log(n); // 5
    ```
- return값이 없는 함수를 변수에 할당하면 undefined값이 된다.
    ```jsx
    var foo = function() {
        console.log(5);
    }

    var n = foo();
    console.log(n); // undefined
    ```
- 값이 없는 return은 해당 함수를 종료시키는 역할
- 반복문에서 break와 비슷한 기능
    ``` jsx
    var test1 = function(text) {
        // 매개변수가 'exit'일 경우 함수 종료
        if (text === "exit") {
            return;
        }   
        // 그 외 경우 log 출력
        console.log("보이나요?");    
    }

    test1("hoho");
    test1("exit");
    ```
### 함수 사용의 장점
- 가독성이 좋아진다.
- 유지보수하기 편하다.

### 함수 활용 팁
- **매개 변수**와 **리턴**을 적극적으로 활용하자.
- 줄 수가 지나치게 길어지면 함수로 빼자.(함수 하나에 10줄 이하로 유지)
- 인덴트가 지나치게 깊어져도 함수로 빼자.
- 함수는 반드시 한 가지 일만 하도록 하자.

<br>

## 객체(Object)
### 객체란 무엇인가?
- 현실의 물체에 대응되는 개념입니다.
- 객체를 사용하면 변수와 함수를 묶어서 관리하게 됩니다.
- 객체는 속성(property)과 메소드(method)를 가집니다.

### 객체 지향 프로그래밍
- 유지보수가 쉬워진다.
- 가독성이 높아진다.
- 대형 프로그램을 짜기 쉬워진다.
- 객체와 객체가 협력해서 일을 한다.
- 객체는 일에 책임을 진다.
- 객체는 객체에 메시지를 보낸다.
- 객체는 자율적으로 일을 한다.

### 객체 선언 방법
- this 키워드 : 메소드 안에서 사용시 함수를 소유한 객체를 가르킨다.
    ```jsx
    var p2 = {}; // p2 객체 선언
    p2.name = "crong"; // 이름 속성 
    p2.weight = 80; // 몸무게 속성
    p2.say = function(word) { // 말하는 메서드
    console.log(this.name + " says, " + word); // this = p2 , word는 매개변수
    };

    console.log('My name is ' + p2.name); // My name is crong
    console.log('My weight is ' + p2.weight + 'kg'); // My weight is 80kg
    p2.say('Nice to meet you!') // crong says, Nice to meet you!
    ```
 - JSON 표기법 활용 객체 생성
    > JSON : 서버에 저장되는 데이터의 표준 포맷 양식 , {키:값} 형태
    ```jsx
    // 사람 1
    var m1 = {
        "name": "Kim",
        "hp": 100,
        "power": 10,
        "attack": function(target) {
        target.hp -= this.power;
        }
    };
    // 사람 2
    var m2 = {
        "name": "Shin",
        "hp": 100,
        "power": 20,
        "attack": function(target) {
        target.hp -= this.power;
        }
    };
    // 커피
    var c1 = {
        type: "Coffee",
        energy: 10
    };
    // eat 매소드 생성
    m2.eat = function(food) {
        this.hp += food.energy;
    }

    m1.attack(m2) // m1의 power만큼 m2의 hp 감소
    m2.eat(c1) // c1의 energy 만큼 m2의 hp 증가
    ```