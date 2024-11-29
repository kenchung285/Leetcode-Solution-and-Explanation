# Leetcode 12 Integer to Roman

 - **Hash Table**
 - **Medium**

## Performance
![performance](assets/Csharp-performance.png)

## Complexity
 * Time complexity : $O(n)$
 * Space complexity : $O(1)$

## Algorithm

## Reference Code
```csharp
public class Solution {
    public string IntToRoman(int num) {
        string[] ones = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
        string[] tens = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        string[] hrns = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        string[] thds = {"", "M", "MM", "MMM"};

        return thds[num/1000] + hrns[(num%1000)/100] + tens[(num%100)/10] + ones[num%10];
    }
}
```