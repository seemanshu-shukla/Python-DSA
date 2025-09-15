


# Searching Algorithm:

## 1. Arrays: 
### Refer: [Notes/Searching_And_Sorting_Algorithm/Introduction_to_arrays.pdf](Notes/Searching_And_Sorting_Algorithm/Introduction_to_arrays.pdf)
### Code:
```python
l1 = []

l1.append(1)
l1.append(1.5)
l1.append('python')

print(l1[0])


import array ## Since array is not builtin data type or method in Python we are importing array library to implement it

arr = array.array('i',[1,2,3,4,5])  ## 'i' represents data structure of array which here is interger
print(arr)
arr[0] = 10
print(arr)
```

## 2. Linear Search Algorithm:
### Refer: [Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf](Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf)
### Coding Exercise 54: Linear Search Algorithm
#### **Problem Description:**

- **Title:** Linear Search in a List
- **Description:** Implement a function `linear_search` that performs a linear search on a list to find a given value. The function should return the index of the first occurrence of the value in the list, or -1 if the value is not found.
- **Parameters:**
- `arr`: A list of elements (can be empty)
- `target`: The value to search for in the list
- **Return:**
- The index of the first occurrence of the target value (0-based), or -1 if not found

#### **Examples:**
1. `linear_search([3, 7, 2, 5], 2)` should return `2`
2. `linear_search([1, 1, 2, 1], 1)` should return `0`
3. `linear_search([], 5)` should return `-1`
4. `linear_search([4, 2, 8], 6)` should return `-1`
    ```python
    def linear_search(arr, target):
        # TODO: Implement this function
        pass

        for i in range(len(arr)):
            if arr[i] == target:
                return i
                
            else:
                continue
            
        return -1
                
    ```

## 3.  Binary Search Algorithm:
### Refer: [Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf](Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf)
### Code:
```python
# print(5//2)
def binary_search(arr,target):
    size = len(arr)

    start =0
    end = size-1

    while(start <= end):
        mid = (start +end)//2

        if(arr[mid]==target):
            return mid # Found the Target
        
        elif ( arr[mid] > target):
            end = mid -1
        elif(arr[mid]< target):
            start = mid+1
        
    return -1


sorted_list = [10,23,35,45,50,70,85]
target = 85

result = binary_search(sorted_list,target)
print(result)
```

# Sorting Algorithm:

## 1. Bubble Sort Algorithm:
### Refer: [Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf](Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf)
### Coding Exercise 55: Bubble Sort Algorithm

You are given a list of integers. Write a Python function to sort the list in ascending order using the **Bubble Sort** algorithm. Bubble Sort repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The process is repeated until the list is sorted.

#### Parameters:
- **lst** (List of integers): The list to be sorted.

#### Returns:
- A list of integers sorted in ascending order.

#### Example:
1. **Input**: `lst = [64, 34, 25, 12, 22, 11, 90]`
   **Output**: `[11, 12, 22, 25, 34, 64, 90]`
2. **Input**: `lst = [5, 1, 4, 2, 8]`
   **Output**: `[1, 2, 4, 5, 8]`

    ```python
    def bubble_sort(lst):
        # Your code goes here
        pass
    
        for i in range(len(lst)-1): ## Number of passes
            for j in range(0,len(lst)-1-i):  ## For iteration over the given pass. -1 due to bubble of 2 element and -i since after every pass largest element for that pass will be at the right pos
                if lst[j] <= lst[j+1]:
                    continue
                else:
                    lst[j],lst[j+1] = lst[j+1],lst[j]
                
            
        return lst
    
    ```

## **NOTE**:
- In Bubble Sort with every pass, we were getting the respective largest elements (1st largest/2nd largest/3rd largest..) at their right position.
- Whereas, in Selection Sort we try to get the respective smallest elements (1st smallest/2nd smallest/3rd smallest..) at their right position.

## 2. Selection Sort Algorithm:
### Refer: [Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf](Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf)
### Coding Exercise 56: Selection Sort

#### Selection Sort Algorithm

You are given a list of integers. Write a Python function to sort the list in ascending order using the **Selection Sort** algorithm. Selection Sort works by repeatedly finding the minimum element from the unsorted part of the list and swapping it with the first element of the unsorted part.

