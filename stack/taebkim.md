(스택 활용 문제)[https://www.acmicpc.net/problem/2493]

```
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