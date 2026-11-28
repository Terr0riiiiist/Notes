```c
#include <stdio.h>

int Max(int a, int b);
int Kanade (int *arr, int length) {
    int local_max  = arr[0];
    int global_max = arr[0];
    for(int i = 1; i < length; i++){
        local_max  = Max(arr[i] + local_max, arr[i]);
        global_max = Max(global_max, local_max);
    }
    return global_max;
}

int Max(int a, int b) {
    if (a>=b) return a;
    return b;
}
int main(void){
    int arr[5] = {2,5,-1,4,3};
    printf("%d\n", Kanade(arr,5));
}

```

> *注意`local_max  = Max(arr[i] + local_max, arr[i]);`*

**这里max不仅给两个数做比较，而且在arr[i] > local_max +arr[i] 时“重置”遍历，从当前元素继续开始计算子序列**

**时间复杂度: O(n)
