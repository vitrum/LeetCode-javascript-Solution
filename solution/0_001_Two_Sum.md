# 1. Two Sum

## Description

Given an array of integers, return **indices **of the two numbers such that they add up to a specific target.

You may assume that each input would have **exactly **one solution, and you may not use the same element twice.

**Example:**

```js
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,

return [0, 1].
```

### 分析和方案

题目意思是查找给定的数组中，哪两项数字的和是指定，并返回对应项目的序号。

简单的解法是两次遍历数组，判断每一项和其他项的合。

```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {

    var map = {};
    for(var i = 0 ; i < nums.length ; i++){
        var v = nums[i];

        for(var j = i+1 ; j < nums.length ; j++ ){
            if(  nums[i] + nums[j]  == target ){
                return [i,j];
            }
        }

    }
};
```



这样的运算时间复杂度是O\(n^2\)，效率不够好。

还可以利用数组下标的方法，建立一个中转MAP数组，下标为nums\[i\]的值，值存在nums数组的下标，通过计算target和nums\[i\]的差是不是在nums数组内，来判断是否能返回。



```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    var a = [];
    for (var i = 0, len = nums.length; i < len; i++) {
        var tmp = target - nums[i];
        if (a[tmp] !== undefined) return [a[tmp], i];
        a[nums[i]] = i;
    }
};
```



