# Insertion-sort
""" This algorithm processds by considering one element at a time, placing the element in the correct order relative to those before it. We start with the first element in the arrary, which is travially sorted by itself. When considering the next element in the array, if it is smaller than the first, we swap them. Next we consider the third element in the array, swapping it leftward until it is in its proper order relative to the first two elements. We continue in this manner with the fourth element, the fifth, and so on, until the whole array is sorted."""

# algorithm: Insertion Sort(A):
```pseudocode
    Input: An array A of n comparable elements
    Output: The array A with elements rearranged in nodecreasion order
        for k from 1 to n - 1 do 
            Insert A[k] at its proper location within A[0], A[1], ...,A[k].
```
# Java implements:
``` Java
    public static void insertionSort(char[] data) {
        int n = data.length;
        for (int k = 1; i < n; k++) {
            char cur = data[k];
            int j = k;
            while (j > 0 && data[j-1] > cur) {
                data[j] = data[j-1];
                j--;
            }
            data[j] = cur;
        }
    }
```