**Parameters:**
- `lst` (List of integers): The list to be sorted.

**Returns:**
- A list of integers sorted in ascending order.

**Example:**
1. **Input:** `lst = [64, 25, 12, 22, 11]`  
   **Output:** `[11, 12, 22, 25, 64]`

2. **Input:** `lst = [29, 10, 14, 37, 13]`  
   **Output:** `[10, 13, 14, 29, 37]`

    ```python
    def selection_sort(lst):
        # Your code goes here
        pass
        min_ele = float('inf')
    
        for i in range(len(lst)-1): ## Number of passes
            for j in range(i,len(lst)): ## Traversing in each pass
                if lst[j] < min_ele:
                    min_ele = lst[j]
                    min_index = j
                
                else:
                    continue
                
            lst[i],lst[min_index] = lst[min_index],lst[i]
            min_ele = float('inf')
            
        return lst
    
    ```
## **Note:**
- In Bubble and Selection sort, we perform swapping of elements to sort the given elements.
- Whereas, Insertion sort is similar to how we arrange the numbered deck of cards in order while playing cards. So, here, instead of swapping, we perform shifting of elements(wrt index) for sorting the given elements.


## 3. Insertion Sort Algorithm:
### Refer: [Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf](Notes/Searching_And_Sorting_Algorithm/Linear_Search_Algorithm.pdf)
### Coding Exercise 57: Insertion Sort

#### Insertion Sort Algorithm

You are given a list of integers. Write a Python function to sort the list in ascending order using the Insertion Sort algorithm. Insertion Sort works by building a sorted section of the list, one element at a time, by inserting each new element into its proper position within the already sorted section.

#### Parameters:
- `lst` (List of integers): The list to be sorted.

#### Returns:
- A list of integers sorted in ascending order.

#### Example:
1. **Input:** `lst = [12, 11, 13, 5, 6]`  
   **Output:** `[5, 6, 11, 12, 13]`

2. **Input:** `lst = [31, 41, 59, 26, 41, 58]`  
   **Output:** `[26, 31, 41, 41, 58, 59]`

    ```python
    def insertion_sort(lst):
        # Your code goes here
        pass
    
        for current in range(1,len(lst)):
            currentCard = lst[current]
            currentPos = current-1 ## It will go from current-1 to 0
            
            while(currentPos >= 0):
                if currentCard < lst[currentPos]:
                    lst[currentPos+1] = lst[currentPos]
                    currentPos = currentPos-1
                
                else:
                    break
            
            lst[currentPos+1] = currentCard
            
        return lst
    ```

# Binary Search Practice Questions:

## Coding Exercise 58: Count Negative Numbers in a Sorted Matrix

**Asked in Companies:**
- Samsung
- Oyo
- Groww
- Dell

**Description:**
You are given an \\( m \\times n \\) matrix `grid` where each row and column is sorted in non-increasing order. Your task is to return the number of negative numbers present in the matrix.

**Parameters:**
- `grid` (List[List[int]]): A 2D matrix with dimensions \\( m \\times n \\), where each row and each column is sorted in non-increasing order.

**Return Values:**
- Integer: The count of negative numbers in the matrix.

**Example:**

```plaintext
Input: grid = [[4, 3, 2, 1], [3, 2, 1, -1], [1, 1, -1, -2], [-1, -1, -2, -3]]
Output: 7
Explanation: There are 7 negative numbers in the matrix.

Input: grid = [[3, 2], [1, 0]]
Output: 0
Explanation: There are no negative numbers in the matrix.
```

