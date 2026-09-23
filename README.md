# Merge Sort using Divide-and-Conquer

## Aim

To implement the Merge Sort algorithm using the Divide-and-Conquer technique and analyze its time complexity.

## Description

Merge Sort is a sorting algorithm based on the Divide-and-Conquer approach.

It works in three steps:

1. Divide the array into two halves.
2. Recursively sort both halves.
3. Merge the sorted halves.

## Algorithm

1. Check whether the array contains zero or one element.
2. If yes, return the array because it is already sorted.
3. Find the middle position of the array.
4. Divide the array into two halves.
5. Recursively apply Merge Sort to the left half.
6. Recursively apply Merge Sort to the right half.
7. Merge the two sorted halves.
8. Return the sorted array.

## Program

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2

    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])

    return merge(left, right)


def merge(left, right):
    result = []
    i = 0
    j = 0

    while i < len(left) and j < len(right):

        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])

    return result


arr = [38, 12, 27, 43, 9, 31, 18, 25]

print("Original Array:", arr)

sorted_arr = merge_sort(arr)

print("Sorted Array:", sorted_arr)
