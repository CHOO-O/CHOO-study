# 시간 복잡도

### 시간 복잡도란?

문제를 해결하기 위해 수행하는 연산 횟수를 말한다.<br>

### 시간 복잡도의 유형

🔹 **Big-Ω(빅-오메가, Ω)** : 최선의 경우(Best case)의 연산 횟수이다.<br>
🔹 **Big-Θ(빅-세타, Θ)** : 최선과 최악의 경우가 같을 때의 연산 횟수이다.<br>
🔹 **Big-O(빅-오, O)** : 최악의 경우(Worst case)의 연산 횟수이다.<br>

알고리즘 성능 분석에서는 주로 **Big-O**표기법을 사용한다.<br>

#### Big-O 표기법으로 표현한 시간 복잡도 그래프

![graph](https://github.com/CHOO-O/CHOO-study/blob/main/Algorithm/assets/Time-complexity-graph.png?raw=true)

### 알고리즘 풀이에서의 시간 복잡도

시간 복잡도를 도출하는 기준은 다음과 같다.<br>

1. 상수는 시간 복잡도 계산에서 제외한다.
2. **가장 많이 중첩된 반복문의 수행 횟수**가 시간 복잡도의 기준이 된다.

```
// 예시 1 : 연산 횟수가 1인 경우의 시간 복잡도 = O(1)
// N과 관계 없는 상수 연산임

public class Main{
  public static void main(String[] args){
    int N = 100;

    for(int i = 0; i < 10; i++){
      System.out.println("Hello, world!");
    }
  }
}
```

```
// 예시 2 : 연산 횟수가 N인 경우의 시간 복잡도 = O(N)

public class Main{
  public static void main(String[] args){
    int N = 100;

    for(int i = 0; i < N; i++){
      System.out.println("Hello, world!");
    }
  }
}
```

```
// 예시 3 : 연산 횟수가 2N인 경우의 시간 복잡도 = O(N)
// 상수는 계산에서 제외

public class Main{
  public static void main(String[] args){
    int N = 100;

    for(int i = 0; i < N; i++){
      System.out.println("Hello, world!");
    }

    for(int i = 0; i < N; i++){
      System.out.println("Hello, world!");
    }
  }
}
```

```
// 예시 4 : 연산 횟수가 N^2인 경우의 시간 복잡도 = O(N^2)
// 가장 많이 중첩된 반복문의 수행 횟수를 기준으로 함

public class Main{
  public static void main(String[] args){
    int N = 100;

    for(int i = 0; i < N; i++){
      System.out.println("Hello, world!");
    }

    for(int i = 0; i < N; i++){
      for(int j = 0; j < N; j++){
        System.out.println("Hello, world!");
      }
    }
  }
}
```
