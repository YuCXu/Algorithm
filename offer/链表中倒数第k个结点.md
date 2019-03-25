##### 题目：输入一个链表，输出该链表中倒数第k个结点。 

思路：先定义两个指向链表头的指针p ,q；先令一个指针指向第k节点，然后两个指针同时向后移动，最后p指向的即为倒数第k个节点。当k为零或节点为空返回。 

代码：

```java
public class Solution{
    public ListNode FindKthToTail(ListNode head,int k){
        ListNode p,q;
        p=q=head;
        int i = 0;
        for(;p != null;i++){
            if(i >= k){
                q = q.next;
            }
            p = p.next;
        }
        rerutn i < k ? null : q;
    }
}
```



