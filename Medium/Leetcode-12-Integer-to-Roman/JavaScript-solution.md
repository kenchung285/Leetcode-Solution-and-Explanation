# Leetcode 12 Integer to Roman

 - **Hash Table**
 - **Medium**

## Performance
![performance](assets/JavaScript-performance.png)

## Complexity
 * Time complexity : $O(n)$
 * Space complexity : $O(1)$

## Algorithm

## Reference Code
```JavaScript
/**
 * @param {number} num
 * @return {string}
 */
var intToRoman = function(num) {
    let n = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1];
    let s = ['M', 'CM', 'D', 'CD', 'C', 'XC', 'L', 'XL', 'X', 'IX', 'V', 'IV', 'I']
    
    let ans = '';
    for(let ind = 0 ; ind < n.length ; ind++)
        while (num >= n[ind]) {
            ans += s[ind]
            num -= n[ind]
        }
    return ans;
};
```