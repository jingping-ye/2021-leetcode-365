# 数组

数组初始化

```js
let n =7; // 假设n为数组的长度
let m = 8; // 假设m为内嵌数组元素的长度

// 初始化一个长度为n的数组，元素填充为0
let nums = new Array(n).fill(0);

// 初始化一个元素为1、3、5的数组nums
let nums = new Array(1,3,5);

// 初始化一个长度为n的数组，元素填充为2
let nums = new Array(n).fill(2);

// 初始化一个大小为m*n的二维数组dp, 其中的值均为true
let dp = Array.from(Array(m), () => Array(n).fill(true));
```

数组操作方法

```js
// 判断是否为空
let arr = new Array(n);

// 返回数组中元素的个数
arr.length

// 判断数组是否为空
arr.length === 0;

// 返回最后一个元素
arr[arr.length-1];

// 返回第一个元素
arr[0];

// 添加元素到数组的末尾
arr.push(1,[2,3...]);

// 删除数组末尾元素
arr.pop();

// 删除数组最前面元素
arr.shift();

// 添加元素到数组的头部
arr.unshift(1,[2,3...])

// 遍历
arr.forEach((item, index, array)=>{
    console.log(item, index, array)
})

// 查找元素2在数组中的索引
arr.indexOf(2); // 找不到返回-1

// 通过索引pos删除1个元素
arr.splice(pos,1);

// 在索引位置pos插入一个元素k
arr.splice(pos,0,k);

// 复制一个数组;浅拷贝，只拷贝了值
let newArr = arr.slice(); 

// 交换数组下标为0和下标为1的两个元素
[arr[0], arr[1]] = [arr[1], arr[0]];
```

