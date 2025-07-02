
# Get_Next_Line

> A function that reads a file line by line, developed for 42 School.

---

## 📝 Description

`get_next_line` is a function that reads from a file descriptor one line at a time. It is especially useful when parsing files or standard input line by line.

This project demonstrates advanced C programming concepts, including:

- Static variables
- File I/O operations
- Memory management
- Buffer management

---

## ✨ Features

- Reads from any file descriptor (e.g., `stdin`, files, pipes)
- Handles multiple file descriptors at the same time
- Efficient and dynamic memory usage
- Customizable `BUFFER_SIZE`
- Leak-free and norm-compliant

---

## ⚙️ Usage

### Function Prototype

```c
char *get_next_line(int fd);
````

### Example

```c
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("file.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return 0;
}
```

---

## 🛠️ Installation

1. **Clone the repository:**

```bash
git clone https://github.com/mouchtach/Get_Next_Line.git
```

2. **Build the project:**

```bash
cd Get_Next_Line && make
```

This will generate `get_next_line.a` (static library).

---

## ✅ Testing

To run basic tests:

```bash
make test
```

For full testing with 42’s *francinette*:

```bash
./francinette --gnl
```

> ⚠️ **Note:** The function returns `NULL` when there's nothing left to read or on error. Always check the return value.

