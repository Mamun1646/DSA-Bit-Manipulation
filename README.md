# DSA-Bit-Manipulation

### Number of 1 Bits
logic 
```cpp
int countSetBits(int number){
    int totalCount ;
    while(number){
        number =number&(number-1);
        totalCount++;
    }
    return totalCount++;
}
