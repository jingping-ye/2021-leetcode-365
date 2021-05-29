# 单调栈

## 适用场景

- 具有相对位置（比如相对当前元素的下一个更大元素）
- 比较大小

## 特点

- 利用栈先进先出的特点，保持栈顶元素为当前元素的最近关系元素。
- 保持栈中的元素单调递增或者递减，单调递增称为单调递增栈，单调递减称为单调递减栈。
- 使用栈存储一系列有特色的树（递增或者递减），用于再比较。

## 例题和思路

### 基础例题

 [#496. 下一个更大元素 I](https://leetcode-cn.com/problems/next-greater-element-i/)

思路：

1. 从右侧开始比较，因为题目是比较当前的元素的下一个更大元素，从右开始更方便
2. 每次迭代时，将比小于或者等于当前数的元素删除，此时
   - 栈顶为当前数的右侧第一个最大元素；如果栈空，则无比当前元素更大的数。
   - 当前数变为下一个迭代元素存在的右侧最大数
3. 逻辑如下

```bash
// 普通逻辑，时间复杂度为O(N^2)
let nextMax; // 这个为当前数的下一个最大数取值
if(arr[i] < arr[i+1]|| arr[i+2]|| arr[i+3]|| ... arr[n]){
   nextMax = arr[i+x];
}else{
    nextMax = -1;
}

// 递归栈的逻辑，时间复杂度为O(N)
假设存在元素arr[i-1]、arr[i]、arr[i-1];
let nextMax;
arr[i]与arr[i-1]可能存在以下关系:
	arr[i] < arr[i+1]，此时arr[i]的nextMax为arr[i+1];
    arr[i] >= arr[i+1], 此时arr[i]的nextMax需要向右比较获得，
    	如果，右侧存在比arr[i+1]大的数，此时nextMax为arr[x]
    	否则，nextMax为-1
arr[i-1]与arr[i]可能存在以下关系：
	arr[i-1]< arr[i]，此时arr[i-1]的nextMax为arr[i];
	arr[i-1]>= arr[i]
		arr[i]的nextMax为-1，则arr[i-1]的nextMax也为-1，此时，没有比arr[i-1]更大的数（也就是空栈）
		arr[i]的nextMax为arr[x]，那么，比较arr[i-1]与nextMax后索引中比nextMax要大的数，即可得出结果（也就是递增栈）
```

### 相关例题

- [下一个更大元素 I](https://leetcode-cn.com/problems/next-greater-element-i) 
- [ 下一个更大元素 II](https://leetcode-cn.com/problems/next-greater-element-ii) 
- [ 下一个更大元素 III](https://leetcode-cn.com/problems/next-greater-element-iii) 
- [84. 柱状图中最大的矩形](https://leetcode-cn.com/problems/largest-rectangle-in-histogram/)
- [739. 每日温度](https://leetcode-cn.com/problems/daily-temperatures/)
- [42. 接雨水](https://leetcode-cn.com/problems/trapping-rain-water/) 
- [ 316. 去除重复字母（困难）](https://leetcode-cn.com/problems/remove-duplicate-letters/)
- [901. 股票价格跨度（中等）](https://leetcode-cn.com/problems/online-stock-span/)
- [ 402. 移掉K位数字](https://leetcode-cn.com/problems/remove-k-digits/)
- [581. 最短无序连续子数组](https://leetcode-cn.com/problems/shortest-unsorted-continuous-subarray/)

