---
nav:
  title: Components
  path: /components
---

## Leetcode

1、给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。

```tsx
import React from 'react';
import { Leetcode } from 'bjg-blog';

const nums = [2, 11, 7, 15], target = 9

const twoSum = (arr, target) => {
  const len = arr.length
  for (let i = 0; i < len; i++) {
    const numTarget = target - arr[i]
    for (let j = i + 1; j < len; j++) {
      if (arr[j] === numTarget) {
        return [i, j]
      }
    }
  }
  return []
}

const twoSum2 = (arr, target) => {
  const len = arr.length,
  map = new Map();
  for (let i = 0; i < len; i++) {
    const numTarget = target - arr[i]
    if(map.has(numTarget)) {
      return [map.get(numTarget), i]
    }
    map.set(arr[i], i)
  }
  return []
}

// console.log(twoSum2(nums, target))


export default () => (
  <Leetcode 
    demo="给定 nums = [2, 7, 11, 15], target = 9。因为 nums[0] + nums[1] = 2 + 7 = 9，所以返回 [0, 1]"
  />);
```

