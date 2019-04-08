# HoI4 Quicksort

This is an implementation of an iterative randomized [quicksort](https://en.wikipedia.org/wiki/Quicksort) algorithm for HoI 4 script arrays. The algorithm allows for very fast sorting of large arrays, compared to naive algorithms such as selection or insertion sort.

Measured on my machine with Script Profiler, sorting a random 1000-element array takes 113 ms. Worst case (sorted array) requires about 300 ms (since the pivot is random, both times may fluctuate slightly). That's about 19.6 times better performance than selection sort, and 22 times better performance than insertion sort.

In order to use the quicksort scripted effect, arguments first need to be set up beforehand (saved as non-temporary variables). They are:
arr = array to sort
low = starting index (you probably want 0)
high = ending index (you probably want arr^num - 1)
Example:
```
    # arr set up beforehand
    # Set arguments
    set_variable = { high = arr^num }
    subtract_from_variable = { high = 1 }

    set_variable = { low = 0 }

    # Arguments: arr, high, low
    quicksort = yes    # arr set up beforehand
    # Set arguments
    set_variable = { high = arr^num }
    subtract_from_variable = { high = 1 }

    set_variable = { low = 0 }

    # Arguments: arr, high, low
    quicksort = yes
````

Included in the file are: the quicksort scripted effects (`quicksort` and `quicksort_partition`), selection sort (`naive_sorting`), insertion sort (`insertion_sort`), scripted effect to measure performance (`sorting_test` - call it with an event while running the profiler), scripted effects to test the sorting effects and an effect to create the test array (
`set_up_array`).

Feel free to use in your mods, but give credits to Yard1 (both in code, with comments; and on your download page).

My [Ledger](https://github.com/Yard1/HoI4-Ledger) mod makes use of this algorithm, albeit in a modified version.
