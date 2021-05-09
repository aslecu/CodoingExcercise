### Result1:

- 执行用时：9 ms, 在所有 Java 提交中击败了12.85%的用户
- 内存消耗：46 MB, 在所有 Java 提交中击败了95.76%的用户



### Code:

```Java
class Solution {
    int[] res;
    int cnt = 0, n, start, nine = 0;
    StringBuilder str;
    char[] num, loop={'0', '1', '2', '3', '4', '5', '6', '7', '8', '9'};
    public int[] printNumbers(int n) {
        this.n = n;
        res = new int[(int)Math.pow(10, n) - 1];
        num = new char[n];
        start = n - 1;
        dfs(0);
        return res;
    }
    
    private void dfs(int x) {
        if(x == n) {    // 循环结束，高位已添加
            String s = String.valueOf(num).substring(start);
            if(!s.equals("0")){     // 只有第一个0不加入数组中
                res[cnt++] = Integer.parseInt(s);
            }
            if(n - start == nine){  // 最高位-起始位==9的个数，则需要进位
                start--;
            }
            return;
        }
        // 从0-9，固定第x位添加
        for(char i : loop) {
            if(i == '9'){
                nine++;
            }
            num[x] = i;
            dfs(x + 1);
        }
        nine--;
    }
}
```



### Result:

- 执行用时：1 ms, 在所有 Java 提交中击败了99.99%的用户
- 内存消耗：46.5 MB, 在所有 Java 提交中击败了82.30%的用户

### Code2:

```java
class Solution {
    public int[] printNumbers(int n) {
        int max = 1;
        for(int i=0;i<n;i++){
            max *= 10;
        }
        int[] res = new int[max-1];
        for(int i=1;i<max;i++){
            res[i-1] = i;
        }
        return res;
    }
}
```



P.S. 非常狗……直接算可以beat99.99%，根本没有大数的用例……优化变成了负优化