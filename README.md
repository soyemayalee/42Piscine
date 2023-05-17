
# push_swap subject

## Mandatory Part

### The Rules ###
- You have 2 stacks named ***a*** and ***b***.
- At the beginning:
    - The stack ***a*** contains a random amount of negative and/or positive numbers which cannot be duplicated.
    - The stack ***b*** is empty.
- The goal is to sort in ascending order numbers into stack ***a***. To do so, you have the following operations at your disposal:
    - sa (swap a): Swap the first 2 elements at the top of stack ***a***. Do nothing if there is only one or no elements.
    - sb (swap b): Swap the first 2 elements at the top of stack ***b***. Do nothing if there is only one or no elements.
    - ss : sa and sb at the same time.
    - pa (push a): Take the first element at the top of ***b*** and put it at the top of a. Do nothing if ***b*** is empty.
    - pb (push b): Take the first element at the top of ***a*** and put it at the top of b. Do nothing if ***a*** is empty.
    - ra (rotate a): Shift up all elements of stack ***a*** by 1. The first element becomes the last one.
    - rb (rotate b): Shift up all elements of stack ***b*** by 1. The first element becomes the last one.
    - rr : ra and rb at the same time.
    - rra (reverse rotate a): Shift down all elements of stack ***a*** by 1. The last element becomes the first one.
    - rrb (reverse rotate b): Shift down all elements of stack ***b*** by 1. The last element becomes the first one.
    - rrr : rra and rrb at the same time.


### The "push_swap" Program ###
|Category|Specifics|
|----|-----|
|Program Name|push_swap|
|Turn in files|Makefile, *.h, *.c|
|Makefile|NAME, all, clean, fclean, re|
|Arguments|stack a: A list of integers||
|External functions|read, write, malloc, free, exit and ft_printf and any equivalent YOU coded|
|Libft authorized|Yes|
|Description|Sort stacks|

Your project must comply with the following rules:
- You have to turn in a Makefile which will compile your source files. It must not relink.
- Global variables are forbidden.
- You have to write a program named ***push_swap*** that takes as an argument the stack ***a*** formatted as a list of integers. The first argument should be at the top of the stack (be careful about the order).
- The program must display the smallest list of instructions possible to sort the stack ***a***, the smallest number being at the top.
- Instructions must be separated by a ’\n’ and nothing else.
- The goal is to sort the stack with the lowest possible number of operations. During the evaluation process, the number of instructions found by your program will be compared against a limit: the maximum number of operations tolerated. If your program either displays a longer list or if the numbers aren’t sorted properly, your grade will be 0.
- If no parameters are specified, the program must not display anything and give the prompt back.
- In case of error, it must display "Error" followed by a ’\n’ on the standard error. Errors include for example: some arguments aren’t integers, some arguments are bigger than an integer and/or there are duplicates.

During the evaluation process, a binary will be provided in order to properly check your program. It will work as follows:
>ARG="4 67 3 87 23"; ./push_swap $ARG | wc -l

>ARG="4 67 3 87 23"; ./push_swap $ARG | ./checker_linux $ARG

If the program checker_linux displays "KO", it means that your ***push_swap*** came up with a list of instructions that doesn’t sort the numbers.
> The checker_linux program is available in the resources of the project in the intranet. You can find a description of how it works in the Bonus Part of this document.

## Bonus Part
This project leaves little room for adding extra features due to its simplicity. However, how about creating your own checker?
>Thanks to the checker program, you will be able to check whether the list of instructions generated by the push_swap program actually sorts the stack properly.

### The "checker" Program ###
|Category|Specifics|
|----|-----|
|Program Name|checker|
|Turn in files|*.h, *.c|
|Makefile|bonus|
|Arguments|stack a: A list of integers|
|External functions|read, write, malloc, free, exit and ft_printf and any equivalent YOU coded|
|Libft authorized|Yes|
|Description|Execute the sorting instructions|

- Write a program named checker that takes as an argument the stack ***a*** formatted as a list of integers. The first argument should be at the top of the stack (be careful about the order). If no argument is given, it stops and displays nothing.
- It will then wait and read instructions on the standard input, each instruction will be followed by ’\n’. Once all the instructions have been read, the program has to execute them on the stack received as an argument.
- If after executing those instructions, the stack ***a*** is actually sorted and the stack ***b*** is empty, then the program must display "OK" followed by a ’\n’ on the standard output.
- In every other case, it must display "KO" followed by a ’\n’ on the standard output.
- In case of error, you must display "Error" followed by a ’\n’ on the standard error. Errors include for example: some arguments are not integers, some arguments are bigger than an integer, there are duplicates, an instruction doesn’t exist and/or is incorrectly formatted.

>You DO NOT have to reproduce the exact same behavior as the provided binary. It is mandatory to manage errors but it is up to you to decide how you want to parse the arguments.

>The bonus part will only be assessed if the mandatory part is PERFECT. Perfect means the mandatory part has been integrally done and works without malfunctioning. If you have not passed ALL the mandatory requirements, your bonus part will not be evaluated at all.
