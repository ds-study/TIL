Stack은 LIFO (Last In First Out) 원칙을 따르는 선형 자료구조로, 마지막에 삽입된 원소가 먼저 pop된다.

## 스택의 종류
- 정적 스택: 크기가 정해져 있다. 스택이 꽉 차면 추가적으로 원소를 추가할 수 없고 오버플로우 에러가 발생한다. 스택이 비면 원소를 제거할 수 없고 언더플로우 에러가 난다.
- 동적 스택: 스택의 크기가 동적으로 늘어나고 줄어든다. 스택이 꽉 차면, 새 원소를 삽입할 때 스택 사이즈가 자동으로 늘어난다. 동적 스택은 연결리스트로 구현된다.

## 스택의 기본 연산
- `push()`
- `pop()`
- `top()`
- `isEmpty()`
- `isFull()`

## 연산 복잡도
| 연산 종류       | 시간 복잡도     | 공간 복잡도      |
|-----------------|-----------------|------------------|
| `push`        | O(1)            | O(1)             |
| `pop`         | O(1)            | O(1)             |
| `top`         | O(1)            | O(1)             |
| `isEmpty`     | O(1)            | O(1)             |
| `isFull`      | O(1)            | O(1)             |

## 문제 추천
- [1406: 에디터 (실2)](https://www.acmicpc.net/problem/1406)
- [4889: 안정적인 문자열 (실1)](https://www.acmicpc.net/problem/4889)