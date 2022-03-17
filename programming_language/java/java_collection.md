## :pushpin: Collection Framework
`Collection FrameWork`는 다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미합니다.

`Collection Framework`의 구성요소는 자료구조에 따라 인터페이스로 구분하고, 이를 구체적인 클래스들로 구현되어 있습니다.

핵심 인터페이스는 다음과 같습니다.
- `List` : 순서가 있는 데이터 집합, 중복 허용
- `Set` : 순서가 없는 데이터 집합, 중복 혀용하지 않음
- `Map` : 키와 값으로 구분된 데이터 집합

이 중에서 `List`와 `Set`인터페이스는 같은 `Collection` 인터페이스를 상속받지만, `Map` 인터페이스는 자료 구조상 차이점으로 인해 별도로 정의되어 있습니다. 

![](https://blog.kakaocdn.net/dn/4wkUX/btq44bqazqr/80s6KaCrGqfETw4Pk5CGqK/img.png)
<br> 출처 : https://crazykim2.tistory.com/557

위 인터페이스들을 구현한 클래스는 다양하며 클래스마다 차이점이 존재합니다.

배열이 아닌 `Collection Framework`를 활용하는 이유는 배열의 크기를 정해두지 않고 활용하기 위해서(= 동적 메모리 할당)입니다.

> [참고사이트 1](http://www.tcpschool.com/java/java_collectionFramework_concept)

> [참고사이트 2](https://www.crocus.co.kr/1553)

> [참고사이트 3](https://crazykim2.tistory.com/557)