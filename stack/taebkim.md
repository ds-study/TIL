top이 아닌 위치에 있는 나머지 원소들의 확인/변경은 원칙적으로 불가능

원래 스택이라는 자료구조는 원소의 추가/제거/top의 원소 확인 이라는 기능만 제공하는 자료구조임

[스택 활용 문제 2493](https://www.acmicpc.net/problem/2493)

```c
#include <stdio.h>

typedef struct
{
    int index;
    int height;
} Tower;

Tower stack[500001];
int top = -1;

void pop()
{
    if (top > 0)
        top--;
}

void push(Tower t)
{
    stack[++top] = t;
}

Tower peek()
{
    return stack[top];
}

int main()
{
    int n;
    scanf("%d", &n);

    push((Tower){0, 1000000});

    for (int i = 1; i <= n; i++)
    {
        int height;
        scanf("%d", &height);

        if (stack[top].height < height)
            pop();

        printf("%d ", peek().index);
        push((Tower){i, height});
    }
    return 0;
}
```
