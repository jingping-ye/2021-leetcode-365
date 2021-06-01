# 字符串

```js
// 初始化一个字符串并赋值为abcd
let str = "abcd"; 

// 获取字符串的长度
str.length;

// 在字符串尾部插入一个字符e
str = `${str}e;`
str = str + 'e';

// 删除字符串尾部的字符
str = str.slice(0,str.length-1)

// 返回从索引pos开始的，长度为len的子字符串
str = str.substr(pos, len);

// 找出给定字符"a"在字符串中的索引（从左至右）
str.indexOf('a');

// 找出给定字符"a"在字符串中的索引（从右至右）
str.lastIndexOf('a');

// 重复"abc"3次生成一个新字符
str = "abc".repeat(3);

// 获取索引为i的字符
str[i];
str.charAt(i);

// 将字符串转为Array
    let arr1 = Array.from(str);
let arr2 = str.split("");
let arr3 = [...str];
```

