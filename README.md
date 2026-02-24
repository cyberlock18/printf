# ft_printf

A custom implementation of the C standard library `printf` function, built as part of the 42 school curriculum.

## Project Summary

`ft_printf` replicates the behaviour of the standard `printf` by parsing a format string and processing a variable number of arguments. The result is compiled into a static library (`libftprintf.a`) that can be linked into any C project.

Supported conversion specifiers:

| Specifier | Description |
|-----------|-------------|
| `%c` | Single character |
| `%s` | String |
| `%d` / `%i` | Signed decimal integer |
| `%u` | Unsigned decimal integer |
| `%x` | Unsigned hexadecimal (lowercase) |
| `%X` | Unsigned hexadecimal (uppercase) |
| `%p` | Pointer address |
| `%%` | Literal percent sign |

## Skills Acquired

- Variadic functions in C (`stdarg.h`, `va_list`, `va_arg`)
- Recursive digit and hexadecimal printing without `sprintf`
- Static library creation with `ar`
- Parsing format strings character by character
- Writing portable, norm-compliant C code (42 Norminette style)
- Working with low-level I/O using the `write` syscall

## Build & Run

All source files live in the `ft_printf/` subdirectory.

```bash
# Enter the source directory
cd ft_printf

# Build the static library (produces libftprintf.a)
make

# Remove object files only
make clean

# Remove object files and the library
make fclean

# Rebuild from scratch
make re
```

### Linking the library in your own project

```c
// example_main.c
#include "ft_printf/ft_printf.h"

int main(void)
{
    ft_printf("Hello, %s! Number: %d\n", "world", 42);
    return (0);
}
```

```bash
# Compile your program and link against the library
cc -Wall -Wextra -Werror example_main.c -L ft_printf -lftprintf -o example
./example
```

## Project Structure

```
printf/
├── README.md
├── README.es.md
└── ft_printf/
    ├── Makefile
    ├── ft_printf.h          # Header – function prototypes
    ├── ft_printf.c          # Core parser and ft_printf entry point
    ├── ft_printf_others.c   # %c, %s, %d/%i, %u helpers
    └── ft_printf_hex.c      # %x, %X, %p helpers
```

## Author

- **ruortiz-** – [42 school](https://42.fr)