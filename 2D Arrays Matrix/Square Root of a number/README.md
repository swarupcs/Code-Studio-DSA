# Square Root of a number

https://www.codingninjas.com/studio/problems/square-root-integral_893351

### Problem statement
```
You are given a positive integer ‘n’.

Your task is to find and return its square root. If ‘n’ is not a perfect square, then return the floor value of sqrt(n).

```

### Example:
```
Input: ‘n’ = 7

Output: 2
```

### Explanation:
```
The square root of the number 7 lies between 2 and 3, so the floor value is 2.
```

## Java Solution
### Approach 1 

### Optimal Approach(Using binary search): 
```
We are going to use the Binary Search algorithm to optimize the approach.

The primary objective of the Binary Search algorithm is to efficiently determine the appropriate half to eliminate, thereby reducing the search space by half. It does this by determining a specific condition that ensures that the target is not present in that half.

Now, we are not given any sorted array on which we can apply binary search. But, if we observe closely, we can notice that our answer space i.e. [1, n] is sorted. So, we will apply binary search on the answer space.
```

### Algorithm:

```
The steps are as follows:

We will declare a variable called ‘ans’.

1. Place the 2 pointers i.e. low and high: Initially, we will place the pointers. The pointer low will point to 1 and the high will point to n.
2. Calculate the ‘mid’: Now, inside a loop, we will calculate the value of ‘mid’ using the following formula:
mid = (low+high) // 2 ( ‘//’ refers to integer division)
3. Eliminate the halves accordingly: 
    a) If mid*mid <= n: On satisfying this condition, we can conclude that the number ‘mid’ is one of the possible answers. So, we will store ‘mid’ in the variable ‘ans’. But we want the maximum number that holds this condition. So, we will eliminate the left half and consider the right half(i.e. low = mid+1).
    b)Otherwise, the value mid is larger than the number we want. This means the numbers greater than ‘mid’ will not be our answers and the right half of ‘mid’ consists of such numbers. So, we will eliminate the right half and consider the left half(i.e. high = mid-1).
4. Finally, the ‘ans’ variable will be storing our answer. In addition to that, the high pointer will also point to the same number i.e. our answer. So, we can return either of the ‘ans’ or ‘high’.
The steps from 2-3 will be inside a loop and the loop will continue until low crosses high.
```

```
import java.util.* ;
import java.io.*; 

public class Solution {

	public static int sqrtN(long N) {
		/*
		 * Write your code here
		 */
		long low = 1;
		long high = N;
		while(low <= high) {
			long mid = (low+high)/2;
			long val = (mid * mid);
			if(val <= N) {
				low = mid + 1;
			} else {
				high = mid - 1;
			}
			
		}
		
		return (int)high;
	}
}

```

