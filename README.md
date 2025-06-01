<h1 align="center">push_swap</h1>

<p align="center">
  <strong>42 Beirut – Algorithmic Sorting Challenge</strong><br>
  A stack-based sorting project focused on algorithm optimization and instruction minimization.
</p>

---

## 📌 Project Description

The `push_swap` project is an algorithmic exercise where the goal is to sort a stack of integers using a limited set of stack operations. Only a second auxiliary stack is allowed, and the output must be the minimal number of instructions to complete the sort. The sorting must be done without using standard library sorting functions, while respecting strict input parsing and memory constraints.

---

## 🧠 Objectives

- Parse and validate user input with full error checking  
- Represent stacks as linked lists or arrays  
- Implement all stack operations listed in the subject  
- Design optimized sorting algorithms, depending on stack size  
- Avoid memory leaks and ensure compliance with 42 Norm  

---

## 🛠️ Allowed Stack Operations

| Command | Effect |
|--------|--------|
| `sa`   | swap the first two elements at the top of stack a |
| `sb`   | swap the first two elements at the top of stack b |
| `ss`   | `sa` and `sb` at the same time |
| `pa`   | push the top element of b onto a |
| `pb`   | push the top element of a onto b |
| `ra`   | rotate a upwards |
| `rb`   | rotate b upwards |
| `rr`   | `ra` and `rb` at the same time |
| `rra`  | reverse rotate a |
| `rrb`  | reverse rotate b |
| `rrr`  | `rra` and `rrb` at the same time |

---

## 🧾 Input Rules

- Only digits with optional '+' or '-' signs are allowed  
- No duplicate integers are accepted  
- Inputs must fit in 32-bit signed int range  
- Empty arguments or whitespace-only arguments are rejected  

Example of invalid input:

```bash
./push_swap "42" "forty two" 10
# Error
```

---

## 📂 File Structure

```
push_swap/
├── Makefile
├── push_swap.h
├── main.c
├── errors.c
├── stack_init.c
├── stack_utils.c
├── sort_small.c
├── sort_large.c
├── operations/
│   ├── swap.c
│   ├── push.c
│   ├── rotate.c
│   └── reverse_rotate.c
```

---

## 🔧 Compilation

```bash
make          # builds push_swap executable
make clean    # removes object files
make fclean   # removes object files and executable
make re       # rebuild everything
```

---

## ▶️ Usage

```bash
./push_swap 2 1 3
```

Example Output:

```bash
sa
```

Count the number of operations:

```bash
ARG="4 67 3 87 23"
./push_swap $ARG | wc -l
```

Check sorting validity:

```bash
ARG="4 67 3 87 23"
./push_swap $ARG | ./checker_linux $ARG
# OK
```

---

## ⚙️ Sorting Strategy

- For 2–5 elements: hardcoded optimal sort  
- For larger stacks (100–500): optimized with:  
  - Index compression (normalization)  
  - Chunking strategies  
  - Greedy + Rotate/Reverse decisions  

---

## 🧪 Edge Cases to Handle

- Duplicate numbers  
- Empty input  
- Numbers out of int range  
- Input with extra whitespace  
- Only one number (do nothing)  

---

## 🚫 Forbidden

- Use of global variables  
- Use of any library function other than:  
  - `malloc`, `free`, `write`, `read`, `exit`  

---

## 📊 Evaluation Guidelines

Your program will be judged based on:

| Stack Size | Max Allowed Operations |
|------------|------------------------|
| 100        | ≤ 700                  |
| 500        | ≤ 5500                 |

Additional checks:
- Norm compliance  
- Memory leaks (use `valgrind`)  
- Crash handling  
- Proper output formatting  

---

<p align="center"><i>"Sorting numbers is easy — doing it efficiently is an art."</i></p>
