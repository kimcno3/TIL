## :pushpin: Enum 클래스 추가설명
선언된 `enum 클래스`는 로딩 과정에서 `Method 영역`에 저장되며 각각의 상수들이 `public static final 필드`이자 `객체`로서 메모리를 할당받는다. Method 영역에 메모리를 할당받기 때문에 프로그램이 끝날 때가지 메모리에 존재한다.

그 다음, Method 영역에 저장된 각각의 상수 메모리에는 Heap 영역에 생성된 해당 상수들의 객체 메모리 주소가 저장된다. 

![](https://honbabzone.com/assets/images/post/java/emum-memory2.png)

stack에서 어느 상수에 대한 참조변수가 선언될 경우, 참조 변수에도 Method 영역의 상수 객체와 같은 메모리 주소가 저장된다.

![](https://honbabzone.com/assets/images/post/java/emum-memory3.png)

> 이미지 출처는 설명란 하단에 기재하였습니다.

**예제코드**
```java
public class Sample{
    public enum EnumName{
        // 각각의 상수가 하나의 필드이자 객체로 Method 영역에 저장
        PRIME_ONE,
        PRIME_TWO;
    }
    public static void main(String[] args){
        EnumName primeNumber = EnumName.PRIME_ONE;
        // primeNumber : 참조변수로 stack 영역에 저장, Heap 영역에 있는 PRIME_ONE 객체의 메모리 주소 할당
        // EnumName.PRIME_ONE; : EnumName 클래스의 PRIME_ONE 필드(클래스변수이므로 객체 선언 X)
    }
}
```

<br>

또한 각 상수 선언시, 각 상수에 대응하는 생성자 매개변수를 지정할 수 있고, 생성자는 `private` 또는 `package-protect`로 선언할 수 있다.

**예제코드2**
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
        EnumName primeNumber = EnumName.PRIME_ONE; // 객체 생성시 인스턴스변수값도 함께 Heap 영역에 저장
        System.out.println(primeNumber.number);
    }
}
```
출력된 값은 상수인 `PRIME_ONE` 객체의 인스턴스 변수인 `number`의 값이라고 할 수 있다.

> [참고사이트](https://seeminglyjs.tistory.com/257)

> [참고사이트(이미지 출처)](https://honbabzone.com/java/java-enum/#enum-%EC%B6%94%EA%B0%80-%EC%86%8D%EC%84%B1%EA%B3%BC-%EC%83%9D%EC%84%B1%EC%9E%90)