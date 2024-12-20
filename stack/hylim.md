# 스택 (Stack)

스택은 후입선출(LIFO, Last In First Out) 방식으로 동작하는 자료 구조입니다. 스택에서는 마지막에 삽입된 요소가 가장 먼저 제거됩니다.

## 주요 연산

- **push**: 스택의 맨 위에 요소를 추가합니다.
- **pop**: 스택의 맨 위에 있는 요소를 제거하고 반환합니다.
- **peek**: 스택의 맨 위에 있는 요소를 제거하지 않고 반환합니다.
- **isEmpty**: 스택이 비어 있는지 확인합니다.
- **size**: 스택에 있는 요소의 개수를 반환합니다.

## 스택의 활용 예시

- **함수 호출 스택**: 함수 호출 시 호출된 함수의 정보를 스택에 저장하고, 함수가 종료되면 스택에서 제거합니다.
- **괄호 검사**: 수식의 괄호가 올바르게 짝지어졌는지 검사할 때 사용합니다.
- **뒤로 가기 기능**: 웹 브라우저의 뒤로 가기 기능은 스택을 이용하여 이전 페이지로 이동합니다.

## 스택의 구현

### 배열을 이용한 스택 구현

스택은 다양한 알고리즘과 문제 해결에 유용하게 사용되는 자료 구조입니다.
### 배열을 이용한 스택 구현 (C 언어 예시)

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

typedef struct s_Stack{
	int items[MAX];
	int top;
} Stack;

void initStack(Stack *s) {
	s->top = -1;
}

int isFull(Stack *s) {
	return s->top == MAX - 1;
}

int isEmpty(Stack *s) {
	return s->top == -1;
}

void push(Stack *s, int item) {
	if (isFull(s)) {
		printf("Stack is full\n");
		return;
	}
	s->items[++(s->top)] = item;
}

int pop(Stack *s) {
	if (isEmpty(s)) {
		printf("Stack is empty\n");
		exit(1);
	}
	return s->items[(s->top)--];
}

int peek(Stack *s) {
	if (isEmpty(s)) {
		printf("Stack is empty\n");
		exit(1);
	}
	return s->items[s->top];
}

int size(Stack *s) {
	return s->top + 1;
}
```

### 연결 리스트를 이용한 스택 구현 (C 언어 예시)

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
	int value;
	struct Node* next;
} Node;

typedef struct {
	Node* top;
	int size;
} Stack;

void initStack(Stack *s) {
	s->top = NULL;
	s->size = 0;
}

int isEmpty(Stack *s) {
	return s->top == NULL;
}

void push(Stack *s, int item) {
	Node* newNode = (Node*)malloc(sizeof(Node));
	newNode->value = item;
	newNode->next = s->top;
	s->top = newNode;
	s->size++;
}

int pop(Stack *s) {
	if (isEmpty(s)) {
		printf("Stack is empty\n");
		exit(1);
	}
	Node* temp = s->top;
	int item = temp->value;
	s->top = s->top->next;
	free(temp);
	s->size--;
	return item;
}

int peek(Stack *s) {
	if (isEmpty(s)) {
		printf("Stack is empty\n");
		exit(1);
	}
	return s->top->value;
}

int size(Stack *s) {
	return s->size;
}
```

