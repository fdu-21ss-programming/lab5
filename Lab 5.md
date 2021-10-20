# Lab 5

> 本次lab目标：
>
> 1. 了解循环结构
> 2. 在头歌平台使用编程解决实际问题



## 获取及提交lab

**获取**：通过 `https://github.com/fdu-21ss-programming/lab5`或者`微信群`获取。

**提交**：本次lab附带的练习题将于2021年10月21日15:25发布于头歌平台

**截止时间**：2021年10月24日 23:59:59



## 1. 了解循环结构

**while循环**

```c
while(condition){
   statement(s);
}
```

`condition` 可以是任意的表达式，当为任意非零值时都为 true

它会在执行循环主体**之前**测试条件，当条件为 true 时执行循环，当条件为 false 时，退出循环



**for循环**

```c
for (init; condition; increment){
   statement(s);
}
```

`init` 会首先被执行，且只会执行一次；可以不在这里写任何语句，只要有一个分号出现即可

接下来，会判断 `condition`，如果为真，则执行循环主体，如果为假，则不执行循环主体

在执行完 for 循环主体后，控制流会跳回上面的 `increment` 语句；可以不在这里写任何语句，只要在`condition`后有一个分号出现即可

![for](image\for.png)



**do...while循环**

```c
do{
   statement(s);
}while( condition );
```

`condition`出现在循环的尾部，所以循环中的 `statement(s)` 会在`condition`被测试之前至少执行一次。

如果条件为真，控制流会跳转回上面的 `do`，然后重新执行循环中的 `statement(s)`



**嵌套循环**

可以在任何类型的循环内嵌套其他任何类型的循环，比如，一个 for 循环可以嵌套在一个 while 循环内，反之亦然

虽说理论上可以嵌套成任意层数的循环，但在实际中，通常为两个循环的嵌套，超过两个的极少使用

举例如下：

```c
#include <stdio.h>

int main()
{
    for (int i = 0; i < 3; ++i) {
        printf("first loop\n");
        for (int j = 0; j < 2; ++j) {
            printf("second loop\n");
        }
    }
    return 0;
}
```

输出如下：

```c
first loop
second loop
second loop
first loop
second loop
second loop
first loop
second loop
second loop
```



**循环控制语句**

循环控制语句可以帮助你更为灵活地使用循环结构

| 控制语句 | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| break    | 终止 **循环** 或 **switch** 语句，程序流将继续执行紧接着循环或 switch 的下一条语句 |
| continue | 告诉一个循环体立刻停止本次循环迭代，该循环体内continue语句后的代码将被跳过，重新开始下一次循环迭代 |
| goto     | 跳到被标记的语句开始执行。但是不建议在程序中使用 goto 语句，因为会大幅降低代码的可读性，提高代码维护难度 |