```python
def countNegatives(grid):
    # Implement your solution here
    pass
    
    ## Sol^1 : Naive Approach Time Complexity O(m*n)
    # countNegatives = 0
    # for i in grid:
    #     for j in i:
    #         if j < 0:
    #             countNegatives = countNegatives + 1
    #         else:
    #             continue
            
    # return countNegatives
    
    ## Sol^ 2: Using Binary Search for finding the first negative element in each row since then all elements which are right
    ## which are right to it will be negative
    ## Time Complexity O(m*(n/2))
    
    countNegatives = 0
    NegativeFound = False
    
    for i in grid:
        start = 0
        end = len(i)-1
        while(start <= end):
            mid = (start+end)//2
            if i[mid] < 0:
                NegativeFound = True
                FirstNegative = mid
                # countNegatives = countNegatives + len(i[mid:])  ## right side all will be < 0 but not sure after left side
                end = mid-1 ## since not sure about presence of negative elements on left side
                
            else:
                ## left side will be > 0 and need to check right side
                start = mid+1
            
        if NegativeFound:
            countNegatives = countNegatives + len(i[FirstNegative:])  ## right side all will be < 0 but not sure after left side
            NegativeFound = False
        else:
            continue
        
    return countNegatives
                
                
## Mayank's Approach:
# def countNegatives(grid):
#     """
#     Count the number of negative numbers in a matrix sorted in non-increasing order
#     both row-wise and column-wise using binary search.
#     """
#     def count_negatives_in_row(row):
#         """
#         Use binary search to count the number of negative numbers in a row.
#         """
#         left, right = 0, len(row)
#         while left < right:
#             mid = (left + right) // 2
#             if row[mid] < 0:
#                 right = mid
#             else:
#                 left = mid + 1
#         return len(row) - left
    
#     total_negatives = 0
#     for row in grid:
#         total_negatives += count_negatives_in_row(row)
    
#     return total_negatives
```

