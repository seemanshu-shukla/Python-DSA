# Searching and Sorting Algorithm:

## 1. Arrays: 
### Refer: [Notes\Searching_And_Sorting_Algorithm\Introduction_to_arrays.pdf](Notes/Searching_And_Sorting_Algorithm/Introduction_to_arrays.pdf)
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
### Refer: Notes\Searching_And_Sorting_Algorithm\Linear_Search_Algorithm.pdf
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

    
    
