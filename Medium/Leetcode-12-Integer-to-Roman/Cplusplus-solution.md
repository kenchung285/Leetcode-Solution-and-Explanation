# Leetcode 12 Integer to Roman

 - **Hash Table**
 - **Medium**

## Performance
![performance](assets/Cplusplus-performance.png)

## Complexity
 * Time complexity : $O(n)$
 * Space complexity : $O(1)$

## Algorithm

## Reference Code
```c++
class Solution {
public:
    string intToRoman(int num) {
        string result = "";
        int x;
        
        x = num / 1000;
        for(int i = 0; i < x; i++)
            result += "M";
        num %= 1000;
        
        if (num >= 900){
            result += "CM";
            num -= 900;
        }else if (num >= 500){
            result += "D";
            num -= 500;
        }else if (num >= 400){
            result += "CD";
            num -= 400;
        }
    
        x = num / 100;
        for(int i = 0; i < x; i++)
            result += "C";
        num %= 100;
        
        if (num >= 90){
            result += "XC";
            num -= 90;
        }else if (num >= 50){
            result += "L";
            num -= 50;
        }else if (num >= 40){
            result += "XL";
            num -= 40;
        }
        
        x = num / 10;
        for(int i = 0; i < x; i++)
            result += "X";
        num %= 10;
        
        if (num >= 9){
            result += "IX";
            num -= 9;
        }else if (num >= 5){
            result += "V";
            num -= 5;
        }else if (num >= 4){
            result += "IV";
            num -= 4;
        }
        
        for(int i = 0; i < num; i++)
            result += "I";
        
        return result;
    }
};
```