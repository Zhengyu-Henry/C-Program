# Week1
## 硬件与软件(Hardware and Software)
1. 硬件 Hardware：计算机的物理设备，例如键盘、屏幕、鼠标、硬盘、内存、DVD 驱动器、处理单元等。
2. 软件 Software：你写的指令，用来命令计算机执行动作和做出决策。软件控制硬件。

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
## Data Type
```text
Data type | Keyword | Bits | Range
integer | int | 32 | −2,147,483,648 to 2,147,483,647
long integer | long | 32 | −2,147,483,648 to 2,147,483,647
short integer | short | 16 | −32768 to 32767
unsigned integer | unsigned | 32 | 0 to 4294967295
character | char | 8 | 0 to 255
floating point | float | 32 | approximately 6 digits of precision
double floating point | double | 64 | approximately 12 digits of precision
```

## 变量的命名规则
### 变量名必须是合法的标识符
在 C 语言中，变量名属于“标识符”。
标识符是由字母、数字和下划线 _ 组成的字符序列。
### 不能以数字开头
标识符可以由字母、数字、下划线组成，但第一个字符不能是数字。
### C 语言区分大小写（case sensitive）
C 语言是 case sensitive 的，也就是说大写字母和小写字母是完全不同的字符。

## C语言关键字（C keywords）
关键字是 C 语言预先定义好的、有特殊用途的单词。你不能把它们当作变量名、函数名等标识符来使用，且必须小写。
```text
auto	double	int	struct
break	else	long	switch
case	enum	register	typedef
char	extern	return	union
const	float	short	unsigned
continue	for	signed	void
default	goto	sizeof	volatile
do	if	static	while
```

## 格式说明符（Format Specifiers）
```text
数据类型	范围	字节数	格式说明符
char	-128 到 127	1	%c
unsigned char	0 到 255	1	%c
short signed int	-32,768 到 32,767	2	%d
short unsigned int	0 到 65,535	2	%u
signed int	-32768 到 32767	4	%d
unsigned int	0 到 65535	4	%u
long signed int	-2147483648 到 2147483647	4	%ld
long unsigned int	0 到 4294967295	4	%lu
float	-3.4e38 到 3.4e38	4	%f
double	-1.7e308 到 1.7e308	8	%lf
long double	-1.7e4932 到 1.7e4932	8	%Lf
输出八进制    %o
输出十六进制    %X
科学计数法（小写）1.23456e+02    %e
科学计数法（大写）1.23456E+02    %E
自动在%f和%e里选择较短形式    %g
自动在%f和%E里选择较短形式    %G
```
### 打印字段宽度（Field Widths）
1. 字段宽度指定数据打印时占用的最小字符宽度。
2. 如果数据宽度小于字段宽度，默认右对齐，左边补空格。如果数值宽度超过字段宽度，字段宽度会自动增加，不会截断。
3. 在 % 和转换说明符之间插入一个整数表示字段宽度，例如 %4d。
4. 字段宽度可用于所有转换说明符。
5. 负号也占用一个字符位置。
### 打印左右对齐（Left / Right Justification）
1. 默认右对齐。
2. 使用 - 标志可以左对齐，在字段内左边对齐，右边补空格。
3. 格式：%-宽度转换说明符。
### 打印精确度（Precision）
1. 精度用小数点 . 后跟一个整数表示，放在 % 和转换说明符之间。
2. 对不同类型含义不同：整数：精度表示最少打印多少位数字，不足补前导零。浮点数：e、E、f：精度表示小数点后的位数；g、G：精度表示最大有效数字位数。字符串：精度表示最多打印多少个字符。
3. 格式：%.精度转换说明符。
### 打印正负数（Positive / Negative Numbers）
1. + 标志：在正数前显示正号，负数前显示负号。
2. 空格标志：在正数前打印一个空格，负数前仍显示负号。
### 打印零填充（Zero Padding）
零填充是指在字段宽度前加 0 标志，用前导零填充空白。
