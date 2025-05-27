# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. At each element, choose to either include it or exclude it.
2. Recurse with updated sum and next index.
3. If end of array is reached and sum is zero, increment count.
4. Return the total count from both include and exclude cases.
5. Final result is the total number of valid subsets.  

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: D Vergin Jenifer
Register Number: 212223240174
def subsetSum(arr, n, i,sum, count):
    if(i==n):
        if(sum==0):
            count+=1
        return count
    count=subsetSum(arr,n,i+1,sum - arr[i],count)
    count=subsetSum(arr,n,i+1,sum,count)
    return count






arr=[]
size=int(input())
for j in range(size):
    value=int(input())
    arr.append(value)
sum = int(input())
n = len(arr)
 
print(subsetSum(arr, n, 0, sum, 0))
*/
```

## Output:

![image](https://github.com/user-attachments/assets/b9033c3b-b6a1-48e0-bddc-7084de96be6d)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
