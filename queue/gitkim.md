# Queue

큐란, 선입 선출(先入先出/First In First Out—FIFO) 특성을 가진 자료 구조를 의미한다.
새로 들어오는 데이터의 위치가 메모리의 'Rear' 또는 'Back'이고, 가장 먼저 들어와 있던 데이터의 위치가 'Front'이다.
우선순위 큐, 원형 큐 등의 바리에이션이 있다.

## Queue의 기본 연산

1. Enqueue : 큐의 rear에 데이터 항목을 추가한다.
2. Dequeue : 큐의 front에서 데이터를 제거하고 반환한다.
3. Peek : 큐의 front 데이터를 확인하지만 제거하지는 않는다.

## Queue의 기본 용어

1. Add : 큐의 rear에 데이터 항목을 추가한다.
2. Delete : 큐의 front 데이터 항목을 꺼내 사용한다.
3. Rear : 가장 최근에 추가한 데이터 항목을 가리키는 포인터
4. Front : 사용할 데이터 항목을 가리키는 포인터
5. Overflow : 끝까지 add된 경우, rear == SIZE - 1일 때 add를 시도하면 발생한다.
6. Underflow : 더 이상 데이터가 큐에 존재하지 않는 경우, front > rear 일 때 delete 시도하면 발생한다.

## Queue의 종류

1. 선형 큐(Linear Queue) : 데이터를 FIFO 순서로 처리하는 가장 기본적인 Queue
2. 환형 큐(Circular Queue) : Queue의 마지막 요소가 첫 요소와 연결된 Queue, 원형으로 순환한다.
3. 우선순위 큐(Priority Queue) : 각 데이터 요소에 우선순위를 할당하고 해당 우선순위에 따라 데이터를 처리하는 Queue
4. 데크(Dequeue) : 양 끝단에서 데이터의 삽입과 삭제가 가능한 Queue
