> 给定一个整数序列 {${}a_{1} ,a_{2}, a_{3}, \dots , a_{n}{}$} ,求长度为${}k (k\leq n){}$ 的连续子序列和最大值

```c
#include <stdio.h>
#include <stdlib.h>
void merge(int *arr, int left, int mid, int right) ;

void merge_sort(int *arr, int left, int right) {
    int mid = left + (right - left) / 2;
    if (right <= left) return;
    merge_sort(arr, left, mid);
    merge_sort(arr, mid + 1, right);
    merge(arr, left, mid, right);
}
void merge(int *arr, int left, int mid, int right) {
    int *temp = (int*) malloc(sizeof(int) * (right-left+1)); // 1. Create temporary array
    int cnt = 0;  // 2. Initialize pointers
    int i = left;
    int j = mid + 1;

    while (i <= mid && j <= right){      // 3. Compare elements and merge
        if(arr[i] <= arr[j]){
            temp[cnt++] = arr[i++];
        } else temp[cnt++] = arr[j++];
    }

    while (i <= mid  ) temp [cnt++] = arr[i++] ;  // 4. Append remaining elements
    while (j <= right) temp [cnt++] = arr[j++] ;

    cnt = 0;   // 5. Copy back to original array
    for(; left <=right; left++)  arr[left] = temp[cnt++];
    free(temp);
}


int main(void){
    int arr [10] = {9,5,1,4,3,10,2,1,0,7};
    merge_sort(arr, 0, 9);
    for(int i=0; i<10; i++ ){
        printf("%d ",arr[i]);
    }
}

```

### Explanations
#### 归&并
归就是把一个数组里所有的数二分成小数组直到被分成单独的数；然后执行[[Assignment_2 （二合一为有序数组）]]

#### merge_sort 详解
```c
void merge_sort(int *arr, int left, int right) {
    int mid = left + (right - left) / 2;
    if (right <= left) return;
    merge_sort(arr, left, mid);
    merge_sort(arr, mid + 1, right);
    merge(arr, left, mid, right);
}
```
*调用的子递归结束之后回到外层递归执行下一行，而不是直接退出*
- 调用时：新函数（包括递归产生的子调用）压到栈顶。
- 返回时：栈顶函数出栈，控制权交还给它下面那一层（调用者），调用者从调用点继续往下执行。
- 主函数是最后一个出栈的，因为它是最先入栈的。




