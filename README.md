# Alogrithm-with-swift
Sort algorithm With Swift 

Goal: To sort an array from low to high (or high to low). Complexity O(N^2) 

You are given an array of numbers and need to put them in the right order. The selection sort algorithm divides the array into two parts: the beginning of the array is sorted, while the rest of the array consists of the numbers that still remain to be sorted. 

1-Find the lowest number in the array. You must start at index 0, loop through all the numbers in the array, and keep track of what the lowest number is.
 2-Swap the lowest number with the number at index 0. Now, the sorted portion consists of just the number at index 0.

 3-Go to index 1.

 4- Find the lowest number in the rest of the array. This time you start looking from index 1. Again you loop until the end of the array and keep track of the lowest number you come across.

 5- Swap the lowest number with the number at index 1. Now, the sorted portion contains two numbers and extends from index 0 to index 1.

 6-Go to index 2. 

7- Find the lowest number in the rest of the array, starting from index 2, and swap it with the one at index 2. Now, the array is sorted from index 0 to 2; this range contains the three lowest numbers in the array. And continue until no numbers remain to be sorted.

It is called a "selection" sort because at every step you search through the rest of the array to select the next lowest number. 
EXample Array = [4,2,6,3,5,2,1]

Iteration number 1: [1, 4, 6, 3, 5, 2, 2] 

Iteration number 2: [1, 2, 6, 4, 5, 3, 2] 

Iteration number 3: [1, 2, 2, 6, 5, 4, 3] 

Iteration number 4: [1, 2, 2, 3, 6, 5, 4] 

Iteration number 5: [1, 2, 2, 3, 4, 6, 5]

Iteration number 6: [1, 2, 2, 3, 4, 5, 6]
/////
code:



import UIKit

var arr = [4,2,6,3,5,2,1]

for x in 0..<arr.count-1

{

    var min:Int = arr[x]// for store the minimum number
    for y in x+1..<arr.count
    
    {
    
        if (min < arr[y])
        {
            arr[x] = min
            
        }
        
        else
        {
            arr[x] = arr[y]
            arr[y] = min
            min = arr[x]
        }
        
    }
}
print("Final result \(arr)")
