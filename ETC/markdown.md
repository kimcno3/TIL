# :pushpin: **목차**
- [Markdown이란?](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#pushpinmarkdown%EC%9D%B4%EB%9E%80)
- [Markdown 기본 문법](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#pushpinmarkdown-%EA%B8%B0%EB%B3%B8-%EB%AC%B8%EB%B2%95)
    - [1. Headers](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#1-headers)
    - [2. 줄바꿈](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#2-%EC%A4%84%EB%B0%94%EA%BF%88)
    - [3. 텍스트 강조](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#3-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EA%B0%95%EC%A1%B0)
    - [4. 수평선](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#4-%EC%88%98%ED%8F%89%EC%84%A0)
    - [5. 인용](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#5-%EC%9D%B8%EC%9A%A9)
    - [6. 링크](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#6-%EB%A7%81%ED%81%AC)
    - [7. 목록](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#7-%EB%AA%A9%EB%A1%9D)
    - [8. 코드](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#8-%EC%BD%94%EB%93%9C)
    - [9. 이미지](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#9-%EC%9D%B4%EB%AF%B8%EC%A7%80)
    - [10. 테이블](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#10-%ED%85%8C%EC%9D%B4%EB%B8%94)
    - [참고자료](https://github.com/kimcno3/TIL/blob/main/ETC/markdown.md#%EC%B0%B8%EA%B3%A0%EC%9E%90%EB%A3%8C)

</br>

# :pushpin:**Markdown이란?**
[**마크다운(markdown)**](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4)은 일반 텍스트 기반의 경량 마크업 언어다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다. HTML과 리치 텍스트(RTF) 등 서식 문서로 쉽게 변환되기 때문에 응용 소프트웨어와 함께 배포되는 README 파일이나 온라인 게시물 등에 많이 사용된다.

</br>

# :pushpin:**Markdown 기본 문법**
## **1. Headers**
- H1 ~ H6까지 지원
- 문장 앞에 # 부터 ###### 까지 원하는 크기에 맞는 # 개수를 입력
- H1의 경우 수평선 자동 추가

### **예시 코드**
```md
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

### **실행 결과**
> # H1
> ## H2
> ### H3
> #### H4
> ##### H5
> ###### H6

</br>

***

</br>

## **2. 줄바꿈**
- `</br>` 명령어 활용
- 띄어쓰기 3번 활용

### **예시코드**
```
줄바꿈을 하고 싶다면 
</br>
이렇게 하면 됩니다.
```
```
줄바꿈을 하고 싶다면(띄어쓰기 3번)   
이렇게 하면 됩니다.
```
### **실행 결과**
>줄바꿈을 하고 싶다면 
></br>
>이렇게 하면 됩니다.

>줄바꿈을 하고 싶다면   
>이렇게 하면 됩니다.

</br>

***

</br>

## **3. 텍스트 강조**
- **볼드체**
    - 원하는 글자 앞뒤에 ** 또는 __ 추가

</br>

- *이텔릭체*
    - 원하는 글자 앞뒤에 * 또는 _ 추가

</br>

- ~~캔슬라인~~
    - 원하는 글자 앞뒤에 ~~ 추가 
### **예시코드**

```
**볼드체를 원한다면**
__볼드체를 원한다면__

*이탤릭체를 원한다면*
_이탤릭체를 원한다면_

~~캔슬라인을 원한다면~~
```
### **실행 결과**
> **볼드체를 원한다면**
>
> __볼드체를 원한다면__

> *이탤릭체를 원한다면*
>
>_이탤릭체를 원한다면_

> ~~캔슬라인을 원한다면~~

</br>

***

</br>

## **4. 수평선**
- *을(를) 세개 이상 붙혀서 사용
- -을(를) 세개 이상 붙혀서 사용
- (*) or (-) 사이사이에 띄어쓰기를 하더라도 세개 이상만 쓰면 수평선이 만들어진다.
### **예시코드**
```md
***
****
*****
* * * 
---
----
-----
- - -
```
### **실행결과**
> ***
> ****
> *****
> * * *
> ---
> ----
> -----
> - - -

</br>

***

</br>

## **5. 인용**
- 원하는 문장 앞에 `>` 추가
### **예시코드**
```md
> 이 문장은 인용글입니다.
```
### **실행결과**
> 이 문장은 인용글입니다.

</br>

***

</br>

## **6. 링크**
- `[링크걸고싶은 문장](해당 URL)`을 사용하면 링크 사용 가능
### **예시코드**
```
[kimcno3 Github 주소](https://github.com/kimcno3)
```
### **실행결과**
> [kimcno3 Github 주소](https://github.com/kimcno3)

</br>

***

</br>

## **7. 목록**
- **순서없는 목록** : `-` , `*` , `+` 사용
- **순서있는 목록** : `'1.'` , `'2.'` , `'3.'` … 사용
- 순서 없는 목록의 경우, Tab키(들여쓰기)를 사용하면 모양이 자동으로 변경
### **예시코드**
```
- 이것은
* 순서없는
+ 목록
```
```
- 들여쓰기를
    - 사용하면
        - 이런 모양
```
```
1. 이것은
2. 순서있는
3. 목록
```
```
1. 들여쓰기를 
    2. 사용하면
        3. 이런 모양
```
### **실행결과**
> - 이것은
> * 순서없는
> + 목록

> - 들여쓰기를
>   - 사용하면
>        - 이런 모양

> 1. 이것은
> 2. 순서있는
> 3. 목록

> 1. 들여쓰기를 
>   2. 사용하면
>       3. 이런 모양

</br>

***

</br>

## **8. 코드**
- Backtick키(`)를 앞뒤로 1개씩 사용하면 원하는 단어만 코드블럭 가능
- Backtick키(`)를 앞뒤로 3개씩 사용하면 원하는 문장을 코드블럭 가능
- 한줄 띄어쓰기와 들여쓰기를 통해 원하는 문장을 코드블럭 가능
    - 들여쓰기를 하지 않은 문장을 만날 때까지 코드블럭 생성
### **예시코드**
```
`이 단어만` 코드블럭
```
    ```
    이 문장 전체를 코드블럭
    ```

```
띄어쓰기 전 문장
(공백)
    (들여쓰기)코드블럭
코드블럭 다음 문장
```

### **실행결과**
`이 단어만` 코드블럭
***
```
이 문장 전체를 코드블럭
```
***
띄어쓰기 전 문장
 <!-- (공백) -->
    (들여쓰기)코드블럭
 코드블럭 다음 문장

</br>

***

</br>

## **9. 이미지**
- ![이미지 설명](이미지 Url)로 이미지 추가 가능

### **예시코드**
```
![Desney](https://images.unsplash.com/photo-1463109598173-3864231fade5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1546&q=80)
```
### **실행결과**
![Desney](https://images.unsplash.com/photo-1463109598173-3864231fade5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1546&q=80)

</br>

***

</br>

## **10. 테이블**
- `|`키를 사용해서 열(column)을 추가 
- 두번째 행에 `|--|`를 추가해야 테이블 생성
- 행(row)추가는 다음 문장에 열 수에 맞춰서 동일하게 `|` 사용
- `|--|` 에 `:`을 사용하여 좌, 우, 가운데 정렬 가능(기본값은 좌측 정렬  )
    - `|:--|` : 좌측 정렬 / `|--:|` : 우측 정렬 / `|:--:|` : 가운데정렬

### **예시코드**
```
정렬X

|이름|나이|거주지|
|--|--|--|
|김OO|26|이천시 OOO-OO로 OOO동 OOO호|
|이OO|23|강릉시 OO로 OO동 OO호|
|박OO|28|담양군 OO로 OO-O 번지|
```
```
좌측 정렬

|이름|나이|거주지|
|:--|:--|:--|
|김OO|26|이천시 OOO-OO로 OOO동 OOO호|
|이OO|23|강릉시 OO로 OO동 OO호|
|박OO|28|담양군 OO로 OO-O 번지|
```
```
우측 정렬

|이름|나이|거주지|
|--:|--:|--:|
|김OO|26|이천시 OOO-OO로 OOO동 OOO호|
|이OO|23|강릉시 OO로 OO동 OO호|
|박OO|28|담양군 OO로 OO-O 번지|
```
```
가운데 정렬

|이름|나이|거주지|
|:--:|:--:|:--:|
|김OO|26|이천시 OOO-OO로 OOO동 OOO호|
|이OO|23|강릉시OO로 OO동 OO호|
|박OO|28|담양군OO로 OO-O 번지|
```
### **실행결과**
> **정렬 X**
>
> |이름|나이|거주지|
> |--|--|--|
> |김OO|26|이천시 OOO-OO로 OOO동 OOO호|
> |이OO|23|강릉시 OO로 OO동 OO호|
> |박OO|28|담양군 OO로 OO-O 번지|

> **좌측 정렬**
>
> |이름|나이|거주지|
> |:--|:--|:--|
> |김OO|26|이천시 OOO-OO로 OOO동 OOO호|
> |이OO|23|강릉시 OO로 OO동 OO호|
> |박OO|28|담양군 OO로 OO-O 번지|

>**우측 정렬**
>
> |이름|나이|거주지|
> |--:|--:|--:|
> |김OO|26|이천시 OOO-OO로 OOO동 OOO호|
> |이OO|23|강릉시 OO로 OO동 OO호|
> |박OO|28|담양군 OO로 OO-O 번지|

> **가운데 정렬**
>
> |이름|나이|거주지|
> |:--:|:--:|:--:|
> |김OO|26|이천시 OOO-OO로 OOO동 OOO호|
> |이OO|23|강릉시OO로 OO동 OO호|
> |박OO|28|담양군OO로 OO-O 번지|

</br>

***

</br>

## **참고자료**

[위키백과 마크다운 정의](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4   
)

[마크다운 6분 정의(드림코드 by 엘리)](https://www.youtube.com/watch?v=kMEb_BzyUqk)

[김지현(ihoneymon
) 님 Github 저장소](https://gist.github.com/ihoneymon/652be052a0727ad59601#file-how-to-write-by-markdown-md)

[박시홍(hongsii) 님 블로그](https://hongsii.github.io/2017/06/01/How-to-Write-with-Markdown/)