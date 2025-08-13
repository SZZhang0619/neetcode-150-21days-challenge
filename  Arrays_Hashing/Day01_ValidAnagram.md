# 242. Valid Anagram(有效字謎)

## Description(描述)：

Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.
(給定兩個字串 `s` 和 `t`，如果 `t` 是 `s` 的字謎，否則返回 `false`。)

### Example(範例) 1:
>Input(輸入): s = "anagram", t = "nagaram"  
Output(輸出): true  

### Example(範例) 2:
>Input(輸入): s = "rat", t = "car"  
Output(輸出): false

## Constraints(提示):
- 1 <= s.length, t.length <= 5 * 10^4
- `s` and `t` consist of lowercase English letters(`s` 和 `t` 由小寫英文字母組成)

### Code(程式碼):

```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
    if (s.length !== t.length) return false;
    
    let myMap = {}
    for(let i = 0; i < s.length; i++){
        myMap[s[i]] = (myMap[s[i]] || 0) + 1;
        myMap[t[i]] = (myMap[t[i]] || 0) - 1;
    }

    for(const char of s){
        if(myMap[char] !== 0){
            return false
        }
    }
    
    return true
}
```

### Approach(解題思路):

1. 如果 t 是 s 的 anagram，則兩個字串中每個字母的出現次數必須相等。
2. 使用一個 myMap 去記錄兩者的字母差異，最後檢查是否全部為 0。
