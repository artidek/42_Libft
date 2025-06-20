# 42_Libft

## Overview

**42_Libft** is a personal implementation of a basic C library, developed as a foundational project for 42 school. The purpose of this library is to re-create many of the standard C library functions from scratch, reinforcing a deep understanding of low-level programming, memory management, and API design in C. The project also introduces a simple linked list API.

This README describes the implementation approach, usage, and structure of the library.

## Features

- **Standard Library Functions**: Custom implementations of memory, string, character, and conversion functions commonly found in `<string.h>`, `<ctype.h>`, and `<stdlib.h>`.
- **File Descriptor Output Functions**: Custom functions to output characters, strings, and numbers to file descriptors.
- **Linked List Utilities**: A set of utilities to create and manipulate singly linked lists.
- **Modular and Testable**: Each function is implemented in a separate file with a shared header.

## Implementation Details

### Project Structure

- `libft.h`: Main header file with all function prototypes and the `t_list` structure.
- `Makefile`: Automates compilation, library creation, and clean-up.
- `ft_*.c`: Each file implements a specific function.

### Main Functions Implemented

#### Memory Functions

- `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`, `ft_calloc`

#### String Functions

- `ft_strlen`, `ft_strlcpy`, `ft_strlcat`, `ft_strdup`, `ft_strchr`, `ft_strrchr`, `ft_strncmp`, `ft_strnstr`, `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_strmapi`, `ft_striteri`

#### Character Analysis

- `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`, `ft_toupper`, `ft_tolower`

#### Conversion

- `ft_atoi`, `ft_itoa`

#### File Descriptor Output

- `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`

#### Linked List

- `t_list`: Definition in `libft.h`
- `ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`, `ft_lstsize`, `ft_lstlast`, `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`

### Notable Implementation Notes

- **Memory Safety**: All allocations are checked for `NULL` before use. Functions like `ft_split` and `ft_strdup` handle allocation failures gracefully.
- **Reentrancy and Modularity**: No global/stateful variables are used; all functions are stateless unless explicitly operating on user data.
- **Norm Compliance**: The code style follows 42 school's norm, with attention to clarity and maintainability.

### Example Usage

To use the library in your project:

```c
#include "libft.h"

int main(void) {
    char *dup = ft_strdup("Hello, 42!");
    ft_putendl_fd(dup, 1); // Prints "Hello, 42!" to standard output
    free(dup);
    return 0;
}
```

Compile and link with:

```bash
make
gcc your_program.c -L. -lft
```

### Building the Library

Run the following command to build the static library `libft.a`:

```bash
make
```

Clean object files:

```bash
make clean
```

Remove object files and the library:

```bash
make fclean
```

Rebuild everything:

```bash
make re
```

Build with bonus linked list functions:

```bash
make bonus
```

### File Descriptor Output

Functions like `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, and `ft_putnbr_fd` can write output to any file descriptor, enabling flexible logging and output redirection.

### Linked List Example

```c
t_list *node = ft_lstnew("hello");
ft_lstadd_back(&node, ft_lstnew("world"));
ft_lstiter(node, print_function);
ft_lstclear(&node, free);
```

## Contributing

This repository is an educational project and does not accept external contributions. For issues or suggestions, feel free to open an issue for discussion.

## License

This project is released for educational purposes as part of the 42 School curriculum.

## Author

Artem Obshatko
