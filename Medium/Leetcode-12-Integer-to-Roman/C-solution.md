# Leetcode 12 Integer to Roman

 - **Hash Table**
 - **Medium**

## Performance
![performance](assets/C-performance.png)

## Complexity
 * Time complexity : $O(n)$
 * Space complexity : $O(1)$

## Algorithm

## Reference Code
```c
typedef struct {
    const int value;
    const char* string;
    const int length;
} Roman;

const Roman romans[] = { 
    { 1, "I", 1 }, 
    { 4, "IV\0", 2 }, 
    { 5, "V\0", 1 }, 
    { 9, "IX\0", 2 }, 
    { 10, "X\0", 1 }, 
    { 40, "XL\0", 2 }, 
    { 50, "L\0", 1 }, 
    { 90, "XC\0", 2 }, 
    { 100, "C\0", 1 }, 
    { 400, "CD\0", 2 }, 
    { 500, "D\0", 1 }, 
    { 900, "CM\0", 2 }, 
    { 1000, "M\0", 1 } 
};
const int romansLength = sizeof(romans) / sizeof(romans[0]);

char* intToRoman(int num) {
    char* result = malloc(sizeof(char) * 30);
    int l = 0;
    for (int i = romansLength - 1; i >= 0; i--) {
        for (int j = num / romans[i].value; j > 0; j--) {
            strcpy(result + l, romans[i].string);
            l += romans[i].length;
        }

        num %= romans[i].value;
    }

    return result;
}
```