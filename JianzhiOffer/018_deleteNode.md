### Result:

- 执行用时：0 ms, 在所有 Java 提交中击败了100.00%的用户
- 内存消耗：37.9 MB, 在所有 Java 提交中击败了60.73%的用户



### Code:

```Java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteNode(ListNode head, int val) {
        ListNode dummpy = new ListNode(0);
        dummpy.next  = head;
        ListNode nextNode = dummpy.next;
        ListNode curNode = dummpy;
        while(nextNode != null){
            if(val == nextNode.val){
                curNode.next = nextNode.next;
                break;
            }
            curNode = nextNode;
            nextNode = curNode.next;
        }
        return dummpy.next;
    }
}
```

