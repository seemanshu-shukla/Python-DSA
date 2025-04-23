# Searching Algorithm:

## 1. Arrays: 
### Refer: [Notes/Searching_And_Sorting_Algorithm/Introduction_to_arrays.pdf](Notes/Searching_And_Sorting_Algorithm/Introduction_to_arrays.pdf)
### Code:
    ```
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
    ```
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
    ```
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

## Bubble Sort Algorithm:
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

    ```
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


