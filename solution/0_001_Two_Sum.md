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

### 分析

## Hints

## My solution

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



