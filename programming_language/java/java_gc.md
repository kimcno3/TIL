# :pushpin: GC

## GC란?
GC(Garbage Collector, 가비지 콜렉터)는 JVM 내에서 불필요한 메모리를 차지하는 객체를 자동으로 식별하여 삭제해주는 기능을 의미한다. 여기서 말하는 메모리는 힙영역을 의미한다.

## GC Heap 영역 구조
![](https://t1.daumcdn.net/cfile/tistory/99D6FE4C5C6710AF0B)<br>
출처 : [링크](https://kamang-it.tistory.com/entry/Java%EC%97%90%EC%84%9C%EC%9D%98-%EA%B0%80%EB%B9%84%EC%A7%80%EC%BB%AC%EB%A0%89%ED%84%B0Garbage-CollectorGC%EB%8F%8C%EC%95%84%EA%B0%80%EB%8A%94-%EC%9B%90%EB%A6%AC-%ED%8C%8C%ED%95%B4%EC%B9%98%EA%B8%B0)

- `young` :` Minor GC`가 일어나며 비교적 방금 생성된 객체들이 저장되는 공간으로 적은 메모리를 차지한다.
    - `eden` : 객체가 새로 생겨나면 저장되는 공간으로 `eden`영역의 메모리가 다 차면 사용하는 객체는 `s0`로 넘기고 그 외 객체는 삭제한다.
    - `s0` : `eden` 영역에서 넘어온 객체들이 저장되며, 동일한 원리로 메모리가 가득 차면 살아남은 객체만 `s1`으로 넘긴다.
    - `s1` : `s0`에서 넘어온 객체가 저장되며, 메모리가 가득차면 일정 기준 이상의 객체만 `old`로 넘긴다.

- `old` : `Major GC`가 발생하며 특정 횟수 이상을 살아남은 객체가 저장되며 발생하는 곳이고 많은 메모리를 차지한다.

<br>

## Minor & Major GC
JVM의 힙영역은 설계될 때 다음과 같은 두가지 전제를 가지고 설계되었다.
1. 대부분의 객체는 금방 접근 불가능한 상태(Unreachable)가 된다.
2. 오래된 객체가 새로 생성된 객체를 참조하는 경우는 매우 드물다.

즉, 방금 생성된 객체가 저장되는 공간(young 영역)과 오래 살아남을 객체가 저장된 공간(old 영역)을 분리시키고 오래 살아남은 객체에 대한 불필요한 신경은 줄이며 새로 생겨나고 없어질 객체에 집중하기 위한 설계라고 볼 수 있다.

그래서 young 영역의 메모리가 가득 찼을 때, 이를 비우는 작업을 `Minor GC`라고 하며, <br>
old 영역이 가득 찼을 때 발생하는 GC를 `Major GC`라고 한다.

<br>

## GC의 작동 원리
### Stop the World
말 그대로 세상이 멈춘다. 즉, GC가 작동하면 JVM 자체가 작동을 멈추게 된다. 

이는 GC가 하는 작업이 객체를 삭제하는 작업이기 때문에 멀티 쓰레드가 작동하는 환경속에서 이미 삭제한 객체를 필요로 하는 쓰레드가 생겨나는 불상사를 방지하기 위한 설계라고 보여진다.(개인적인 견해)

하지만 이렇게 JVM을 중지시키는 시간이 길어지면 프로그램 성능에 매우 치명적으로 작용될 수 있다. 하지만 GC의 작업은 메모리 측면에서 필수적으로 필요하다.

그렇기 때문에 프로그램 성능의 차이가 느껴지지 않을 만큼 적은 메모리에 대해 자주 GC를 작동시켜 메모리를 관리하는 방법을 JVM은 채택하고 있으며, 이것이 `Minor GC`다. 그래서 young 영역은 상대적으로 적은 메모리를 차지한다. 그래야 GC가 작동하는 시간이 짧아지기 때문이다.

반대로 `Major GC`가 발생하는 old 영역은 많은 메모리를 차지하고 있어 한번 GC가 발생하면 긴 시간동안 JVM의 작동이 멈춰야 하는 위험이 있다. 그래서 위에서 말한 전제처럼 별로 쓰이지도 않고 오래 살아남은 객체들에게 메모리를 많이 할당하여 GC의 작동을 거의 하지 않도록 설계된 것이다.

<br>

### Mark and Sweep
그러면 객체를 삭제할 것인지 계속 저장해둘 것인지를 정하는 기준은 무엇일까?

계속 사용할 객체를 `Reachable` 이라고 하며, 그렇지 않고 GC의 대상이 되는 객체를 `Unreachable` 이라고 표현한다. 그대로 번역하면 `접근가능한 객체` 또는 `접근할 수 없는 객체` 라는 뜻이다.
- Reachable : 접근 가능한 객체
- Unreachable : 접근 불가능한 객체

자바에서 힙 영역에 저장되는 객체들 중 `Root Set`이 되는 객체가 있다. 그리고 이 `Root Set` 객체를 기준으로 상속이나 참조하고 있는 다른 객체들이 연결되어 있는 구조로 저장된다.

![](https://media.vlpt.us/images/recordsbeat/post/40b78c47-247d-428b-a482-065116b2d6c2/0_-dB_3FTm5N-5kjN6.gif)<br>
출처 : [링크](https://velog.io/@recordsbeat/Garbage-Collector-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EA%B8%B0#reference-counting--mark-and-sweep)

GC는 이러한 `Root Set`부터 연결된 객체들을 순회하며 `Mark`를 하고 `Mark`가 되지 않는 객체는 더 이상 Stack이나 Method 영역에서 참조하지 않는다고 판단하여 GC의 대상으로 간주(`Sweep`)한다.


> [참고사이트](https://kamang-it.tistory.com/entry/Java%EC%97%90%EC%84%9C%EC%9D%98-%EA%B0%80%EB%B9%84%EC%A7%80%EC%BB%AC%EB%A0%89%ED%84%B0Garbage-CollectorGC%EB%8F%8C%EC%95%84%EA%B0%80%EB%8A%94-%EC%9B%90%EB%A6%AC-%ED%8C%8C%ED%95%B4%EC%B9%98%EA%B8%B0)

> [참고 사이트](https://velog.io/@recordsbeat/Garbage-Collector-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EA%B8%B0#reference-counting--mark-and-sweep)

<br>

## GC 구현 방식
### Serial
- 단일 쓰레드로 GC가 작동
- 무조건 STW 발생

### Parallel
- 병렬처리 GC로 멀티 쓰레드로 GC를 실행

### CMS(Concurrent Mark Sweep) GC
- STW를 최소화한 GC로 몇가지 단계를 통해 Reachable 객체를 구별
- 작동 순서
    1. `initial Mark` : Root Set 객체만 마킹(STW 발생)
    2. `Concurrent Mark` : 마킹된 Root Set과 연결된 객체들을 마킹(STW 발생 X)
    3. `Remark` : `Concurrent Mark` 과정에서 마킹된 객체와 다른 객체만 추가 마킹 및 확정(STW 발생)
    4. `Concurrent Sweep` : 마킹되지 않은 객체 삭제(STW 발생 X)


### G1 GC vs ZGC
두 종류의 GC는 자세히 설명된 [블로그 링크](https://huisam.tistory.com/entry/jvmgc#G-GC)로 대체합니다.

<br>

> [참조 사이트](https://velog.io/@recordsbeat/Garbage-Collector-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EA%B8%B0#gc-%EA%B5%AC%ED%98%84-%EB%B0%A9%EC%8B%9D)
