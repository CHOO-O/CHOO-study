# Stack(스택)

**_후입선출(LIFO / Last in, First Out)_** 형태의 선형 자료구조이다.

### Java의 Stack 클래스

```java
imort java.util.Stack;

Stack<자료형> stack = new Stack<>();
```

_!! Stack 클래스는 deprecated되었기 때문에 Deque 클래스를 사용하는것을 권장하고 있다. 추후 정리해서 올릴 것!_

### 주요 메서드

| 메서드명   | 설명                                                  |
| ---------- | ----------------------------------------------------- |
| push(item) | 스택에 요소 삽입                                      |
| pop()      | 스택의 가장 위에 있는 요소를 **_제거_** 하고 반환     |
| peek()     | 스택의 가장 위에 있는 요소를 반환                     |
| isEmpty()  | 스택이 비어있는지 확인해 boolean값(true/false)을 반환 |
| size()     | 스택의 현재 요소 개수 반환                            |

_주의! 스택이 비어있는 상황에서 pop()혹은 peek()를 하게 되면 EmptyStackException 예외가 발생한다._
