## :pushpin: HashMap
### equals(), hashCode() 오버라이딩이 필수적인 이유
> `equals()`와 `hasCode()` 오버라이딩 관련 설명은 다음 [링크](https://github.com/kimcno3/TIL/blob/main/programming_language/java/java_equals_and_hashcode.md)를 참고하세요.

첫번째로 key를 객체로 이용할 경우, 논리적 동일함이 보장되지 않는다면 같아야할 key가 다르다고 인식되어 수정이 아닌 원치 않는 값의 추가가 될 수 있다.

그래서 두 메소드를 오버라이딩하여 논리적 동일함을 보장해야 의도에 맞는 key를 설정할 수 있다. 여기서 말한 논리적 동일함을 보장하는 방법이 자바에선 `equals()`와 `hashCode()`를 오버라이딩하는 것을 의미한다.

<br>

두번째 이유는 두 메소드의 오버라이딩은 해시충돌을 해결할 때에도 두 메소드의 재정의는 필수적이다.

해시 충돌이란 두개의 다른 객체를 키로 가져올 때, 두 객체가 다른 값을 가지고 있지만 계산된 해시값이 같아 같은 버캇을 가르키는 경우를 의미한다.

이런 경우에는 하나의 버킷이 두개의 값이 저장되어야 하는데 이를 해결하는 방법론은 큰 범주에서 두가지다.

1. `Opening Addrress` : 해당 버킷에 이미 데이터가 존재한다면, 메모리 내 다른 버킷에 데이터를 저장해두는 방법이다.

2. `Separate Chaining` : 추가적인 메모리를 할당해 해당 버킷과 `LinkedList` 타입으로 연결하여 저장한다.

자바에선 2번 Chaining 방법으로 해싱 충돌을 해결한다.

이렇게 같은 해시에 연결된 데이터를 다시 불러올 경우(`get()`), 키를 구별하기 위해 내부적으로 `equals()` 메소드가 사용된다. 이때 `equals()`가 오버라이딩 되어있다면 정확히 동일한 키를 구별하고 그에 대응하는 값을 가져올 수 있을 것이다.

<br>

> [참고사이트_Custom Key](http://www.gisdeveloper.co.kr/?p=5332)

> [참고사이트_equals()와 hashCode()](https://nesoy.github.io/articles/2018-06/Java-equals-hashcode)

> [참고사이트_해시 충돌](https://m.blog.naver.com/weplayicecream/221467971945)