```c
scanf: %[flag]type
```

| **flag** | **含义** | **flag** | **含义**       |
| -------- | ------ | -------- | ------------ |
| *        | 跳过     | l        | long, double |
| 数字       | 最大字符数  | ll       | long long    |
| hh`      | char   | L        | long double  |
| h        | short  |          |              |
```c
int a, b;
int count = scanf("%d %d", &a, &b);

// 如果你成功输入了两个整数，比如 "10 20"，count 的值是 2
// 如果只成功输入了一个整数，count 的值是 1
// 如果输入格式不对或直接结束（如 Ctrl+D / Ctrl+Z），count 的值是 EOF (-1)
```