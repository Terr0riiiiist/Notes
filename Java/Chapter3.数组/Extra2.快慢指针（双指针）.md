*Leetcode:定义一个有序递增数组，去除其中重复元素*
```
public class Leetcode_practise2 {  
    static void main() {  
        int arr [] = {1,1,2,2,2,2,3,3,3,3};  
        int slow = 0;  
        int fast = 1;  
  
        while (fast < arr.length) {  
            if (arr[slow] != arr[fast]) {  
                slow++;  
                arr[slow] = arr[fast];  
            }  
            fast++;  
  
        }  
        for (int i = 0; i <= slow; i++)  
            System.out.print(arr[i] + " ");  
        }  
    }
```
**慢指针：存入的位置**
**快指针：找不存在的数据**
**如果快慢指针数据相等：快指针移到下一个位置
快慢指针数据不相等：慢指针移到下一个位置 ->存入快指针的数据 -> 快指针移到下一个位置

