# 哈希表

### 基础操作

- JavaScript中的哈希表默认有序，即按照增加的先后顺序排序。

```js
// 初始化一个哈希表
let map = new Map();

// 初始一个哈希表，包含键值对[a,1],[b,2];
let map = new Map([
    ['a',1],['b',2]
]);

// 返回哈希表的长度
map.size;

// 返回哈希表是否为空
map.size === 0;

// 判断哈希表中是否存在键key
map.has(key);

// 获取键对应的值，键不存在返回undefined
map.get('a');

// 设置键值对
map.set('c',1);

// 清除所有键值对
map.clear();


// 删除对应键key
map.delete(key);

// 返回所有的键
// MapIterator {"a", "b", "c"}
map.keys();

// 返回所有的值
// MapIterator {1, 2, 1}
map.values();

// 迭代map
map.forEach((value,key)=>{
    console.log(key, value);
})

for(let [key, value] of map){
    console.log(key, value)
}

// map转为数组
let arr  = [...map];

// 复制map
let map1 = new Map([
    ['a',1],
    ['b', 2]
]);
let map2 = new Map(map1);

// 合并两个map
let first = new Map([
  [1, 'one'],
  [2, 'two'],
  [3, 'three'],
]);

let second = new Map([
  [1, 'uno'],
  [2, 'dos']
]);

// 合并两个Map对象时，如果有重复的键值，则后面的会覆盖前面的。
// 展开运算符本质上是将Map对象转换成数组。
let merged = new Map([...first, ...second]);

```

### 哈希冲突

> 对于键值相同的处理

- 拉链法：使用链表，额外的空间存储
- 线性探查法：使用数组，方便连续寻址。
