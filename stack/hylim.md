# 큐 (Queue)

## 큐란?
큐(Queue)는 데이터 구조의 한 종류로, 먼저 들어온 데이터가 먼저 나가는 FIFO(First In, First Out) 원칙을 따릅니다. 큐는 일상 생활에서 줄을 서는 것과 비슷한 개념입니다.

## 큐의 주요 연산
큐에서 주로 사용되는 연산은 다음과 같습니다:
- `enqueue`: 큐의 뒤에 요소를 추가합니다.
- `dequeue`: 큐의 앞에서 요소를 제거하고 반환합니다.
- `peek` 또는 `front`: 큐의 앞에 있는 요소를 반환하지만 제거하지는 않습니다.
- `isEmpty`: 큐가 비어 있는지 확인합니다.
- `size`: 큐의 크기를 반환합니다.

## 큐의 종류
큐에는 여러 종류가 있습니다:
- **일반 큐 (Simple Queue)**: 기본적인 FIFO 구조를 따르는 큐입니다.
- **원형 큐 (Circular Queue)**: 큐의 마지막 위치가 처음 위치와 연결되어 원형으로 동작하는 큐입니다.
- **우선순위 큐 (Priority Queue)**: 각 요소가 우선순위를 가지고 있으며, 우선순위가 높은 요소가 먼저 나가는 큐입니다.
- **이중 끝 큐 (Deque, Double-ended Queue)**: 양쪽 끝에서 요소를 추가하거나 제거할 수 있는 큐입니다.

## 큐의 구현

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

typedef struct s_queue {
	int items[MAX];
	int front;
	int rear;
} Queue;

void initializeQueue(Queue *q) {
	q->front = -1;
	q->rear = -1;
}

int isFull(Queue *q) {
	return q->rear == MAX - 1;
}

int isEmpty(Queue *q) {
	return q->front == -1 || q->front > q->rear;
}

void enqueue(Queue *q, int value) {
	if (isFull(q)) {
		printf("Queue is full\n");
		return;
	}
	if (isEmpty(q)) {
		q->front = 0;
	}
	q->items[++q->rear] = value;
}

int dequeue(Queue *q) {
	if (isEmpty(q)) {
		printf("Queue is empty\n");
		exit(EXIT_FAILURE);
	}
	return q->items[q->front++];
}

int peek(Queue *q) {
	if (isEmpty(q)) {
		printf("Queue is empty\n");
		exit(EXIT_FAILURE);
	}
	return q->items[q->front];
}

int size(Queue *q) {
	if (isEmpty(q)) {
		return 0;
	}
	return q->rear - q->front + 1;
}

int main() {
	Queue q;
	initializeQueue(&q);

	enqueue(&q, 10);
	enqueue(&q, 20);
	enqueue(&q, 30);

	printf("Front element is %d\n", peek(&q));
	printf("Queue size is %d\n", size(&q));

	printf("Dequeued element is %d\n", dequeue(&q));
	printf("Queue size is now %d\n", size(&q));

	return 0;
}
```

## 큐의 활용 예시
큐는 다음과 같은 다양한 분야에서 활용됩니다:
- **운영체제**: 프로세스 스케줄링
- **네트워크**: 패킷 처리
- **프린터**: 인쇄 작업 대기열
- **콜센터**: 고객 대기열 관리

## 참고 자료
- [위키백과: 큐](https://ko.wikipedia.org/wiki/%ED%81%90_(%EC%BB%B4%ED%93%A8%ED%8C%85))
