*给定一个递增的有序数组和一个目标值，在数组中找到目标值，打印其索引。* 
*如果目标值不存在于数组中，打印应插入的位置 

**举例1**： 
数据：nums = [1,3,5,6]； target = 5 输出：2 
**举例2：** 
数据：nums = [1,3,5,6]，target = 2 输出：1 
**举例3：**
数据：nums = [1,3,5,6]，target = 7 输出：4

```
public class Assignment3 {  
    static void main() {  
        int[] num = {1, 3, 5, 6};  
        int target1 = 4; /* -> 2 */  
        int target2 = 3; /* -> 1 */  
        int target3 = 7; /* -> 4 */  
  
        int count = 0;  
        for (int i = 0; i <= num.length - 1; i++) {  
            if (num[i] == target1) {  
                System.out.println(i);  
                count++;  
                break;  
            }  
        }  
        int count2 = 0;  
        int i = 0;  
        if (count == 0) {  
            for (; i < num.length; i++) {  
                if (num[i] < target1) {  
                    count2++;  
                } else break;  
            }  
            System.out.println(count2);  
        }  
    }  
}
```
注意数组中有重复元素，不加入break会重复打印。