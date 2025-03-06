# 투 포인터

### 개요

**정렬된** 배열에서 원하는 답(구간)을 찾기 위해 **두 개의 포인터**를 두고 조작하는 알고리즘들이다.<br>

모든 경우의 수를 탐색하는 방식 (`O(N²)`)보다 시간 복잡도를 단축할 수 있다. (`O(N)`)<br>

### 투 포인터(Two Pointer)

예를 들어, 정렬된 배열에서 합이 target 값이 되는 서로 다른 두 수를 찾으려고 한다.<br>

이중 `for`문으로 해결할 수도 있지만, 이 경우 배열의 크기가 매우 커지면 연산 시간이 늘어나게 된다.<br>

이 때 투 포인터 방식을 사용할 수 있다.<br>

```
// 주어진 배열의 길이는 N이며 찾아야 할 값을 target이라고 할 때

int p1 = 0; // 앞 포인터
int p2 = N - 1; // 뒤 포인터

while(p1 < p2){
  if(array[p1] + array[p2] == target){
    System.out.println("find!");
    break;
  } else if (array[p1] + array[p2] < target) {
    // 합이 target보다 작을 경우, 더 큰 값을 더해야 하므로 앞 포인터 증가
    p1 ++;
  } else {
    // 합이 target보다 큰 경우, 더 작은 값을 더해야 하므로 뒤 포인터 감소
    p2 --;
  }
}
```

### 슬라이딩 윈도우(Sliding Window)

슬라이딩 윈도우 알고리즘은 두 개의 포인터로 **일정 범위를 지정**한 다음, **범위를 유지한 채로 이동**하는 방법이다.<br>

![sw](https://github.com/CHOO-O/CHOO-study/blob/main/Algorithm/assets/Two-pointer-sw.png?raw=true)

위와 같이 범위를 이동하면 겹치는 일부 요소를 재사용하거나 겹치지 않는 부분만 비교할 수 있기 때문에 중복 연산을 줄일 수 있다.<br>

이 알고리즘을 사용하는 문제들은 `Deque`를 사용해 구현하는 경우가 많다.<br>

🔗 [Deque(덱)](https://github.com/CHOO-O/CHOO-study/blob/main/Data-structure/Deque.md)

🔗 [백준 11003 최솟값 찾기](https://github.com/CHOO-O/CHOO-algorithm/tree/main/%EB%B0%B1%EC%A4%80/Platinum/11003.%E2%80%85%EC%B5%9C%EC%86%9F%EA%B0%92%E2%80%85%EC%B0%BE%EA%B8%B0)
