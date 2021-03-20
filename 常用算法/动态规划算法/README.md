# 动态规划

动态规划基本是普通递归的优化。如果我们看到一个递归方法重复调用（入参相同），那么我们即可使用动态规划进行优化。方法很简单：存储相同子问题结果，防止后续需要时重复计算。

动态规划的优点：

- 对于递归来说，其时间复杂度往往是指数级，而通过动态规划，可以将时间复杂度转为线型。
- 对于递归来说，计算时间复杂度，我们需要先计算子问题的个数，这是相对隐蔽的；而对于动态规划来说，如果采用备忘录的方式，那么使用迭代，时间复杂度计算相对较快。

## 通用模式

- DP表：自底而上，使用DP表从底算起，直至最终值。这里一般采用迭代的方法。
- 备忘录：自顶而下，仍然采用递归的方式，方式对于相同输入的值进行了存储，所以避免了重复计算，以降低时间复杂度。

## 优化步骤

1. 重叠子问题（重复子问题）
2. 最优子结构

步骤：

1. 判定是否是DP问题
2. 使用最少参数来编写一个状态表达式
3. 用公式表达状态的关系（数学函数）
4. 使用DP表或者备忘录的形式解决问题

## 判断能够用DP解决？

- 求极值（最大或者最小值）、
- 确定条件下的计数问题或者概率问题

## 定义状态

> 关键部分

- DP问题基本是状态和状态转移问题。

- 如何定义状态？

- 状态可以认为是一系列参数集，这些参数集可以用来表明确定的位置。参数集应该尽可能的小以减少状态空间。

- 比如背包问题，其状态就是两个参数：指数和权重。通过DP(index, weight)我们可以得到最大的利润，当index和weight变化时，因为index和weight的变化可以用来表示一个具体的子问题

## 构造状态之间的关系

> 最难的部分，需要直觉、观察和练习

比如：给定n个数，选择k个数的和相加为N（允许重复选择和不同顺序），求k的可能数字

例如: [1,3, 5] 6

1. 列出所有可能，找规律 => `state(n) = state(n-1) + state(n-3) + state(n-5)`

```js
static int solve(int n)
{ 
   // base case
   if (n < 0) 
      return 0;
   if (n == 0)  
      return 1;  
 
   return solve(n-1) + solve(n-3) + solve(n-5);
}    
```



## 使用备忘录或者DP表优化state

> 最简单部分

存储状态的答案，以便下次调用

```js
// initialize to -1
public static int[] dp = new int[MAXN];

// this function returns the number of 
// arrangements to form 'n' 
static int solve(int n)
{ 
// base case
if (n < 0) 
	return 0;
if (n == 0)
	return 1;

// checking if already calculated
if (dp[n]!=-1) 
	return dp[n];

// storing the result and returning
return dp[n] = solve(n-1) + solve(n-3) + solve(n-5);
}

// This code is contributed by Dharanendra L V.

```

## DP表和备忘录

1. DP表：自底而上；从具体到抽象
2. 备忘录：自顶而下；从抽象到具体

### DP表

从底层开始，累积值一直到顶层。

一般来说，base case都还是 p[x]~p[0]，最终返回d[n]。

- dp表示按照顺序填充的，我们直接访问dp表就可以获取最终状态



```js
// Tabulated version to find factorial x.
int dp[MAXN];

// base case
int dp[0] = 1;
for (int i = 1; i< =n; i++)
{
    dp[i] = dp[i-1] * i;
}
```

### 备忘录方法

```js
// Memoized version to find factorial x.
// To speed up we store the values
// of calculated states

// initialized to -1
int dp[MAXN]

// return fact x!
int solve(int x)
{
    if (x==0)
        return 1;
    if (dp[x]!=-1)
        return dp[x];
    return (dp[x] = x * solve(x-1));
}
```

- 存储最近的状态值

| #          | DP表                                                   | 备忘录                                           |
| ---------- | ------------------------------------------------------ | ------------------------------------------------ |
| 状态转换   | 状态转换关系难以发现                                   | 状态转换关系容易发现                             |
| 代码       | 多条件时，代码变得复杂                                 | 代码简单而且复杂度更低                           |
| 速度       | 快，因为可以直接从表中访问之前的状态                   | 慢，因为许多递归调用和语句声明                   |
| 子问题解决 | 如果所有的子问题必须解决一遍，那么DP表的方法具有优势。 | 如果定义的子问题无需解决，那么备忘录方法具有优势 |
| 表格访问   | 从第一项开始，逐渐填充                                 | 无需填写所有表内容，按需填写即可                 |

