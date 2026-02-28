<div align="center">

# 🖨️ ft_printf

**Recreating one of C's most iconic functions — format strings, variadic args, and all.**

![C](https://img.shields.io/badge/language-C-blue?style=for-the-badge&logo=c)
![42](https://img.shields.io/badge/school-42-black?style=for-the-badge)
![Score](https://img.shields.io/badge/score-100%2F100-brightgreen?style=for-the-badge)

</div>

---

## 🧠 What is ft_printf?

`ft_printf` is a 42 project where you rewrite the famous `printf` function from the C standard library. It dives deep into **variadic functions**, format parsing, and low-level output — all without using the real `printf`.

---

## ✅ Supported Conversions

| Specifier | Output |
|-----------|--------|
| `%c` | Single character |
| `%s` | String |
| `%p` | Pointer address (hex) |
| `%d` | Signed decimal integer |
| `%i` | Signed integer |
| `%u` | Unsigned decimal integer |
| `%x` | Hexadecimal (lowercase) |
| `%X` | Hexadecimal (uppercase) |
| `%%` | Literal percent sign |

---

## 🚀 Usage

```bash
git clone https://github.com/Houdaifa1/ft_printf
cd ft_printf
make
```

Include in your project:

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello, %s! You are %d years old.\n", "world", 42);
    ft_printf("Pointer: %p\n", (void *)&main);
    ft_printf("Hex: %x | %X\n", 255, 255);
    return (0);
}
```

---

## 🔧 Makefile Targets

| Target | Action |
|--------|--------|
| `make` | Compile the library |
| `make clean` | Remove object files |
| `make fclean` | Full cleanup |
| `make re` | Rebuild |

---

## 💡 How It Works

```
ft_printf(format, ...)
     │
     ▼
Parse format string char by char
     │
     ├── Regular char → write directly
     │
     └── '%' found → read next char
              │
              ├── 'c' → va_arg(char)
              ├── 's' → va_arg(char*)
              ├── 'd'/'i' → va_arg(int)
              ├── 'u' → va_arg(unsigned int)
              ├── 'x'/'X' → va_arg(unsigned int) → base 16
              ├── 'p' → va_arg(void*) → hex address
              └── '%' → literal '%'
```

---

<div align="center">
<i>Because reimplementing the wheel is how you learn to build cars.</i>
</div>
