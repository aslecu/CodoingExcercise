
### Result:

- 执行用时：
1 ms, 在所有 Java 提交中击败了 **84.55%** 的用户

- 内存消耗：
35.3 MB, 在所有 Java 提交中击败了 **85.87%** 的用户



### Code:
```Java
class Solution {
    int m, n, k;
    boolean[][] visited;
    public int movingCount(int m, int n, int k) {
        this.m = m;
        this.n = n;
        this.k = k;
        this.visited = new boolean[m][n];
        return goNext(0, 0, 0, 0);
    }

    public int goNext(int x, int y, int sumi, int sumj){
        if (sumi+sumj > k || x >= m || y >= n || visited[x][y]){
            return 0;
        }
        visited[x][y] = true;
        return 1 + goNext(x+1, y, getSum(x+1), getSum(y)) + goNext(x, y+1, getSum(x), getSum(y+1));
    }

    private int getSum(int n){
        int sum=0;
        while(n > 0) {
            sum += n % 10;
            n /= 10; 
        }
        return sum;
    }
}
```