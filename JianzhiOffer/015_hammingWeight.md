### Result:

- 执行用时：1 ms, 在所有 Java 提交中击败了96.86%的用户
- 内存消耗：35 MB, 在所有 Java 提交中击败了97.62%的用户



### Code:

```Java
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
            int j = 1;
            int res = 0;
            for(int i=0;i<32;i++){
                if((n & j) != 0){
                    res++;
                }
                j = j << 1;
            }
            return res;
    }
}
```

### Code2:

```java
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
        return dfs(n,1);
    }
    public int dfs(int n,int i){
        if(i>32){
            return 0;
        }
        return  ((n>>>i) & 1) == 1 ? dfs(n,i+1)+1 : dfs(n,i+1);
    }
    
}
```