## Coding Exercise 59: Find smallest letter greater than target
![image](https://github.com/user-attachments/assets/f8a4dfdf-3b8b-4580-907d-8e8c58578642)
```python
def next_greatest_letter(letters, target):
    """
    Return the smallest character in letters that is lexicographically greater than target.

    Parameters:
    letters (List[char]): Sorted array of characters.
    target (char): The target character.

    Returns:
    char: The smallest character greater than target, or the first character if no such character exists.
    """
    # Implement the function logic
    pass

    start = 0
    end = len(letters)-1
    maxFound = False
    
    while(start <= end):
        mid = (start+end)//2
        if letters[mid] > target:
            next_max = letters[mid]
            maxFound = True
            end = mid-1
        
        else:
            start = mid+1
            
    
    if maxFound:
        return next_max
        
    else:
        return letters[0]
        
    
    ## Mayank's Sol^
    ## Hint:
    ## 1. Use binary search to find the letter optimally.
    ## 2. Use the advantage of sorted array.
    ## 3.If target is larger than or equal to the last character in letters, you should return the first letter in the array because the array is circular.
    
    # # Binary search approach to find the smallest character greater than the target
    # left, right = 0, len(letters)
    
    # # Use binary search to find the correct position
    # while left < right:
    #     mid = left + (right - left) // 2
        
    #     # If the mid character is greater than the target, it could be a potential answer
    #     if letters[mid] > target:
    #         right = mid
    #     else:
    #         left = mid + 1
    
    # # If 'left' is out of bounds, return the first character (circular condition)
    # return letters[left % len(letters)]
```

## Coding Exercise 60: Find First and Last Position of Element in Sorted Array
![image](https://github.com/user-attachments/assets/1a1dfa5b-cdc6-499a-ba45-a87f04cc5534)
```python
def searchRange(nums, target):
    # Implement your solution here
    pass

    start = 0
    end = len(nums)-1
    
    while(start <= end):
        mid = (start+end)//2
        if nums[mid] == target:
            first = mid
            last = mid
            for i in range(last+1,len(nums)):  ## For Finding Last
                if nums[i] == target:
                    last = i
                else:
                    break ## Important since sorted at right side will be always greater hence no need to check further
                
            for j in range(first-1,0,-1): ## For Finding First
                if nums[j] == target:
                    first = j
                    
                else:
                    break ## Important
                
            return [first,last]
            
        elif nums[mid] > target:
            end = mid - 1
            
        else:
            start = mid + 1
            
    return [-1,-1]
    
    ## Mayank's Sol^
    ## Hint: Apply Binary Search Twice to find the First and Last occurence of the target
    
    # def findFirst(nums, target):
    #     """
    #     Find the first occurrence of the target using binary search.
    #     """
    #     left, right = 0, len(nums) - 1
    #     result = -1
    #     while left <= right:
    #         mid = (left + right) // 2
    #         if nums[mid] == target:
    #             result = mid
    #             right = mid - 1
    #         elif nums[mid] < target:
    #             left = mid + 1
    #         else:
    #             right = mid - 1
    #     return result
 
    # def findLast(nums, target):
    #     """
    #     Find the last occurrence of the target using binary search.
    #     """
    #     left, right = 0, len(nums) - 1
    #     result = -1
    #     while left <= right:
    #         mid = (left + right) // 2
    #         if nums[mid] == target:
    #             result = mid
    #             left = mid + 1
    #         elif nums[mid] < target:
    #             left = mid + 1
    #         else:
    #             right = mid - 1
    #     return result
 
    # start = findFirst(nums, target)
    # end = findLast(nums, target)
 
    # return [start, end]
```

## Coding Exercise 61: Minimum in Rotated Sorted Array


# -> List/Array Practice Questions:
## Coding Exercise 63: Maximum Element in a List
<img width="915" height="918" alt="image" src="https://github.com/user-attachments/assets/4cb45908-2dcd-468a-82ec-3f9e0ff8d930" />

```python
def find_max_element(lst):
    """
    Function to find the maximum element in a list.
    :param lst: List[int] -> List of integers
    :return: int -> The maximum element in the list
    """
    # TODO: Implement this function
    pass

    max_ele = lst[0]
    for i in range(1,len(lst)):
        if lst[i] > max_ele:
            max_ele = lst[i]
            
    return max_ele

```

## Coding Exercise 64: Sum of Elements in a List
<img width="902" height="804" alt="image" src="https://github.com/user-attachments/assets/35981e08-228f-4352-b719-cf3280ff4957" />

```python
def sum_of_elements(lst):
    """
    Function to find the sum of all elements in the list.
    :param lst: List[int] -> List of integers
    :return: int -> The sum of all elements in the list
    """
    # TODO: Implement this function
    pass

    sum_lst = lst[0]
    for i in range(1,len(lst)):
        sum_lst = sum_lst + lst[i]
        
    return sum_lst
```

## Coding Exercise 65: Palindrome List (Handle Edge Case Len 1 and Empty List)
<img width="815" height="844" alt="image" src="https://github.com/user-attachments/assets/6c55020a-d5bd-482a-a981-a8fbc769007c" />

```python
def is_palindrome(lst):
    """
    Function to check if a list is a palindrome.
    :param lst: List[int] -> List of integers
    :return: bool -> True if the list is a palindrome, False otherwise
    """
    # TODO: Implement this function
    pass

    ## Sol^ 1 using lst == lst[::-1]
    
    ## Sol^ 2 using 2 pointer approach
    
    # Edge clase
    if lst == [] or len(lst) == 1:
        return True
    
    start = 0
    end = len(lst) -1
    while(start <= end):
        if lst[start] == lst[end]:
            start = start + 1
            end = end - 1
        else:
            return False
            
    return True
```

## Coding Exercise 66: Reverse a List
<img width="789" height="874" alt="image" src="https://github.com/user-attachments/assets/91527482-1ada-40ec-9089-646697c65b5d" />

```python
def reverse_list(lst):
    """
    Function to reverse the order of elements in a list.
    :param lst: List[int] -> List of integers
    :return: List[int] -> The list with elements in reversed order
    """
    
    pass

    ## Sol^ 1 using slicing lst[::-1]
    
    ## Sol^ 2 l.sort(reverse=True) and sorted(l,reverse=True)
    
    ## Sol^ 3 using 2 pointer approach --> n/2 time complexity
    start = 0
    end = len(lst) - 1
    while(start < end):
        lst[start],lst[end] = lst[end],lst[start]
        start = start + 1
        end = end - 1
        
    return lst
```

## Coding Exercise 67: Rotate List(Handle Edge Case)
<img width="787" height="928" alt="image" src="https://github.com/user-attachments/assets/08eb1c4b-29d6-4deb-8a41-017bbd1921f5" />

```python
def rotate_left(ARR, D):
    """
    Function to rotate the list to the left by D positions.
    :param ARR: List[int] -> The list of integers
    :param D: int -> The number of positions to rotate
    :return: List[int] -> The list after rotation
    """
    # TODO: Implement this function
    pass

    ## delete first D elements and append it to the end of list
    ## if D > len(ARR) then delete D%len(ARR) elements from front and append them
    ## to the end of the list since upto D rotation ARR will be same then remainder 
    ## will be the resultant rotation
    
    if ARR == [] or len(ARR) == 1:
        return ARR
        
    if D > len(ARR):
        D = D%len(ARR)
        
    res = ARR[D:]
        
    for i in range(D):
        #res = res + list(ARR[i])
        ## list(ARR[i]) --> wrong we might need to append it in the empty list
        res.append(ARR[i])
        
    return res
    
    ## Sol^ 2 return ARR[D:] + ARR[:D]
    
## Here Time Complexity will be D instead of n
```

## Coding Exercise 68: Plus One in the Number
<img width="725" height="887" alt="image" src="https://github.com/user-attachments/assets/713c6b89-463f-4817-a19c-930d7bc8effa" />

```python
def plus_one(digits):
    """
    Function to increment a large integer represented as a list of digits by one.
    :param digits: List[int] -> List of digits representing the large integer
    :return: List[int] -> The list representing the integer after incrementing
    """
    # TODO: Implement this function
    pass

    if digits[-1] < 9:
        digits[-1] = digits[-1] + 1
        return digits
        
    else:
        end = len(digits) - 1
        while(end >= 0):
            if digits[end] == 9:
                digits[end] = 0
                end = end - 1
                
            else:
                digits[end] = digits[end] + 1
                return digits
                
        if end == -1:
            return [1] + digits
        else:
            digits
```

## Coding Exercise 69: Missing Number(Sum Of First N Natural Numbers)
<img width="725" height="823" alt="image" src="https://github.com/user-attachments/assets/90e0f139-7a7d-4e4d-a081-71623f5b5a62" />

```python
def find_missing_number(nums):
    """
    Function to find the missing number in the array.
    :param nums: List[int] -> A list of distinct integers in the range [0, n]
    :return: int -> The missing number in the range
    """
    # TODO: Implement this function
    pass
    
    ## Sol^ 1: Naive or Brute Force Approach
    
    # for i in range(0,len(nums)+1):
    #     if i not in nums:
    #         return i
    ## Time complexity n*n or O(n^2)
            
            
    ## Sol^ 2: Using Sum of first n natural numbers
    n=len(nums)
    expected_sum = (n*(n+1))/2
    actual_sum = sum(nums)  ## O(n) time complexity
    
    missing = expected_sum - actual_sum
    return missing
    
    ## Time Complexity = O(n)
```

## Coding Exercise 70: Is Array Sorted?
<img width="715" height="800" alt="image" src="https://github.com/user-attachments/assets/5cb26d41-825a-4b97-a387-515558349cdf" />

```python
def is_sorted(arr):
    """
    Function to check if the given array is sorted in non-decreasing order.
    :param arr: List[int] -> A list of integers
    :return: bool -> True if the array is sorted, False otherwise
    """
    # TODO: Implement this function
    pass

    ## The array is considered sorted if every element is less than or equal to the
    ## next element.(Non-Decreasing or Ascending order)
    
    ## Naive Approach
    for i in range(len(arr)-1):
        if arr[i] <= arr[i+1]:
            continue
        else:
            return False
            
    return True
    
    ## Time Complexity = O(n)
```

## Coding Exercise 71: Move Zeros (Two-pointer approach when both pointers are pointing to 0 value):
<img width="702" height="833" alt="image" src="https://github.com/user-attachments/assets/8796f45e-c5d3-4217-b1db-b2d8683f1161" />

```python
# def move_zeroes(nums):
#     """
#     Function to move all 0's to the end of the array while maintaining the order of non-zero elements.
#     :param nums: List[int] -> A list of integers
#     :return: None -> The list is modified in place
#     """
#     # TODO: Implement this function
#     pass

    ## Sol^ 1: My custom logic
    # zeros = []
    # non_zeros = []
    
    # for i in nums:
    #     if i == 0:
    #         zeros.append(i)
            
    #     else:
    #         non_zeros.append(i)
    
    # return non_zeros + zeros
    
    ## Sol^ 2: Two Pointer Approach
    
    # p1 = 0
    # p2 = 1
    # l_num = len(nums)
    # if l_num == 0 or l_num == 1:
    #     return nums
        
    # while(p1 < l_num-1 and p2 < l_num-1):
    #     if nums[p1] == 0 and nums[p2] !=0:
    #         nums[p1],nums[p2] = nums[p2],nums[p1]
    #         p1 = p1 + 1
    #         p2 = p2 +  1
            
    #     if nums[p1] != 0 and nums[p2] ==0:
    #         p1 = p1 + 1
    #         p2 = p2 + 1
            
    #     if nums[p1] == 0 and nums[p2] == 0:
    #         p2 = p2 + 1
            
    #     if nums[p1] !=0 and nums[p2] != 0:
    #         p1 = p1 + 2
    #         p2 = p2 + 2
            
    # return nums
    
    ## Mayank's Sol^
def move_zeroes(nums):
    """
    Function to move all 0's to the end of the array while maintaining the order of non-zero elements.
    :param nums: List[int] -> A list of integers
    :return: None -> The list is modified in place
    """
    non_zero_index = 0  # Pointer to track the position of the next non-zero element
 
    # Move non-zero elements to the front of the list
    for i in range(len(nums)):
        if nums[i] != 0:
            nums[non_zero_index] = nums[i]
            non_zero_index += 1
    
    # Fill the remaining positions with zeros
    while non_zero_index < len(nums):
        nums[non_zero_index] = 0
        non_zero_index += 1
 
# Helper function to display the result (for debugging)
def display_result(nums):
    move_zeroes(nums)
    print(nums)
 
# # Example usage (can be removed)
# # nums = [0, 1, 0, 3, 12]
# # display_result(nums)  # Output should be [1, 3, 12, 0, 0]


    # ## My Custom Sol^

    # l = [0]*len(nums)
    # zeros = 0
    # non_zeros = 0

    # for i in nums:
    #     if i != 0:
    #         non_zeros = non_zeros + 1
    #         l[non_zeros-1] = i
            
    # return l
```

## Coding Exercise 72: Intersection of two Lists (Careful with i not in intersection)
<img width="724" height="865" alt="image" src="https://github.com/user-attachments/assets/a4427fc2-2b77-46fc-9b3c-01a4bbaf0d75" />

```python
def intersection(nums1, nums2):
    """
    Function to find the intersection of two integer arrays.
    :param nums1: List[int] -> First array of integers
    :param nums2: List[int] -> Second array of integers
    :return: List[int] -> An array of unique integers present in both arrays
    """
    # TODO: Implement this function
    pass

    intersection = []
    # for i in nums1:
    #     if i not in intersection and i in nums2:
    #         intersection.append(i)
    
    for i in nums2:
        if i not in intersection and i in nums1:
            intersection.append(i)
            
    return intersection
```
## Coding Exercise 73: Max Consecutive Ones
<img width="721" height="790" alt="image" src="https://github.com/user-attachments/assets/6da91ffd-31eb-4a35-8d21-29ebd5b16fd4" />

```python
def find_max_consecutive_ones(nums):
    """
    Function to find the maximum number of consecutive 1's in a binary array.
    :param nums: List[int] -> A binary array where each element is either 0 or 1
    :return: int -> The maximum number of consecutive 1's
    """
    # TODO: Implement this function
    pass

    consecutive_ones = 0
    max_ones = 0
    
    for i in range(len(nums)):
    	if nums[i] == 1:
    		consecutive_ones = consecutive_ones + 1
    		## VVIP below if statement
    		if i == len(nums)-1:
    		    if max_ones < consecutive_ones:
    			    max_ones = consecutive_ones
    
    	else:
    		if max_ones < consecutive_ones:
    			max_ones = consecutive_ones
    			consecutive_ones = 0 ## reset
    		else:
    			consecutive_ones = 0 ## reset
    			
    return max_ones

```






















## Coding Exercise 62: Search in Rotated Sorted Array

