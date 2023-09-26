# DSA-Bit-Manipulation

### 1.Number of 1 Bits

#### Method 1 : Logic (Implementation of Brian Kernighan’s Algorithm)

```cpp
int countSetBits(int number){
    int totalCount ;
    while(number){
        number =number&(number-1);
        totalCount++;
    }
    return totalCount++;
    }
```
__Time Complexity:__ O(log n);
__Space Complexity:__ O(1);

#### Method 2 : Logic (Recursion)

```cpp
int countSetBits(int number){
    if(number==0)
      return 0;

    //if last bit set add 1 else add 0
      return number&1 + setBits(number>>1);
    
    }
```
__Time Complexity:__ O(log n);
__Space Complexity:__ O(1);

__Note:__ We can solve this using map,array etc.But Best Approach Discuss above.

