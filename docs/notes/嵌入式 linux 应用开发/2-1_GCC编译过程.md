# GCC编译过程

---

## GCC编译流程图

``` mermaid
flowchart LR
    A[main.c] -->|预处理| B(main.i)
    B -->|编译| C(main.S)
    C -->|汇编| D(main.o)
    D -->|链接| E(LED.elf)
    E -->|反汇编| F(led.dis)
    G(start.S) -->|汇编| H(start.o)
    H -->|链接| E
```
