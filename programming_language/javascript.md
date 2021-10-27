# :pushpin: 목차
[includes()](#includes) <br>
[replace()](#replace) <br>
[isNAN()](#isNAN) <br>
[push() , pop()](#push--pop) <br>
[unshift() , shift()](#unshift--shift)


<br>

# **includes**()
문자열이 특정 문자열을 포함하는지 확인하는 메서드
```jsx 
.includes()
```

**searched_string** : 검색할 문자열로 필수 요소. 대소문자를 구분<br>
**start_index** : 검색을 시작할 index 값. 선택 요소. 값이 없으면 문자열 전체 대상 지정
```jsx
string.includes(searched_string, start_index)
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

# **replace**()
특정 문자열을 원하는 문자열로 바꿔주는 메서드
```jsx 
.replace()
```
**delete_string** :  삭제되는 문자열<br>
**new_string** : `delete_string` 대신 추가되는 문자열
```jsx
string.replace(delete_string, new_string)
```
**예시**
```jsx
let string = '010-1234-5678'
string.replace('-', '')

// replace 메서드는 제일 먼저 일치하는 문자열 하나만 바꿔준다.

// 결과 값 : 0101234-5678
```
- 모든 문자열을 한번에 교체하고 싶다면 **정규표현식**을 사용해야 한다.
    - **정규표현식**: 문자열에 나타나는 특정 문자 조합과 대응시키기 위해 사용되는 패턴

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

# **isNAN**()
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

# **push**() , **pop**()
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

# **unshift**() , **shift**()
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