# Deque(덱)

Double Ended Queue로, **양방향에서 삽입과 삭제가 가능한 큐** 자료구조이다.

### 용어

| **용어**  | **설명**          |
| --------- | ----------------- |
| **front** | 덱의 가장 앞 요소 |
| **rear**  | 덱의 가장 끝 요소 |

### Java의 Deque 클래스

```java
import java.util.LinkedList;
import java.util.Deque;

Deque<자료형> deque = new LinkedList<>();
```

### 주요 메서드

| **메서드명**                        | **설명**                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| **addFirst / offerFirst(item)**     | 덱의 가장 앞에 요소 삽입                                            |
| **add / addLast / offerLast(item)** | 덱의 가장 뒤에 요소 삽입                                            |
| **pollFirst()**                     | 덱의 가장 앞에 있는 요소를 **제거** 후 반환<br> 없을 시 `null` 반환 |
| **pollLast()**                      | 덱의 가장 뒤에 있는 요소를 **제거** 후 반환<br> 없을 시 `null` 반환 |
| **peekFirst()**                     | 덱의 가장 앞에 있는 요소를 반환 <br> 없을 시 `null` 반환            |
| **peekLast()**                      | 덱의 가장 뒤에 있는 요소를 반환<br> 없을 시 `null` 반환             |
| **removeFirst()\***                 | 덱의 가장 앞에 있는 요소를 **제거** 후 반환                         |
| **removeLast()\***                  | 덱의 가장 뒤에 있는 요소를 **제거** 후 반환                         |
| **getFirst()\***                    | 덱의 가장 앞에 있는 요소를 반환                                     |
| **getLast()\***                     | 덱의 가장 뒤에 있는 요소를 반환                                     |
| **removeFirstOccurrence(item)**     | 덱의 앞쪽부터 탐색해 특정 요소 삭제                                 |
| **removeLastOccurrence(item)**      | 덱의 뒤쪽부터 탐색해 특정 요소 삭제                                 |
| **size()**                          | 덱의 현재 요소 개수 반환                                            |
| **isEmpty()**                       | 덱이 비어있는지 확인해 `true/false`를 반환                          |
| **clear()**                         | 덱의 모든 요소 제거                                                 |

> **주의할 점**<br>**\*** 표시가 있는 메서드는 덱이 비어있는 상황에서 호출 시 NoSuchElementException 예외가 발생한다.
