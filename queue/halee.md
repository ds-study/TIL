큐는 FIFO (First In First Out) 원칙을 따르는 선형 자료 구조로, 먼저 삽입된 원소가 먼저 나온다.

![큐](https://media.geeksforgeeks.org/wp-content/uploads/20241212130245410876/Representation-of-Queue-Data-Structure.webp)

## 큐의 기본 연산
- `enqueue()`: 큐의 tail에 원소를 삽입한다.
- `dequeue()`: 큐의 head에 있는 원소를 제거한다.
- `front()`: 큐의 head에 있는 원소를 제거하지 않고 리턴만 한다. 
- `size()`: 큐에 있는 원소의 개수를 리턴한다.
- `isEmpty()`: 큐가 비어있는지 여부를 boolean으로 반환한다.
- `isFull()`: 큐가 찼는지 여부를 boolean으로 반환한다.

## 연산 복잡도
| 연산 종류류     | 시간 복잡도 | 공간 복잡도 |
|--------------|------------|------------|
| `enqueue` | O(1)       | O(1)       |
| `dequeue` | O(1)       | O(1)       |
| `front` | O(1) | O(1)       |
| `size` | O(1)      | O(1)       |
| `isEmpty` | O(1) | O(1) |
| `isFull` | O(1) | O(1)   |


## 큐의 종류
1. Simple Queue: FIFO 원칙을 따르는 단순한 큐이다.
2. Double-Ended Queue (Deque): 삽입과 삭제가 큐의 앞/뒤 양쪽에서 가능하다.
3. Circular Queue: 큐의 마지막 위치가 첫번째 위치와 연결된 원형 큐로 마찬가지로 FIFO 원칙을 따른다.
4. Priority Queue: 원소의 우선순위를 기준으로 접근 가능하다.
	- Ascending Priority Queue: 우선순위가 높아지는 순으로 정렬된다. 우선순위가 가장 낮은 원소가 먼저 pop된다.
	- Descending Priority Queue: 우선순위가 낮아지는 순으로 정렬된다. 우선순위가 가장 높은 원소가 먼저 pop된다.

## 큐의 응용 사례
- 생산자와 소비자의 속도가 다를 경우 버퍼로 사용된다. 예를 들어 cpu는 처리 속도가 굉장히 빠른 것에 비해 키보드는 처리 속도가 매우 느리기 때문에 큐가 버퍼로 사용된다.
- 생산자는 하나인데 소비자가 여럿인 경우에도 사용된다. 예를 들어 여러 프로세스들이 cpu 하나를 동시에 사용하는 경우에 큐가 사용된다.
- 큐는 너비 우선 탐색이나 위상 정렬과 같은 알고리즘에 사용된다.

## 문제 추천
- [1966: 프린터 큐(실3)](https://www.acmicpc.net/problem/1966)
