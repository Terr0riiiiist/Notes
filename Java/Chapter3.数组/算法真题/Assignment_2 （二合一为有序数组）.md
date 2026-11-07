给你两个有序数组 **arr1** 和 **arr2**， 将两个数组中的数据合并到一个大数组中。 
要求：合并之后的大数组也是有序的 举例1：
arr1: 1 3 5 7 9
arr2: 2 4 6 8 10 
arr3: 1 2 3 4 5 6 7 8 9 10

```
package Array.Assignment;  
  
public class Assignment2_fix {  
    static void main() {  
        /*给定两个有序递增数组，将他们合并为第三个有序递增数组*/  
        int A[] = {1, 3, 5, 5, 7, 8};  
        int B[] = {1, 2, 4, 6, 8, 9, 10};  
        int C[] = new int[10];  
  
        int count = 0;  
        int i = 0;  
        int j = 0;  
        while (i < A.length && j < B.length) {  
            if (A[i] <= B[j] ) {  
                if(count == 0 || A[i] != C[count-1]) {  
                    C[count] = A[i];  
                    count++;  
                }  
                i++;  
  
            }  
            else  {  
               if ( B[j] != C[count-1]){  
                C[count] = B[j];  
                count++;}  
               j++;  
            }  
  
        }  
  
  
            if (i >= A.length) {  
                for (; j < B.length; j++) {  
                    if (B[j] != C[count-1] && count !=0) {  
                        C[count] = B[j];  
                        count++;  
                    }  
                }  
            }  
                else  
                for (; i < B.length; i++) {  
                    if (A[i] != C[count-1] && count != 0) {  
                        C[count] = A[i];  
                        count++;  
                    }  
                }  
  
        for (int i1 = 0; i1 < count; i1++) {  
            System.out.print(C[i1] + " ");  
  
        }  
    }  
}
```

#### Note1: 双指针不一定必须是嵌套，可以是平行
*例如本题目中只需要比较A[i]和B[j],两个指针独立运行*
#### Note2:  指针的自增
*如果指针自增写在内层if,即去重if，如果不重复指针就不走，形成死循环*
#### Note3: 分支判断
*主循环里两个独立的if表示一次循环同时读取两个if,可能造成指针同时增加；if...else和双if要判断何时使用*
#### Note4: 判断if和while的使用时机
*结尾把一个数组剩余的元素全部加到大数组，最初写的是while (i == $A.length$),这样永远不会停止循环，大数组指针越界；应该用if ( i >= $A.length$),内层再通过arr.fori把剩余元素加到大数组*
#### Note5: 注意指针范围一定要落在[0,length-1]
*使用count-1这种指针时，要筛选非负情况*

