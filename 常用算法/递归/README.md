# 递归

## 数学描述

计算从1加到100

```js
{
    f(n) = 1; // n==1; --> base case
    f(n) = n + f(n-1); // n>1
}
```

## 基准条件(base condition)

如上

## 栈溢出(stack overflow)

当未定义基准条件或者不能达到基准条件，会因为内存耗尽而出现栈溢出

## 直接递归(direct recursion)和间接递归(indirect recursion)

### 直接递归

```js
function funcA(){
    funcA
}
```

### 间接递归

```js
function funcA(){
    funcB();
}

function funcB(){
    funcA();
}
```

## 尾递归(tail-recursion)

> 递归方法是函数最后执行的。

```js
function rec(num){
    if(n<0){
        return;
    }
    console.log("num===", num);
   	rec(num - 1);
}
```

- 尾递归：快速排序
- 非尾递归：归并排序

## 内存分配

```js
function rec(num) {
    if (num < 1) {
      return;
    } else {
          console.log("num-before", num);
          rec(num - 1);
          console.log("num-after", num);
        }
    }
rec(3);
```



