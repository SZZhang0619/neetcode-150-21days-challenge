# 217. Contains Duplicate(包含重複項)

## Description(描述)：

Given an integer array `nums,` return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.  
(給定一個整數陣列 `nums`，如果任何值在陣列中至少出現兩次 ，則傳回 `true`，如果每個元素都是不同的，則傳回 `false`。)

### Example(範例) 1:
>Input(輸入): nums = [1,2,3,1]  
Output(輸出): true  
Explanation(解釋):The element 1 occurs at the indices 0 and 3.  
(元素 1 出現在索引 0 和 3 處)

### Example(範例) 2:
>Input(輸入): nums = [1,2,3,4]  
Output(輸出): false  
Explanation(解釋):All elements are distinct.  
(所有元素都是不同的)

### Example(範例) 3:
>Input(輸入): nums = [1,1,1,3,3,4,3,2,4,2]  
Output(輸出): true

## Constraints(提示):
- 1 <= nums.length <= 10^5
- -10^9 <= nums[i] <= 10^9

### Code(程式碼):

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
    let mySet = new Set();
    for(const num of nums){ 
        if(mySet.has(num)){
            return true;
        }
        mySet.add(num);
    }
    return false
};
```

### Approach(解題思路):

- 使用 Set 資料結構儲存已經出現過的數字。
- 在遍歷 nums 時，如果當前數字已經在 Set 中出現過，立即回傳 true。
- 若遍歷結束都沒有重複，回傳 false。