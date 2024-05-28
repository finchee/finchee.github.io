# GCC常用选项

---

## 常用编译选项

|选项|描述|
|-|-|
|-E|预处理, 开发过程中想快速确定宏可以使用`-E`或`-dM`|
|-c|预处理、编译、汇编, 但不链接|
|-o|指定输出文件|
|-I|指定头文件目录|
|-L|指定链接时的库文件目录|
|-l|指定链接的库文件|

## 多文件编译

### 源程序内容

main.c:

```C
#include <stdio.h>
#include "sub.h"

int main(int argc, char *argv[])
{
    int i
    printf("main fun! \n");
    sub_fun();
    return 0;
}
```

sub.h:

```C
void sub_fun(void);
```

sub.c:

```C
void sub_fun(void)
{
    printf("sub fun! \n");
}
```

### 编译及执行结果

```shell
finchee@linux-server:~/Documents/嵌入式linux应用开发基础/02_options/02_multi_file$ gcc -o test main.c sub.c
sub.c: In function ‘sub_fun’:
sub.c:3:5: warning: implicit declaration of function ‘printf’ [-Wimplicit-function-declaration]
    3 |     printf("sub fun! \n");
      |     ^~~~~~
sub.c:1:1: note: include ‘<stdio.h>’ or provide a declaration of ‘printf’
  +++ |+#include <stdio.h>
    1 | void sub_fun(void)
sub.c:3:5: warning: incompatible implicit declaration of built-in function ‘printf’ [-Wbuiltin-declaration-mismatch]
    3 |     printf("sub fun! \n");
      |     ^~~~~~
sub.c:3:5: note: include ‘<stdio.h>’ or provide a declaration of ‘printf’
finchee@linux-server:~/Documents/嵌入式linux应用开发基础/02_options/02_multi_file$ ./test
main fun! 
sub fun! 
finchee@linux-server:~/Documents/嵌入式linux应用开发基础/02_options/02_multi_file$ 
```
