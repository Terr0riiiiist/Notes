*Leetcode：从1~100中随机选取十个数生成一个数组，要求不能重复*
```
public class Leetcode_practise_fix {  
    public static void main(String[] args) {  
        Random a = new Random();  
  
  
        int arr[] = new int[10];  
        for (int i = 0; i < arr.length; ) {  
            int num = a.nextInt(1, 101);  
            int count = 0;  
            for (int j = 0; j < arr.length; j++) {  
                if (num == arr[j]) {  
                    count++;  
                    break;  
                }  
            }  
            if (count == 0) {  
                num = a.nextInt(1, 101);  
                arr[i] = num;  
                i++;
```
这里只有count == 0时才会继续下一个数的填入，如果i++在**for**里索引无条件自增。
