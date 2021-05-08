
### Result:

- 执行用时：5 ms, 在所有 Java 提交中击败了**98.39%**的用户

- 内存消耗：40.8 MB, 在所有 Java 提交中击败了**5.01%**的用户




### Code:
```Java
class Solution {
    public boolean exist(char[][] board, String word) {
        char[] words = word.toCharArray();
        int rLen = board.length, cLen = board[0].length;
        for(int i = 0; i < rLen; i++) {
            for(int j = 0; j < cLen; j++) {
                if(dfs(board, words, i, j, 0)){
                    return true;
                }
            }
        }
        return false;
    }
    boolean dfs(char[][] board, char[] word, int i, int j, int k) {
        if(i >= board.length || i < 0 || j >= board[0].length || j < 0 
          || board[i][j] != word[k]){
            return false;
        }
        if(k == word.length - 1){
            return true;
        }
        board[i][j] = ' ';
        boolean res = dfs(board, word, i + 1, j, k + 1) || dfs(board, word, i - 1, j, k + 1) || 
                      dfs(board, word, i, j + 1, k + 1) || dfs(board, word, i , j - 1, k + 1);
        board[i][j] = word[k];
        return res;
    }
}
```