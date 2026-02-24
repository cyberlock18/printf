# ft_printf

Implementación personalizada de la función `printf` de la biblioteca estándar de C, desarrollada como parte del currículo de la escuela 42.

## Resumen del proyecto

`ft_printf` replica el comportamiento del `printf` estándar analizando una cadena de formato y procesando un número variable de argumentos. El resultado se compila en una biblioteca estática (`libftprintf.a`) que puede enlazarse con cualquier proyecto en C.

Especificadores de conversión soportados:

| Especificador | Descripción |
|---------------|-------------|
| `%c` | Un carácter |
| `%s` | Cadena de texto |
| `%d` / `%i` | Entero decimal con signo |
| `%u` | Entero decimal sin signo |
| `%x` | Hexadecimal sin signo (minúsculas) |
| `%X` | Hexadecimal sin signo (mayúsculas) |
| `%p` | Dirección de puntero |
| `%%` | Signo de porcentaje literal |

## Habilidades adquiridas

- Funciones variádicas en C (`stdarg.h`, `va_list`, `va_arg`)
- Impresión recursiva de dígitos y valores hexadecimales sin `sprintf`
- Creación de bibliotecas estáticas con `ar`
- Análisis de cadenas de formato carácter a carácter
- Escritura de código C portable y conforme a la norma de 42 (Norminette)
- E/S de bajo nivel mediante la llamada al sistema `write`

## Compilación y ejecución

Todos los archivos fuente se encuentran en el subdirectorio `ft_printf/`.

```bash
# Entrar al directorio fuente
cd ft_printf

# Compilar la biblioteca estática (genera libftprintf.a)
make

# Eliminar solo los archivos objeto
make clean

# Eliminar archivos objeto y la biblioteca
make fclean

# Recompilar desde cero
make re
```

### Enlazar la biblioteca en tu propio proyecto

```c
// ejemplo_main.c
#include "ft_printf/ft_printf.h"

int main(void)
{
    ft_printf("¡Hola, %s! Número: %d\n", "mundo", 42);
    return (0);
}
```

```bash
# Compilar el programa enlazándolo con la biblioteca
cc -Wall -Wextra -Werror ejemplo_main.c -L ft_printf -lftprintf -o ejemplo
./ejemplo
```

## Estructura del proyecto

```
printf/
├── README.md
├── README.es.md
└── ft_printf/
    ├── Makefile
    ├── ft_printf.h          # Cabecera – prototipos de funciones
    ├── ft_printf.c          # Analizador principal y punto de entrada de ft_printf
    ├── ft_printf_others.c   # Helpers para %c, %s, %d/%i, %u
    └── ft_printf_hex.c      # Helpers para %x, %X, %p
```

## Autor

- **ruortiz-** – [Escuela 42](https://42.fr)
