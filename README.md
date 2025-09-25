# Array Search in C++

**Aim:**
To study and implement different types of **searching techniques in arrays** using **C++**.

**Tools Used:**

* VS Code or any online C++ Compiler

---

## Theory

Searching is one of the most fundamental operations in computer science and programming. It is used to locate a specific element from a collection of data such as arrays, linked lists, or other data structures. The efficiency of a search algorithm depends on the **structure of the data** and the **searching technique** used.

An **array** is a collection of elements stored at contiguous memory locations. To search for an element, we can use either **simple methods like Linear Search** or **efficient methods like Binary Search**. C++ also provides **STL (Standard Template Library)** functions that simplify searching operations.

### 1. Linear Search

* Works by sequentially checking each element of the array.
* Does not require the array to be sorted.
* Easy to implement but inefficient for large datasets.
* Time Complexity: **O(n)**
  <img width="800" height="292" alt="image" src="https://github.com/user-attachments/assets/d7a51ca9-4e0c-417c-bceb-bab7db4f2bf5" />


### 2. Binary Search

* Works only on **sorted arrays**.
* Divides the array into halves repeatedly until the target is found.
* Very efficient compared to linear search.
* Time Complexity: **O(log n)**
<img width="1000" height="471" alt="image" src="https://github.com/user-attachments/assets/d16e1a6a-4236-484c-a989-6677ec8ea848" />


### 3. Search Using STL `find()`

* Part of the **Standard Template Library** (`<algorithm>`).
* Implements linear search internally, but makes the code shorter and cleaner.
* Returns an iterator pointing to the element if found, else returns the end of the array.

---

### Why Searching is Important?

* **Data Retrieval:** Essential in databases, file systems, and memory management.
* **Optimization:** Efficient searching reduces execution time in large applications.
* **Real-World Applications:** Product searches in e-commerce, text searches in editors, searching records in libraries, etc.

---

### General Syntax of Array Declaration

```cpp
int arr[size] = {elements};   // Declare and initialize array
```

### General Syntax of STL find

```cpp
auto it = find(arr, arr + size, target);
if (it != arr + size) {
    cout << "Element found at index " << (it - arr);
}
else {
    cout << "Element not found";
}
```

---

## Program 1 – Linear Search

**Algorithm (Detailed):**

1. Start the program.
2. Initialize a fixed array of size 7 with predefined values `{9, 8, 5, 1, 0, 3, 2}`.
3. Take the target element from the user as input.
4. Set a variable `index = -1` to track if the element is found.
5. Traverse the array from the first element (index `0`) to the last element (index `size-1`).

   * For each element, check if `arr[i] == target`.
   * If yes, store the index in `index` and break the loop.
6. After traversal:

   * If `index != -1`, print that the element was found at that index.
   * Else, print that the element is not found.
7. End the program.

**Key Point:** Works on unsorted arrays.

---

## Program 2 – Binary Search

**Algorithm (Detailed):**

1. Start the program.
2. Initialize a fixed array of size 7 with predefined values `{9, 8, 5, 1, 0, 3, 2}`.
3. Sort the array in ascending order using `sort()`.
4. Display the sorted array to the user.
5. Take the target element from the user as input.
6. Set two pointers:

   * `low = 0` (first index)
   * `high = size - 1` (last index).
7. Repeat while `low <= high`:

   * Calculate `mid = (low + high) / 2`.
   * If `arr[mid] == target`, element is found → store index and stop the loop.
   * Else if `arr[mid] < target`, update `low = mid + 1` (search right half).
   * Else, update `high = mid - 1` (search left half).
8. After the loop ends:

   * If element was found, display its index in the sorted array.
   * Else, print that the element is not present.
9. Stop the program.

**Key Point:** Faster but requires a sorted array.

---

## Program 3 – Search Using STL `find()`

**Algorithm (Detailed):**

1. Start the program.
2. Initialize a fixed array of size 7 with values `{9, 8, 5, 1, 0, 3, 2}`.
3. Take the target element from the user as input.
4. Use the **STL function `find(start, end, target)`** to search in the array:

   * If the element is found, `find()` returns an iterator pointing to that element.
   * If not found, it returns `end` (i.e., `arr + size`).
5. Compare the result of `find()` with `arr + size`.

   * If it is not equal, calculate the index using pointer arithmetic (`it - arr`) and print the position.
   * Else, print that the element is not found.
6. Stop the program.

**Key Point:** Simplifies searching using built-in STL functionality.

---

## Key Learning Outcomes

* Learned different searching techniques in arrays: Linear, Binary, and STL.
* Understood how **Linear Search** works on both sorted and unsorted arrays.
* Understood how **Binary Search** is efficient but works only on sorted data.
* Learned to use **STL functions** like `find()` for simpler and cleaner code.
* Compared the performance and use cases of each technique.

---

## Applications

* **Databases:** Searching records quickly.
* **Operating Systems:** Searching memory blocks and process IDs.
* **E-commerce:** Searching products from a large list.
* **Gaming:** Searching player scores or inventory items.
* **Text Editors:** Finding words/characters in documents.
