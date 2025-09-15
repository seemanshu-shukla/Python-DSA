# List/Array Practice Questions:
## Coding Exercise 63: Maximum Element in a List.
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



## Coding Exercise 62: Search in Rotated Sorted Array

