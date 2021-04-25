### Result:

- 执行用时：1 ms, 在所有 Java 提交中击败了45.22%的用户

- 内存消耗：35.4 MB, 在所有 Java 提交中击败了22.82%的用户



### Code:

```Java
class Solution {
    public int cuttingRope(int n) {
        int[] max = new int[n+1];
        max[0] = 0;
        max[1] = 1;
        max[2] = 1;
        int i = 3;
        int temp;
        while(i<=n){
            max[i] = 0;
            for(int j=1;j<=i-1;j++){
                temp = j * Math.max(i-j, max[i-j]);
                if(temp > max[i]){
                    max[i] = temp;
                }
            }
            i++;
        }
        return max[n];
    }
}
```
