# DSA-Bit-Manipulation



### Even and Odd Check
```cpp
if(number & 1){
    //number is odd
    //  3 =11
    //& 1 =01
    //    =01
}
else //number is even
  //  2 =10
    //& 1 =01
    //    =00
```

### Swap two numbers without third variable
```cpp
a =5;  //101
b =7;   //111

a =a^b;  //010
b =a^b;  //101;  5 
a =a^b;  //111    7
 //swap using xor operator
```




### Find ith bit ?(Only Logic)


```cpp
int a = 32 //100000
int bitMask=1;
bitMask =bitMask<<i
 //Left shit bitMask<<ith
int ansBit = a&bitMask;


```
### set the ith bit ?

```cpp
int a = 32 //100000
int bitMask=1;
bitMask =bitMask<<i
 //Left shit bitMask<<ith
int ansBit = a | bitMask; 
//Just operaor will be or 


```
### clear the ith bit ?

```cpp
int a = 36 //100100
int bitMask=1;
bitMask =bitMask<<i
 //Left shit bitMask<<ith

bitMask =~bitMask;  //111011

int ansBit = a & bitMask;     //100000




```

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

### First Two Non repeating Number [Reference](https://www.geeksforgeeks.org/non-repeating-element/)

[ Find Rightmost Set Value](https://www.educative.io/answers/how-to-find-the-position-of-the-rightmost-set-bit-of-an-integer)
```cpp
 vector<int> singleNumber(vector<int> nums) 
    {
        int length =nums.size();
        int valueOfXor=0;
        for(int i=0;i<length;++i)
        //after xor operation duplicate value will be remove
            valueOfXor=valueOfXor^nums[i];
    
    
    //find right most set bits
    int rightMostSetBits=valueOfXor&~(valueOfXor-1);
   
   vector<int>nonRepeatingNumber(2);
    
    //first divide the array between two parts depends on set bit.
     for(int i=0;i<length;++i){
         
         if(rightMostSetBits&nums[i])
             nonRepeatingNumber[1]^=nums[i];
          else 
             nonRepeatingNumber[0]^=nums[i];
         
     }
    sort(nonRepeatingNumber.begin(),nonRepeatingNumber.end());
     
     return nonRepeatingNumber;
    }```