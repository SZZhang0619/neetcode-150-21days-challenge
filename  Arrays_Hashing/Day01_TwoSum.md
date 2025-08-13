# 1. Two Sum(兩數之合)

## Description(描述)：

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

(给定一個整數陣列 nums 和一個整數目標值 target，請你在該陣列中找出和為目標值 target  的那兩個整数，並回傳它們的陣列索引。

你可以假設每種輸入只會對應一個答案，並且你不能使用兩次相同的元素。

你可以按任意顺序回傳答案。)

### Example(範例) 1:
>Input(輸入): nums = [2,7,11,15], target = 9  
Output(輸出): [0,1]  
Explanation(解釋): Because nums[0] + nums[1] == 9, we return [0, 1].
(元素 1 出現在索引 0 和 3 處)

### Example(範例) 2:
>Input(輸入): nums = [3,2,4], target = 6  
Output(輸出): [1,2] 

### Example(範例) 3:
>Input(輸入): nums = [3,3], target = 6  
Output(輸出): [0,1]

## Constraints(提示):
- 2 <= nums.length <= 10^4
- -10^9 <= nums[i] <= 10^9
- -10^9 <= target <= 10^9
- Only one valid answer exists.

### Code(程式碼):

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let map = new Map()
    for(let i = 0; i < nums.length; i++){
        let num = target-nums[i];
        if(map.has(num)){
            return [map.get(num), i];
        }
        map.set(nums[i], i);
    }
    return
};
```

### Approach(解題思路):

1. 逐一遍歷陣列；對於每個元素計算補數，若補數已存在於 Map（代表先前元素可與當前元素組成目標值）則立即回傳；否則將當前元素與其索引存入 Map 後續繼續檢查。

