# Week1
## 硬件与软件(Hardware and Software)
### 1. 硬件 Hardware：计算机的物理设备，例如键盘、屏幕、鼠标、硬盘、内存、DVD 驱动器、处理单元等。
### 2. 软件 Software：你写的指令，用来命令计算机执行动作和做出决策。软件控制硬件。

## 硬件
### Central Processing Unit, CPU：中央处理单元，负责处理。包括ALU和CU。
1. ALU：Arithmetic Logic Unit，算术逻辑单元。执行计算和比较；数据会改变；例如加减乘除、比较大小。
2. CU：Control Unit，控制单元。在 CPU 寄存器和其他硬件组件之间移动数据；本身不改变数据；读取程序指令，并向 ALU 发出命令。
### Main Memory：主存，通常指内存/RAM。
1. 内存被划分为很多“字节”；每个字节有一个地址；CPU 通过地址找到数据；地址就像房间号，字节就像房间。
2. 易失性 volatile：程序结束或计算机关机后，主存内容会丢失。
3. 主存也叫 RAM，Random Access Memory，随机存取存储器。
4. 速度快，容量通常较小，用于运行程序时临时存放。
### Secondary Memory / Storage：二级存储，如硬盘、U盘、光盘。
1. 非易失 non-volatile：程序不运行或关机后，数据仍然保留。
2. 速度慢，容量通常较大，用于长期保存数据。
### Input Devices：输入设备，如键盘、鼠标、扫描仪、相机、麦克风。
输入设备是把外部信息发送给计算机的设备。
### Output Devices：输出设备，如显示器、打印机、音箱。

## 软件
### 系统软件 System Software
1. 管理计算机硬件；管理运行在计算机上的程序。
2. 操作系统，如 Windows、Linux；实用程序 utility programs；软件开发工具 software development tools。
### 应用软件 Application Software
1. 为用户提供服务；解决特定问题。
2. 文字处理软件，如 Word；游戏；解决具体问题的程序。

## 预处理指令（Preprocessor Directives）
### 基本概念
预处理指令是 C 语言中一种特殊的命令，它们以 # 开头，在程序正式编译之前由预处理器处理。你可以把它们理解为“写给预处理器看的指令”，而不是写给编译器或运行时看的。它们不是 C 语句，所以末尾不加分号，也不参与程序运行
### 预处理在编译流程中的位置
```text
源代码 .c
   ↓ 预处理（处理 # 开头的指令）
预处理后的代码
   ↓ 编译（生成汇编代码）
汇编代码
   ↓ 汇编（生成目标文件 .o / .obj）
目标文件
   ↓ 链接（和库函数等合并）
可执行文件
```

## 转义序列（Escape Sequence）
```text
\n	换行（newline）
\t	水平制表符（Tab），将光标移动到下一个Tab位。
\\	反斜杠本身 \
\"	双引号 "
\'	单引号 '
\0	空字符（null character）
\a	响铃（alert）
\b	退格（backspace）
\r	回车（carriage return）
\f	换页（form feed）
\v	垂直制表符（vertical tab）
\?	问号 ?
```
