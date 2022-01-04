# :pushpin: Javascript

## :pushpin: 목차
**[:pushpin: 함수 모음](#pushpin-함수-모음)**
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
- [split()](#split)
- [Math.min() , Math.max()](#Mathmin--Mathmax)
- [sort()](#sort)
- [substring() , substr()](#substring--substr)
- [Map()](#Map)
- [Array.from()](#Arrayfrom)

**[:pushpin: 고차함수 모음](#pushpin-고차함수-모음)**
- [forEach()](#forEach)
- [map()](#map)
- [filter()](#filter)
- [reduce()](#reduce)
- [every() , some()](#every--some)
- [flat()](#flat)

**[:pushpin: 개념 정리](#pushpin-개념-정리)**
- [자료형(Types)](#자료형Types)
- [Truthy and Falsy](#Truthy-and-Falsy)
- [Primitive vs Reference](#Primitive-vs-Reference)
- [일반 변수와 참조 변수](#일반-변수와-참조-변수)
- [배열(Array)](#배열Array)
- [함수(Function)](#함수Function)
- [객체(Object)](#객체Object)
- [객체 생성자(Object Constructor)](#객체-생성자Object-Constructor)
- [프로토타입(Prototype)](#프로토타입Prototype)
- [DOM(Document Object Model)](#DOMDocument-Object-Model)
- [스코프(Scope)](#스코프Scope)
- [호이스팅(Hoisting)](#호이스팅Hoisting)

**[:pushpin: 참고 사이트](#pushpin-참고-사이트)**

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
> 정규표현식: 문자열에 나타나는 특정 문자 조합과 대응시키기 위해 사용되는 패턴
> 정규표현식의 기본 내용 : [링크](https://curryyou.tistory.com/234)


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
push(value) // 배열 가장 뒷 순서에 value 추가
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

console.log(arr1) 
// [1, 2, 3, 4]
// concat()을 사용해도 value1은 변하지 않는다.
```

<br>

## **join**()
배열을 문자열로 바꿀 때 사용합니다.
```jsx
array.join('string')

// array : 문자열로 바꿀 배열
// string : 배열 각각의 값 사이에 추가할 문자열 , string을 기준으로 배열 안의 값이 나눠진디.
```

**예시**
```jsx
let arr = ['H' , 'E' , 'L' , 'L' , 'O']

arr.join() 
// 'H,E,L,L,O'
// 기본적으로 ','가 사용된다.

arr.join('')
// 'HELLO'
// 아무 문자열 없이 '' 만 사용

arr.join(' ')
// 'H E L L O'
// 띄어쓰기 사용

arr.join(' / ')
// 'H / E / L / L / O'

console.log(arr)
// ['H', 'E', 'L', 'L', 'O']
// join()을 사용해도 기존 배열은 변하지 않는다.
```

<br>

## **indexOf**() , **lastIndexOf**()
- indexOf() : 배열이나 문자열 안의 원소를 가지고 첫 인덱스를 찾는다.
- lastIndexOf() : 배열이나 문자열 안의 원소를 가지고 마지마 인덱스를 찾는다.
```jsx
indexOf(value) 
lastIndexOf(value)

// value : 인덱스를 찾고자 하는 값
```

**예시**
```jsx
// 배열 선언
let arr = [10, 20, 30, 40, 10, 50];

arr.indexOf(10); // 0 , 가장 앞에 있는 인덱스 출력
arr.indexOf(65535); // -1 , 원소값이 해당 배열에 없는 경우 -1 출력
arr.lastIndexOf(10); // 4 가장 마지막 인덱스 출력

// indexOf() 가  -1이 나오는 것을 기준으로 중복여부를 판단할 수 있다.
if (arr.indexOf(60) === -1){ // 60이 배열에 존재하는지 여부 판단
    arr.push(60); // 중복되는 값이 아니라면 배열에 추가
}
console.log(arr) // [10, 20, 30, 40, 10, 50, 60];

// indexOf() 나 lastIndexOf() 를 사용해도 기존 배열은 변하지 않는다.

// 문자열 선언
let string = 'booboo' 

string.indexOf('b') // 0
string.indexOf('a') // -1
string.lastIndexOf('b') // 3 

// 중복 여부 판단으로 활용
if (string.indexOf('n') === -1){
    string += 'n';
}
console.log(string); // booboon

//문자열의 경우, 배열과 다르게 기존 문자열도 바뀐다.
console.log(string); // booboon

```

<br>

## **slice**()
기존 배열을 잘라 새로운 배열을 만든다.
```jsx
slice(startIndex, endIndex)

// startIndex : 시작 index, 이 위치부터 배열을 자른다.(포함 O)
// endIndex : 끝 index , 이 위치 직전의 index까지 배열을 자른다. (포함 X)
```

**예시**
```jsx
let arr = [1, 2, 3, 4, 5];

let newArr = arr.slice(2, 4); // index 2 ~ index 4 직전의 위치 == index 3
console.log(newArr); // [3, 4]

// 기존 배열은 변하지 않는다.
console.log (arr) // [1, 2, 3, 4, 5]
```

<br>

## **splice**()
- 기존 배열을 잘라 새로운 배열을 만든다.
- **잘라낸 원소들은 원본 배열에서 사라진다.(slice()와 차이점)**

```jsx
splice(startIndex, numElement)

// startIndex : 시작 index, 이 위치부터 배열을 자른다.(포함 O)
// numElement : 잘라낼 원소의 수
```
**예시**
```jsx
let arr = [1, 2, 3, 4, 5];

arr.slice(2, 4); // [3, 4, 5] , index 2부터 3개의 원소
console.log(arr); // [1, 2] , 기존 배열이 수정된다.
```

<br>

## **split**()
문자열을 문자의 배열로 나누고 싶을 때 사용하는 메소드

```jsx
string.split(value)

// string : 배열로 나누고 싶은 문자열
// value : 기준이 될 값, value를 기준으로 문자열을 잘라 배열의 원소를 만든다.
```

**예시**
```jsx
let string = "hello, world a-b-co,ltd";
string.split(""); // ['h', 'e', 'l', 'l', 'o', ',', ' ', 'w', 'o', 'r', 'l', 'd', ' ', 'a', '-', 'b', '-', 'c', 'o', ',', 'l', 't', 'd']
string.split(",");// ['hello', ' world a-b-co', 'ltd']
string.split("-"); // ['hello, world a', 'b', 'co,ltd']

string // 기존 배열은 변하지 않는다.
```

<br>

## **Math.min**() , **Math.max**()
인자값에 최소값과 최대값을 구하는 Math객체 메소드
```jsx
Math.min(value)
Math.max(value)

// value : 최소값을 찾고 싶은 인자값들
```

**예시**
```jsx
Math.min(1,2,3,4,5) // 1
Math.max(1,2,3,4,5) // 5

// 배열에서 최소, 최대값을 구하고 싶은 경우
// 전개연산자 ...을 활용해야 한다.
// (...arr) === (arr[0] , arr[1] , arr[2] ... ) 

let arr = [1,2,3,4,5]
Math.min(...arr) // 1
Math.max(...arr) // 5
```

<br>

## sort()
배열을 오름차순 또는 내림차순으로 정렬
```jsx
arr.sort((a,b) => a-b); // 오름차순
arr.sort((a,b) => b-a); // 내림차순

// a : i번째 요소
// b : i+1번째 요소
```

**예시**
```jsx
let arr = [2,4,1,3,5];

arr.sort((a,b) => a-b); // [1,2,3,4,5]
arr.sort((a,b) => b-a); // [5,4,3,2,1]
```
만약 콜백함수를 사용하지 않고 sort함수만 호출할 경우, 배열의 요소를 **ASCII 문자 기준 오름차순**으로 정렬한다.
```jsx
let arr = [1,2,4,3,10,23]; 

arr.sort(); // [1, 10, 2, 23, 3, 4]
```

<br>

## substring() , substr()
문자열에서 특정 위치에서 시작하여 특정 문자 수 만큼의 문자들을 반환
```jsx
substring(startIndex , lastIndex)
// startIndex : 시작점이 될 문자열의 인덱스
// lastIndex : 끝점이 될 문자열의 인덱스
// startIndex부터 lastIndex 바로 전까지 반환한다.
// slice() 와 같은 인자 규칙

substr(startIndex , Number)
// startIndex : 시작점이 될 문자열의 인덱스
// value : startIndex 부터 반환할 문자열의 개수
// splice() 와 같은 인자 규칙
```

**예시**
```jsx
let str = 'Hello'

str.substing(0,3) // 'Hel' , 0~2까지의 문자열을 반환한다.
str.substr(0,3) // 'Hel' , 0부터 3개의 문자열을 반환한다.

// 문자열을 immutble 성격을 가지고 있기 때문에 메소드를 사용한다 해도 기존에 선언된 변수는 변하지 않는다.
```

<br>

## Map()
### 기본 개념
Object, Set과 같은 해쉬 테이블 유형 중 하나이며, `key : value` 구조로 이루어져 있다. 
### Object와의 차이점
|특징|Map|Object|
|--|--|--|
|키 자료형|어떤 자료형도 키값으로 지정 가능|`String` or `symbol`민 가능|
|정렬|키가 자동으로 정렬|정렬 X|
|크기|size로 파악 가능|직접 알아내야 한다.|

### 사용 함수
1. set() : 키와 value를 선언하는 함수
2. get() : 선언된 키에 해당하는 value를 가져오는 함수
3. has() : 키와 value의 존재여부를 파악하는 함수(boolean)
    - 조건문 조건식으로 활용 가능
4. keys() , values() : 선언된 모든 키값 또는 value값을 전부 가져오는 함수

### 예시
```jsx
// map 객체 생성
let m = new Map();

// 키로 선언할 변수 선언
let name = 'Kim';
let age = 26;
let phone = {'iphone' : 12}

// set(key , value) 
m.set(name, 0);
m.set(age , 1);
m.set(phone, 2);

console.log(m); // Map(3) {'Kim' => 0, 26 => 1, {…} => 2}

//get(key) 
m.get(name); // 0
m.get(age); // 1
m.get(phone); // 2

//get()을 활용한 value값 재할당
m.set(age , m.get(age) + 1); // value값을 1 => 2 로 재할당
m.get(age); // 2

// has(key) 
m.has(name) // true
!m.has(name) // false

// keys() , values()
m.keys() // {'Kim', 26, {…}}
m.values() // {0, 2, 2}
```

<br>

## Array.from()
유사 배열 객체(array-like object)나 반복 가능한 객체(iterable object)를 얕게 복사해 새로운Array 객체를 생성하는 메소드
### 예시
```jsx
// string, array에서 배열 생성
Array.from('foo'); // ["f", "o", "o"]
Array.from([1, 2, 3]); // [1, 2, 3]

// Set객체로 배열 만들기
let s = new Set('age' , 26);
Array.from(s); // ['age' , 26]

// Map객체로 배열 만들기
let m = new Map(['name', 'kim'], ['age', 26]);
Array.from(m); // [['name', 'kim'], ['age', 26]];
Array.from(m.keys()) // ['name', 'age'];
Array.from(m.values()) // ['kim', 26];

// 화살표 함수 사용
Array.from({length:5} (v,i) => i+1); //  [1, 2, 3, 4, 5]
```

<br>

***

<br>

# :pushpin: 고차함수 모음
## **forEach()**
반복문과 같은 기능을 실행하는 함수입니다.

### 함수 기본 구조
```jsx
arr.forEach(function callback(value, index) {} , thisArg)
```
- `arr` : 사용할 배열
- `function callback` : callback되는 함수(매개변수로 배열의 요소(`value`)와 index값(`index`)를 받는다.)
- `thisArg` : callback 함수에서 this로 사용하는 값으로 Optional 인자다.

<br>

### 예시
```jsx
let a = [10,11,12,13,14,15];

a.forEach(function predicate(v, i){  // v : 배열 요소, i : 인덱스값
                    console.log( v + ',' + i));
                });

// 결과
// 10,1
// 11,2
// 12,3
// 13,4
// 14,5
// 15,6

// =>를 활용하면 간단하게 코드를 작성할 수 있다.
a.forEach((v, i) => console.log(v + ',' + i));
```
<br>

## **map()**
기존 배열의 요소들에게 변화를 주는 함수

### 함수 기본 구조
```jsx
arr.map(function callback(value, index) {} , thisArg)
```
- `arr` : 사용할 배열
- `function callback` : callback되는 함수(매개변수로 배열 요소(`value`)와 index값(`index`)를 받는다.)

### 예시
```jsx
let a = [10,11,12,13,14,15];

let answer = a.map(function predicate(v, i){  // v : 배열 요소, i : 인덱스값
                    return v*v; // 기존 배열 요소의 제곱값을 담은 새로운 배열 생성
                });
console.log(answer);

// 결과
[100, 121, 144, 169, 196, 225]

// =>를 활용하면 간단하게 코드를 작성할 수 있다.
let answer = a.map((v) => v*v);
```

<br>

## **filter()**
기존 배열에서 특정 조건에 해당하는 요소만 가져오는 함수

### 함수 기본 구조
```jsx
arr.map(function callback(value, index) {} , thisArg)
```
- `arr` : 사용할 배열
- `function callback` : callback되는 함수(매개변수로 배열 요소(`value`)와 index값(`index`)를 받는다.)

<br>

### 예시
```jsx
let a = [10,11,12,13,14,15];

let answer = a.filter(function predicate(v, i){  // v : 배열 요소, i : 인덱스값
                    return v%2 === 0; // 특정 조건을 부여(짝수)
                });
console.log(answer);

// 결과
[10, 12, 14]

// =>를 활용하면 간단하게 코드를 작성할 수 있다.
let answer = a.filter((v) => v%2 === 0);
```

<br>

## **reduce()**
기존 배열의 요소를 활용해 특정 값을 생성해 내는 함수(전체합, 최대값 등)

### 함수 기본 구조
```jsx
arr.reduce(function callback(makingValue , currentValue) {} , firstValue)
```
- `arr` : 사용할 배열
- `function callback` : callback되는 함수
    - `makingValue` : 만들어지는 특정 값
    - `currentValue` : `sum`에 추가될 현재 배열요소
- `firstValue` : 초기값

<br>

### 예시
```jsx
let a = [10,11,12,13,14,15];

let answer = a.reduce(function predicate(sum, v){  // sum : 만들어지는 값 , v : 현재 배열 요소
                    return sum + v; // 전체합 공식 생성
                } , 0); // 0 : 초기값
console.log(answer);

// 결과
75

// =>를 활용하면 간단하게 코드를 작성할 수 있다.
let answer = a.reduce((sum, v) => sum + v, 0);
```
<br>

## **every() , some()**
- `every()` 함수는 원하는 배열의 요소들 전부 특정 조건에 부합해야만 `true`를 반환합니다.
> [every() 함수 상세 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
- `some()` 함수는 배열의 요소들 중 하나라도 특정 조건에 부합한다면 `true`를 반환합니다.
> [some() 함수 상세 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/some)

### **예제**
```jsx
var onlyEven = [2,4,6]; // 짝수만 있는 배열
var mixedBag = [2,4,5,6]; // 섞여있는 배열

// 홀수, 짝수를 구분하는 함수 선언
var isEven = function(x) { return x % 2 === 0 };


// every() 활용
onlyEven.every(isEven); // 모든 요소가 짝수일 경우, true
mixedBag.every(isEven); // 하나라도 짝수가 아니라면 false

// some() 활용
mixedBag.some(isEven);// 하나라도 짝수가 있다면 true
```

<br>

## **flat()**
모든 하위 배열 요소를 지정한 깊이까지 재귀적으로 이어붙인 새로운 배열을 생성
> [flat() 상세 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)

### 함수 기본 구조
```jsx
arr.flat(depth)
```
`depth`는 배열 중복의 깊이를 의미하며 기본값은 `1`입니다.

<br>

### 예제
```jsx
//배열깊이가 2일 경우
[ [1, 2], [3, 4] ].flat(); // [1, 2, 3, 4]

// 배열깊이가 3일 경우
[ [1, 2, [3]], [4, 5] ].flat(); // [1, 2, [3], 4, 5]

// 배열깊이가 3, 매개변수에 2를 지정
[ [1, 2, [3]], [4, 5] ].flat(2); // [1, 2, 3, 4, 5]
```

<br>

***

<br>

# :pushpin: 개념 정리

## 자료형(Types)
### 자료형이랑?
우리가 변수에 담을 수 있는 존재를 **값**이라고 하는데, 이 값의 종류를 **자료형**이라고 한다. 자바스크립트에서 자료형은 **7가지**로 구분할 수 있다.

### 1. String Type (문자열)
- 따옴표를 이용해 표현합니다.
- 문자열은 더 할 수 있습니다. 예) "a" + "b" === "ab"
- 문자열은 유사배열입니다.
- Index를 이용해 각 문자열에 접근할 수 있습니다.
- .length 속성이 있습니다. 예) "abc".length === 3

### 2. Number Type (숫자)
- 숫자는 여러분이 이미 알고 계신 그대로 숫자일 뿐입니다.
- 더하기, 빼기, 곱하기, 나누기 등의 연산이 가능합니다.
- Infinity 혹은 -Infinity 등과 같이 무한대를 표현하는 숫자값도 있습니다.
- NaN이라는 값 또한 숫자입니다.
    - "Not A Number"를 의미합니다.
    - 주로 숫자가 아닌 값을 숫자로 치환할때 의도치않게 자주 나타나는 값입니다. 예) Number("abc")

### 3. Boolean Type
- true, false 두 가지 값이 있습니다.
- Boolean값 선언시 주의할 점
    ```jsx
    var o = new Boolean(true);  // 이렇게 만들어 사용하지 마세요.
    var t = true; // 항상 이렇게 만들어 사용하세요.
    ```
### 4. Undefined Type
- "없음"을 의미합니다.
- undefined라는 값이 있습니다.
- 초기값이 할당되지 않은 변수나 매개변수 등은 모두 undefined 값을 기본값으로 합니다.
- 객체에서 없는 속성을 접근하는 경우, undefined 값이 결과로 도출됩니다.

```jsx
// 초기값이 할당되지 않은 변수
let a;
console.log(a); // undefined

// 초기값이 할당되지 않은 매개변수
function foo (a, b) {
  console.log(a); // 1
  console.log(b); // undefined
}
foo(1);

// 객체에서 존재하지 않는 속성을 접근하는 경우
const something = {
  name: 'Ken'
};
console.log(something.age); // undefined
```

### 5. Null Type
- "없음"을 의미합니다.
- null이라는 값이 있습니다.
- 명시적으로 "값이 없음"을 나타낼때 주로 사용됩니다.
- 간혹 혼돈하시는 분들을 위해 명시하자면, null === null 은 true입니다.
- 비록 undefined와 같이 "없음"을 나타내는 값일지라도, 대입한 적 없는 변수 혹은 속성과 명시적으로 "없음"을 나타내는 경우를 구분을 할 수 있어야 코드의 의미가 명확해 질 것입니다. undefined는 전자, null은 후자의 경우에 많이 쓰입니다.

```jsx
let bar = [ 1, 2, 3 ];
bar = null; // bar라는 변수에 "값이 없음"이라고 표기함
```

> `Undifined` vs `Null` 용도의 차이
>
> `Undifinde` 값은 말그대로 **정의되지 않는 값**으로 값이 대입되지 않은 상태임을 표현 <br>
> `Null` 값은 **의도적으로 값이 없음**을 표현


### 6. Object Type
- 일반 객체 뿐 아니라, 배열과 함수도 객체에 포함됩니다.

```jsx
const person = {};            // 빈 객체 생성
person.name = 'ken';        // 객체 내 Key, Value 생성
console.log(person.name);   // 'ken'
console.log(person);        // { name: 'ken' }
console.log(typeof person); // 'object'

const list = [1, 2, 3];
console.log(typeof list);   // 'object'

function foo () {}
console.log(typeof foo);    // 'function' (이상한 자바스크립트..)
```

### 7. Symbol Type (new in ES2015, the least of your concern)

<br>

## Truthy and Falsy
### Truthy? Falsy?
자료형과 더불어 자바스크립트의 값들을 나누는 또 다른 기준으로 해석하자면 "진실같은 성격"(Truthiness)와 "거짓같은 성격"(Falsiness)로 볼 수 있습니다. 자바스크립트의 모든 값들은 둘 중 한 가지에 속합니다.

### Falsy인 경우
```jsx
0
-0
false
undefined
null
""
''
``
NaN
```
> 위의 경우를 제외한 모든 값은 Truthy입니다.

<br>

## Primitive vs Reference
### Primitive
- 실제 값을 변수에 할당하는 Type
- Object를 제외한 모든 자료형이 해당
#### **Primitive 비유 설명**
변수가 포스트잇이라 생각했을 때, **Primitive** 타입은 포스트잇에 실제 값을 적어 관리하는 형태라고 생각하면 됩니다.

#### **예시 코드**
```jsx
let a = 10;
const b = a;

a = 30;

console.log(b); // ?
```
#### **예시 코드 해석**
- `let a = 10;` <br>
  : a 포스트잇에 10을 적는다.
- `const b = a;` <br>
: b 포스트잇에 a 포스트잇에 적힌 내용을 똑같이 적는다.
- `a = 30;` <br>
  : 새로운 a 포스트잇에 30를 적고 기존 a 포스트잇은 버린다. (재활용 X)
- `console.log(b);` <br>
  : b 포스트잇에 적힌 값을 출력한다.

<br>

### Reference
- 실제 값이 아님 참조 주소를 변수에 할당하는 Type
- Object가 해당(Object, Array, Function ...)
#### **Reference 비유 설명**
변수가 포스트잇이라 생각했을 때, **Reference** 타입은 포스트잇에는 실제 값이 저장된 위치를 적고, 실제 값들은 다른 곳에 저장해 두는 것이라 생각하면 됩니다.

#### **예시 코드**
```jsx
const list1 = [ 1, 2, 3 ];
const list2 = [ 1, 2, 3 ];

const result = list1 === list2;

console.log(result); // ?
```
#### **예시 코드 해석**
- `const list1 = [ 1, 2, 3 ];` <br>
  : 포스트잇1에 해당 정보가 저장된 위치를 적는다.(위치1)
- `const list2 = [ 1, 2, 3 ];` <br>
  : 포스트잇2에 해당 정보가 저장된 위치를 적는다.(위치2)
- `const result = list1 === list2;` <br>
  : 포스트잇1과 2에 적힌 내용을 비교한다.(`위치1 === 위치2` ???)
- `console.log(result);` <br>
  : 비교한 결과를 출력한다. (`False`)

#### **예시 코드2**
```jsx
const person1 = {
  age: 10
};
const person2 = person1;

person1.age = 20;

console.log(person2); // ?
```
#### **예시 코드2 해석**
- `const person1 = {age: 10};` <br>
  : person1 포스트잇에 어떤 정보가 담긴 위치를 적는다.(위치1)
- `const person2 = person1;` <br>
  : person2 포스트잇에 person1 포스트잇에 적힌 정보를 적는다.(위치1)
- `person1.age = 20;` <br>
  : person1 포스트잇이 가르키는 정보를 수정한다.
- `console.log(person2);` <br>
  : person2 포스트잇에 적힌 위치정보가 가르키는 정보를 출력한다.(위치1)

> [**Reference 추가 예제 설명**](https://github.com/kimcno3/vanillaCoding/blob/main/step5/javascript_koans.md#reference)

<br>

## 일반 변수와 참조 변수
### 두 변수의 차이점
- 기본 타입을 변수에 할당하면 일반 변수, 객체를 변수에 할당하면 참조 변수가 된다.
- 배열도 객체이기 때문에 변수에 할당하면 참조 변수가 된다.
- 다시 말해
    - 문자열, 숫자 등을 변수에 할당하면 일반 변수
    - 객체, 배열을 변수에 할당하면 참조 변수


### 값 전달 변수(call by value) 와 참조 전달 변수(call by reference)
- 값 전달 변수는 함수 내부에서 값을 바꿔도 외부에서는 그대로다. (immutable)
- 변수에 값을 재할당하지 않는 이상 함수에서는 바뀌지 않는다.
- 참조 전달 변수는 함수 내부에서 값을 바꾸면 외부의 객체도 값이 바뀝니다. (mutable)

<br>

## 배열(Array)
### 배열이란?
- 배열(array)는 자바스크립트에서 가장 많이 사용하는 자료구조 종류 중 하나
- 주로 같은 종류의 값을 여러개 묶어서 저장
- 배열은 '객체'이다.

### 배열 생성 방법
배열의 Literal은 다음과 같습니다.
> [Literal 상세 설명](https://github.com/kimcno3/vanillaCoding/blob/main/step5/javascript_koans.md#%EB%B0%B0%EC%97%B4-literals)

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
<br> **배열**: Mutable
<br> **문자열**: Immutable

> [Mutable 상세 설명](https://github.com/kimcno3/vanillaCoding/blob/main/step5/javascript_koans.md#pushpin-mutable)

```jsx
// 배열의 속성과 메소드를 문자열에도 테스트

// 배열 선언
var arr = ['h', 'e', 'l' , 'l', 'o'];
arr[0]; // 'h'

arr[0] = 'k';
console.log(arr); // ['k', 'e', 'l' , 'l', 'o'], 값이 변한다.

// 문자열 선언
var string = 'hello';
string[0]; // 'h'

string[0]; = 'k';
console.log(string); // 'hello' , 값이 변하지 않는다. 
```
> **결론 : 문자열은 배열과 달리 원하는 인덱스값만 바꿀 수 없다.**

<br>

## 함수(Function)
### 함수 특징
return값이 있는 함수를 호출하는 경우, 변수에 값을 할당하기 위해 사용한다.
```jsx
var five = function() {
    return 5;
}

var n = five(); // 변수 n에 return값 5 할당
console.log(n); // 5
```
<br>

return값이 없는 함수를 변수에 할당하면 undefined값이 된다.
```jsx
var foo = function() {
    console.log(5);
}

var n = foo();
console.log(n); // undefined
```
<br>

값이 없는 return은 해당 함수를 종료시키는 역할을 합니다.<br>
(반복문에서 break와 비슷한 기능)
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

### 함수 오버라이딩(Overriding)
- 상위 Scope에서 선언한 변수 또는 메소드를 자식 Scope에서 재선언하여 사용하는 것을 의미합니다.
- 오버라이딩된 변수, 메소드는 하위 Scope 안에서만 유효하고 상위 Scope에서는 유효하지 않습니다.
> [자바스크립트 오버라이딩 상세 설명](https://beomy.tistory.com/5)

#### **예제**
```jsx
// 전역변수 선언
var message = "Outer";

// 전역변수 return
function getMessage() {
    return message;
}

// 오버라이딩
function overrideMessage() {
    var message = "Inner";
    return message;
}

// 전역변수로 선언된 변수값 return
getMessage(); // log : "Outer"

// 오버라이딩한 변수값 return
overrideMessage(); // log : "Inner"

// 오버라이딩 아후 다시 변수값을 출력해보면 바뀌어 있지 않습니다.(오버라이딩하는 함수 내에서만 변경내용 유효)
message // log : "Outer"
```

<br>

만약 오버라이딩이 아니라 함수 실행시 전역변수를 재할당하는 경우, Global Scope에서도 재할당된 변수값이 유효합니다.
```jsx
// 전역변수 선언
var message = "Outer";

// 전역변수 return
function getMessage() {
    return message;
}

// 오버라이딩
function overrideMessage() {
    message = "Inner"; // 전역변수 자체를 재할당
    return message;
}

overrideMessage() // 함수 실행 -> 전역변수 재할당

message // log : "Inner"
```

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
- `this` 키워드 : 메소드 안에서 사용시 함수를 소유한 객체를 가르킨다.
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
    <br>

 - **JSON** 표기법 활용 객체 생성 <br>
  **JSON**이란, 서버에 저장되는 데이터의 표준 포맷 양식 , {키:값} 형태를 의미합니다.
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
<br>

### **`in` Keyword**
-  `in` 연산자는 명시된 속성이 명시된 객체에 존재하면 `true`를 반환합니다.
- 기본 형태 : `속성명 in 객체명`

> [in 연산자 상세 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/in)

#### **예제**
```jsx
// 객체 생성
var megalomaniac;

megalomaniac = {
    mastermind: "The Monarch",
    henchwoman: "Dr Girlfriend",
    theBomb: true
};

// 해당 객체에 속성이 존재하면 true
var hasBomb = "theBomb" in megalomaniac;

hasBomb; // log : true

// 해당 객체에 속성이 없으면 false
var hasDetonator = "theDetonator" in megalomaniac;

hasDetonator; // log : false
```

<br>

### **속성 추가(add) & 삭제(delete)**
- **속성 추가** : 객체에 새로운 속성 선언
- **속성 삭제** : `delete` 연산자 활용
> [delete 연산자 상세 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/delete)

#### **예제**
```jsx
// 객체 생성
var megalomaniac = { mastermind : "Agent Smith", henchman: "Agent Smith" };

// 속성 존재 여부 파악
"secretary" in megalomaniac; // log : false

// 없는 속성을 객체에 추가
megalomaniac.secretary = "Agent Smith";
"secretary" in megalomaniac; // log : true

// 기존에 존재하던 속성 삭제
delete megalomaniac.henchman;
"henchman" in megalomaniac; // log : false
```

<br>

## 객체 생성자(Object Constructor)
### 객체 생성자란?
자바스크립트에서는 객체를 만들어내는 기능을 수행하는 함수를 의미
> 자바스크립트는 Class 기반이 아닌 Prototype 기반의 프로그래밍 언어
>
> 객체를 정의하는 Class가 없기 때문에 이를 대체할 객체 생성자 함수를 선언해야 한다.
### 예시
```jsx
// human(), food() 함수가 바로 객체 생성자 함수
// JAVA에서 Class와 같은 역할
var human = function(name, hp, power){
    this.name = name;
    this.hp = hp;
    this.power = power;
    this.attack = function(target) {
        target.hp -= this.power;
        console.log(this.name + '이 ' + target.name + '을 공격했습니다.')
    }
    this.eat = function(food) {
        this.hp += food.energy;
        console.log(this.name + '이 ' + food.name + '을 먹었습니다.')
    }
}
var food = function(name, energy){
    this.name = name;
    this.energy = energy;
}

// p1, p2, f1는 객체, 인스턴스라고 한다.(참조변수라고 한다.)
var p1 = new human('kim', 100, 10);
var p2 = new human('lee', 200, 20);
var f1 = new food('donut', 10);


p1.attack(p2);
p2; // p2.hp가 p1.power만큼 감소

p2.eat(f1);
p2; // p2.hp가 f1.energy만큼 증가
```

<br>

## 프로토타입(Prototype)
### 프로토타입이란?
- 생성자로 만든 객체는 프로토타입이라는 속성을 가집니다.
- 프로토타입을 활용하면 메모리를 절약하고 효율적으로 객체의 메소드를 생성할 수 있다.

### 예시
```jsx
// 객체 생성자
function Human(name, hp, mp, power) {
  this.name = name;
  this.hp = hp;
  this.mp = mp;
  this.power = power;
}
// 프로토타입을 활용한 메소드 정의
Human.prototype.attack = function(target) {
    target.hp -= this.power;
};

//  Human의 객체를 100개 생성한다고 가정할 때, 각각의 객체가 모두 같은 기능을 하는 함수에 대한 메모리를 차지하게 된다.
//  이를 프로토 타입을 통해 하나의 메모리 공간으로 같은 함수을 참조하여 활용할 수 있다.
//  메모리 절약 효과 극대화
```
> 참고자료 : https://medium.com/@bluesh55/javascript-prototype-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-f8e67c286b67

<br>

## DOM(Document Object Model)
### DOM이란? ([MDN 정의](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction))
- HTML 문서를 계층 구조로 표현한 프로그래밍 인터페이스
    - 브라우저는 HTML 문서의 요소들을 통해 계층구조의 DOM을 생성하고 화면에 출력(렌더링)한다.
    - DOM은 사용자가 JS를 사용해 웹화면을 추가, 수정, 삭제할 수 있는 표면같은(인터페이스) 역할을 한다.
    - 즉, JS가 DOM을 수정하는 것이고 HTML 문서 자체는 수정되지 않는다.

- 표준: W3CDOM
- 구현체: Gecko, Webkit 등

> **DOM에 대한 추가 설명** <br>
> - [유노코딩님 영상](https://www.youtube.com/watch?v=zyz1eJJjsNE) <br>
> - [바닐라코딩 사전가이드](https://book.vanillacoding.co/starter-kit/step-4/interacting-with-webpages/dom-introduction)

### html 객체
- HTML 문서도 객체로 간주된다.
- window: 최상위 객체
- document: dom의 최상위 객체이면서 window의 하위 객체

    ```html
    <!-- HTML 파일 -->
    <!DOCTYPE html>
    <html>
        <head>
            <title>HTML Tutorial</title>
        </head>
        <body>
            <script src = 'dom.js'></script>

            <h1>This is a heading</h1>
            <h1>Another h1 heading</h1>
            <p id='main'>This is a paragraph.</p>
        </body>
    </html>
    ```

    ```jsx
    // js 파일
    var list = document.getElementsByTagName('h1'); // h1태그들의 코드를 배열에 원소로 저장

    list[0].innerHTML; // 'This is a heading' , 태그 안에 있는 텍스트
    list[0].innerHTML = "Hello"; // 텍스트 변경

    var list = document.getElementById('main'); // id가 main인 태그를 지정하여 배열에 선언
    main.innerHTML = "Hello"; // 텍스트 변경
    ```

### JS로 DOM 제어하기
- 모든 HTML 엘리먼트는 객체이므로 다른 객체와 마찬가지로 JS로 제어가 가능하다.

### DOM 객체의 값 바꾸기
```jsx
var element = document.getElementById('test')
element.innerHTML = '값'
<h2>My First Page</h2>
<p id="test"></p>
```

<br>

## 스코프(Scope)
### Scope란?
우리가 작성하는 코드의 **접근 범위**를 결정하는 개념을 의미합니다.

### 함수 스코프(Function Scope)
```jsx
function foo () {
  /* --- foo scope start --- */
  var a = 1;

  console.log(a); // 로그 #1
  /* --- foo scope end   --- */
}

foo();
```
`로그 #1`에서는 `a` 라는 변수의 값(1)이 성공적으로 출력됩니다.

그 이유는 자바스크립트에서 `var` 를 이용하여 선언한 변수는 **해당 변수 선언문을 감싸고 있는 함수를 기준으로 접근 범위가 설정되고 그 범위 내부에서는 자유롭게 접근하여 사용할 수 있기 때문**입니다.

위 예제 코드에서 **"foo scope start"** 부분부터 **"foo scope end"** 부분 내에서는 언제든지 자유롭게 `a` 라는 변수에 접근하여 사용이 가능한 것입니다. 이 부분을 우리는 `foo` 함수 Scope라고 부를 수 있습니다.

### Scope Chain
- Scope는 아래 그림처럼 계층 구조로 형성됩니다.
- 가장 최상위 Scope는 `Global Scope`라고 부릅니다.
- `Global Scope` 하위에는 함수 생성을 기준으로 `하위 Scope`가 형성됩니다.
- [**상위**] `Global Scope` -> `Person Scope` -> `displayName Scope` [**하위**]

![https://www.learnsimpli.com/scope-chain-in-javascript/
](https://book.vanillacoding.co/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-M-IhZy_qTGIqJrZSYiJ%2F-Me9-xqRQj7kQET48S-y%2F-Me93WPy0wKVw3DQtdHz%2F3-2.png?alt=media&token=06a45e40-d4aa-4767-a027-e6981c4e8f0d)
참고 그림(https://www.learnsimpli.com/scope-chain-in-javascript/)

### Scope 계층에서 가장 중요한 특징
- 상위에서 하위 Scope 내부 정보를 접근할 수 없다.
- 반대로 하위에서 상위 Scope의 정보는 접근 가능합니다.
- 실행문의 위치를 기준으로 하위 Scope부터 시작하여 원하는 값을 찾을때까지 상위로 탐색합니다.

### 예제1
```jsx
var a = 1;

function foo () {
  var a = 2;
  console.log(a); // 로그 #1
}

foo();
```
**로그 #1**에는 **2**가 찍혀 나옵니다.

- 그 이유는 어떤 변수에 대한 정보를 필요로 할 때, 자바스크립트는 **현 실행문의 위치를 기준**으로 하위 Scope부터 시작하여 해당 변수의 값을 찾아나갑니다.
- `foo` 함수 Scope 탐색 결과 a라는 변수에 2가 할당되어 있기 때문에 해당 값을 출력하게 되는 것입니다.

### 예제2
```jsx
var a = 1;

function foo () {
  var a = 2;
  console.log(a); // 로그 #1
}

foo();
console.log(a);   // 로그 #2
```
**로그 #1**에는 2가 출력됩니다.
- 그 이유는 예제1과 같은 이유입니다.

**로그 #2**에는 1이 출력됩니다.
- 그 이유는 로그 #2가 출력되는 실행문의 위치가 Global Scope이기에 그 하위 Scope에는 접근할 수 없습니다. 그러므로 같은 Global Scope에서 선언된 a값을 찾은 결과로 1이 출력되는 것입니다.

### 예제3
```jsx
function foo () {
  var a = 2;
  console.log(a); // 로그 #1
}

foo();
console.log(a);   // 로그 #2
```
**로그 #1**에는 2가 출력됩니다.
- 그 이유는 예제1과 같은 이유입니다.

**로그 #2**에는 에러가 납니다.("a is not defined")
- 그 이유는 `Global Scope`에서 선언된 변수 `a`가 없기 때문입니다.
- 만약 상위 Scope가 존재했다면, `상위 Scope에서 같은 변수를 탐색`했을 것이고, 같은 원리로 가장 높은 Scope(`Global Scope`)까지 변수 a의 존재 여부를 탐색하게 됩니다.
- 위와 같은 과정 중간에 원하는 정보를 찾았다면 탐색을 멈춥니다.

### Global Scope
```html
<html>
  <head>
    <title>Global Scope Sample</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <script>
      var a = '바닐라코딩';

      console.log(`우리는 ${a}입니다.`); //로그 #1

      setTimeout(function () {
        console.log(`[1초 후] 우리는 ${a}입니다.`); //로그 #2
      }, 1000);
    </script>
    <script>
      var a = '느린캠퍼스';

      console.log(`우리는 ${a}입니다.`); //로그 #3
    </script>
  </body>
</html>
```
#### **실행 결과**
```jsx
우리는 바닐라코딩입니다. // 로그 #1
우리는 느린캠퍼스입니다. // 로그 #3
[1초 후] 우리는 느린캠퍼스입니다. // 로그 #2

`로그 #3`보다 `로그 #2`가 더 늦게 실행되면서 변수 a에 할당된 값이 다른 `Script`에서 할당된 값이 출력됩니다.
```
결국 `Global Scope`에서 선언된 변수는 **하나의 공용공간**으로 이해하면 좋습니다.

즉, 하나의 HTML문서에는 하나의 `Global Scope`가 존재하고, 이 공간에서 선언된 변수는 여러 `script`에서 사용가능하단 의미가 됩니다.

우리가 어떤 물건을 **공용공간**(`Global Scope`)에 배치해둔다면, 다른 누군가가 그 물건을 사용할 수도 있고 혹은 **수정/삭제**할 가능성도 있습니다.

**물론 절대 사용하면 안된다는 의미는 아닙니다.** 필요하다면 반드시 사용해야 하지만, 주의를 기울여 신중하게 사용해야만 합니다.

<br>

### **렉시컬 스코핑(lexical scoping)**
-  **함수를 어디에 선언했는지**에 따라 Scope가 결정되는 방식
- 반대로 **어디서 호출되었는지**에 따라 Scope가 결정되는 방식을 **Dynamic scoping** 이라고 합니다.
> [스코핑 상세설명](https://im-developer.tistory.com/63)

> [예시문제 설명 링크](https://github.com/kimcno3/vanillaCoding/blob/main/step5/javascript_koans.md#%EB%A0%89%EC%8B%9C%EC%BB%AC-%EC%8A%A4%EC%BD%94%ED%95%91lexical-scoping)

<br>

## 호이스팅(Hoisting)
### 호이스팅이란?
- 우리가 작성하는 모든 변수 선언문을 해당 코드가 속한 스코프 내에서 최상위로 끌어올려진 상태로 실행하는 것을 의미합니다.
- 코드가 실행되기 전에 진행되는 전처리 작업 중 하나입니다.
- 중요한 부분은 **"변수 선언문"** 만 끌어올려진다는 점입니다. 변수에 값을 대입 혹은 할당하는 구문은 우리가 실제로 작성한 흐름과 같이 실행됩니다.

### **예제1**
```jsx
console.log(a);
var a = 1;
```
**위와 같은 코드도 실제 구동 흐름은 아래와 같습니다.**
```jsx
var a; // 변수 선언문만 해당 스코프내 가장 처음으로 실행시킨다.
console.log(a);
a = 1;
```

### **예제2**
```jsx
var a = 1;

function foo () {
  console.log(a);
  var a = 2;
}

foo();
```
위 예제의 경우도 실제 구동 흐름은 아래와 같습니다.
```jsx
var a = 1;

function foo () {
  var a;
  console.log(a);
  a = 2;
}

foo();
```
함수 scope 안에서 변수 선언문만 가장 먼저 실행되었기 때문에 `"undifined"`가 출력되는 것입니다.

### **함수 표현식(Function Expression)**
```jsx
d(); // 함수 #1

var d = function () {
  console.log('I am inside function d');
};

d();  // 함수 #1
```
함수도 변수에 대입할 경우 같은 원리의 호이스팅이 적용됩니다.

그래서 위의 코드에서는 아래와 같은 결과를 가지게 됩니다.
- 함수 #1 실행 결과 : Error(d is not a function) -> 변수에 함수가 할당X
- 함수 #2 실행 결과 : 함수 #1에서 에러발생으로 실행 X

### **함수 선언식(Function Declaration)**
```jsx
j(); // 함수 #1

function j () {
  console.log('j');
}

j(); // 함수 #2
```
함수 표현식과 다르게 함수 선언식을 활용하게 되면 함수 선언식이 호이스팅 되기 때문에 순서가 중요하지 않습니다.

그래서 위의 코드는 아래와 같은 결과를 가지게 됩니다.
- 함수 #1 실행 결과 : j
- 함수 #2 실행 결과 : j

<br>

## :pushpin: 참고 사이트]
- [자바스크립트 기초 강의 By 호눅스님](https://www.inflearn.com/course/javascript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-codesquad-masters_lv1)
- [바닐라코딩 사전가이드](https://book.vanillacoding.co/starter-kit/)
