# Queue(큐)

**_선입선출(FIFO / First in, First Out)_** 형태의 선형 자료구조이다.

### 용어

| 용어  | 설명                                          |
| ----- | --------------------------------------------- |
| rear  | 큐의 가장 끝 요소                             |
| front | 큐의 가장 앞 요소                             |
| add   | 큐의 rear 부분에 요소 추가                    |
| poll  | 큐의 front 부분의 요소를 **_제거_** 하고 확인 |
| peek  | 큐의 front 부분의 요소를 확인                 |

### Java의 Queue 클래스

```java
import java.util.LinkedList;
import java.util.Queue;

Queue<자료형> queue = new LinkedList<>();
```

### 주요 메서드

| 메서드명    | 설명                                                |
| ----------- | --------------------------------------------------- |
| add(item)   | 큐에 요소 삽입                                      |
| offer(item) | 큐에 요소 삽입                                      |
| remove()    | 큐의 가장 앞에 있는 요소를 **_제거_** 하고 반환     |
| poll()      | 큐의 가장 앞에 있는 요소를 **_제거_** 하고 반환     |
| element()   | 큐의 가장 앞에 있는 요소를 반환                     |
| peek()      | 큐의 가장 앞에 있는 요소를 반환                     |
| isEmpty()   | 큐가 비어있는지 확인해 boolean값(true/false)을 반환 |
| size()      | 큐의 현재 요소 개수 반환                            |
| clear()     | 큐의 모든 요소 제거                                 |

_큐가 비어있는 상황에서 add(), remove(), element()를 하게 되면 NoSuchElementException 예외가 발생한다._
