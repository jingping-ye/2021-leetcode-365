# 链表

## 单链表

结点定义

```js
/**
 * 单链表结点定义
 */
class ListNode{
  val; // 结点存储的值
  next; // 指向下一个结点的指针
  constructor(val){
    this.val = val;
    this.next = null;
  }
}
```

使用方法

```js
// 新建单链表结点
let node1 = new ListNode(1);
let node2 = new ListNode(2);
let node3 = new ListNode(3);

// 修改结点的值
node1.val = 5;

// 连接结点
node1.next = node2;
node2.next = node3;
```

