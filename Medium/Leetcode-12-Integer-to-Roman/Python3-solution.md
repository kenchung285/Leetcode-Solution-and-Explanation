# Leetcode 12 Integer to Roman

 - **Hash Table**
 - **Medium**

## Performance
![performance](assets/Python3-performance.png)

## Complexity
 * Time complexity : $O(n)$
 * Space complexity : $O(1)$

## Algorithm

## Reference Code
```python
class Solution:
    def intToRoman(self, num: int) -> str:
        m = {
            "I":  1,
            "IV": 4,
            "V":  5,
            "IX": 9,
            "X":  10,
            "XL": 40,
            "L":  50,
            "XC": 90,
            "C":  100,
            "CD": 400,
            "D":  500,
            "CM": 900,
            "M":  1000,
        }

        ans = ""

        for symbol, value in sorted(m.items(), key=lambda item: item[1], reverse=True):
            while num >= value:
                ans += symbol
                num -= value
        
        return ans
```