# :pushpin: 자바의 신 정리
> 상세 내용은 책을 구매하셔서 확인하시기 바랍니다.

<br>

## :pushpin: 목차
**:pushpin: Volume 1**
- [:pushpin: Chapter1](#pushpin-Chapter1)


## :pushpin: Chapter1
> 프로그래밍이란 무엇인가?

### 직접해 봅시다.
빼기, 곱하기, 나누기 메소드 생성해보기.
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
> [링크](https://docs.google.com/forms/d/e/1FAIpQLSeF0UY6gNGiFqK3bCueSrczI7QVjh2zFylg7o3DB5UKIX-C-Q/viewform?c=0&w=1)