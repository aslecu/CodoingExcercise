### Result:

- 执行用时：0 ms, 在所有 Java 提交中击败了100.00%的用户
- 内存消耗：35.2 MB, 在所有 Java 提交中击败了60.57%的用户



### Code:

```Java
class Solution {
    public int cuttingRope(int n) {
        if(n<4){
            return n-1;
        }
        long res = 1;
        while(n>4){
            res = res * 3 % 1000000007;
            n = n-3;
        }
        return (int)(res * n % 1000000007);
    }
}
```
