# Sorting Algorithms & Big O

This project is designed to help you understand different sorting algorithms, the concept of Big O notation, and how to select the best sorting algorithm for a given input. Additionally, you will learn about stable sorting algorithms.

## Learning Objectives

By the end of this project, you will be able to explain:

- At least four different sorting algorithms.
- What the Big O notation is and how to evaluate the time complexity of an algorithm.
- How to select the best sorting algorithm for a given input.
- What a stable sorting algorithm is.

## Requirements

### General

- Allowed editors: vi, vim, emacs.
- All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89.
- All your files should end with a new line.
- A `README.md` file, at the root of the project folder, is mandatory.
- Your code should use the Betty style. It will be checked using `betty-style.pl` and `betty-doc.pl`.
- You are not allowed to use global variables.
- No more than 5 functions per file.
- Unless specified otherwise, you are not allowed to use the standard library. Any use of functions like `printf`, `puts`, etc., is totally forbidden.
- The prototypes of all your functions should be included in your header file called `sort.h`.
- Don't forget to push your header file.
- All your header files should be include guarded.
- A list or array does not need to be sorted if its size is less than 2.

### Data Structure and Functions

For this project, you are given the following `print_array` and `print_list` functions:

```c
#include <stdlib.h>
#include <stdio.h>

/**
 * print_array - Prints an array of integers
 *
 * @array: The array to be printed
 * @size: Number of elements in @array
 */
void print_array(const int *array, size_t size)
{
    size_t i;

    i = 0;
    while (array && i < size)
    {
        if (i > 0)
            printf(", ");
        printf("%d", array[i]);
        ++i;
    }
    printf("\n");
}

#include <stdio.h>
#include "sort.h"

/**
 * print_list - Prints a list of integers
 *
 * @list: The list to be printed
 */
void print_list(const listint_t *list)
{
    int i;

    i = 0;
    while (list)
    {
        if (i > 0)
            printf(", ");
        printf("%d", list->n);
        ++i;
        list = list->next;
    }
    printf("\n");
}

/**
 * struct listint_s - Doubly linked list node
 *
 * @n: Integer stored in the node
 * @prev: Pointer to the previous element of the list
 * @next: Pointer to the next element of the list
 */
typedef struct listint_s
{
    const int n;
    struct listint_s *prev;
    struct listint_s *next;
} listint_t;

