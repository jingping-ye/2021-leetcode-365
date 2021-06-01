# 树

### 衍生的树的种类

- 二叉树
- 二叉搜索树
- AVL树
- 红黑树
- 区间树
- B树

## 二叉树

```js
/**
 * 二叉树结点定义
 */
class TreeNode {
  val; // 结点存储的值
  left; // 指向左侧子结点的指针
  right; // 指向右侧子结点的指针
  constructor(val) {
    this.val = val;
    this.left = null;
    this.right = null;
  }

  traverse(node){
    // 前序遍历
    traverse(node.left);

    // 中序遍历
    traverse(node.right);

    // 后序遍历
  }
}

```

二叉树使用方法

```js
// 新建二叉树结点
let node1 = new TreeNode(1);
let node2 = new TreeNode(2);
let node3 = new TreeNode(3);

// 修改结点的值
node1.val = 5;

// 连接结点
node1.left = node2;
node2.right = node3;
```

遍历

```js

```

