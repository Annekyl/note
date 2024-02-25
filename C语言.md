[TOC]

# 头歌知识补充

## 1.scanf格式化输入函数

##### 格式化输入函数 scanf 的格式说明符

| 格式说明符 | 输入的数据类型 |
| ---------- | -------------- |
| %d         | 十进制整型数   |
| %f         | 浮点数         |
| %o         | 八进制整型数   |
| %x         | 十六进制整型数 |
| %c         | 一个字符       |
| %s         | 字符串         |

## 2.printf函数

#### 格式化输出函数 printf 的格式说明符

| 格式字符 | 用法                                                         |
| -------- | ------------------------------------------------------------ |
| %d       | 以十进制形式输出带符号整数，正数的符号省略                   |
| %o       | 以八进制形式输出无符号整数，不输出前缀0                      |
| %x, %X   | 以十六进制形式输出无符号整数，不输出前缀Ox                   |
| %u       | 以十进制形式输出无符号整数                                   |
| %f       | 以小数形式输出单、双精度实数                                 |
| %e, %E   | 以指数形式输出单、双精度实数                                 |
| %g, %G   | 以%f或%e中较短的输出宽度输出单、双精度实数，且不输出无意义的0 |
| %c       | 输出单个字符                                                 |
| %s       | 输出字符串                                                   |

#### 附加格式说明字符

`printf` 函数可以指定输出数据类型外，还可以通过附加格式说明指定输出数据的字段宽度、精度、对齐方式，附加格式说明字符含义如下，在具体应用中加以领会。

| 格式修饰符 | 用法                                                         |
| ---------- | ------------------------------------------------------------ |
| l          | 修饰格式字符时，用于d,o,x,u输出long型数据                    |
| h          | 修饰格式字符时，用于d,o,x输出short型数据                     |
| -          | 结果左对齐，右边填空格                                       |
| +          | 输出符号(正号或负号)                                         |
| m          | m指域宽，若实际位数多于定义的宽度，则按实际位数输出，若实际位数少于定义的宽度则补以空格或0 |
| .n         | n指精度。对于浮点数，用于指定输出的浮点数的小数的位数；对于字符串，指定从字符串左侧开始截取的子字符个数 |

## 3.转义字符

`printf()` 函数的 < 待打印的字符串 > 可以包含转义字符，其使用方法如下表所示： 

| 转义字符 | 含义                                  | 转义字符 | 含义       |
| -------- | ------------------------------------- | -------- | ---------- |
| \a       | 响铃符                                | \b       | 回退符     |
| \f       | 换页符                                | \n       | 换行符     |
| \r       | 回车符                                | \t       | 横向制表符 |
| \v       | 纵向制表符                            | \\       | 反斜杠     |
| \?       | 问号                                  | \’       | 单引号     |
| \ooo     | 八进制数，ooo代表1-2个八进制数        | \”       | 双引号     |
| \xhh     | 十六进制数，hh代表1个或多个十六进制数 |          |            |

## 4.sqrt函数：求平方根

sqrt函数是math.h头文件中定义的一个数学库函数，用于计算一个数的平方根。它的原型如下：

```
c复制代码#include <math.h>

double sqrt(double x);
```

参数说明：

- `x`：要求平方根的数值。

返回值：

- 返回计算结果，即`x`的平方根。

使用示例：

```
c复制代码#include <stdio.h>
#include <math.h>

int main() {
    double result = sqrt(9); // 计算9的平方根
    printf("Result: %f\n", result);
    return 0;
}
```

上述示例中，`sqrt(9)`计算了9的平方根，结果为3。然后将结果打印输出。

请注意，`sqrt`函数返回的是一个`double`类型的浮点数。如果需要使用整数类型的结果，可以进行类型转换。例如，`(int)sqrt(9)`将结果转换为整数类型。

## 5.pow函数：求指数幂

pow函数是C语言中的一个数学库函数，用于计算一个数的指数幂。它的原型如下：

```
c复制代码#include <math.h>

double pow(double base, double exponent);
```

参数说明：

- `base`：要进行指数运算的底数。
- `exponent`：指定的指数。

返回值：

- 返回计算结果，即`base`的`exponent`次幂。

使用示例：

```
c复制代码#include <stdio.h>
#include <math.h>

int main() {
    double result = pow(2, 3); // 计算2的3次幂
    printf("Result: %f\n", result);
    return 0;
}
```

上述示例中，`pow(2, 3)`计算了2的3次幂，结果为8。然后将结果打印输出。

请注意，`pow`函数返回的是一个`double`类型的浮点数。如果需要使用整数类型的结果，可以进行类型转换。例如，`(int)pow(2, 3)`将结果转换为整数类型。

# 第01课基础知识1

## 1.fgets函数：读取文件内容

```c
char *fgets(char *str, int num, FILE *stream);

```

参数解释：

- `str`：用于存储读取的字符串的字符数组，即接收输入的缓冲区。
- `num`：要读取的最大字符数（包括换行符和空字符），即缓冲区的大小。
- `stream`：要从中读取字符串的输入流，常见的是`stdin`（标准输入，即键盘输入）或文件指针。

`fgets`函数的工作原理如下：

1. 从指定的输入流中读取字符，直到遇到换行符 `\n`、达到最大字符数 `num-1` 或者遇到文件结束符 EOF。
2. 将读取的字符存储到 `str` 指向的字符数组中，直到遇到换行符 `\n` 或者达到最大字符数限制。
3. 在存储的字符序列末尾添加一个空字符 `\0`，表示字符串的结束。

`fgets`函数的返回值是成功读取的字符串的地址，即指向 `str` 的指针。如果没有读取到任何字符或者发生了错误，则返回空指针 `NULL`。

在示例代码中，我们使用了 `fgets` 函数来从标准输入中获取用户输入的纯英文字符串。我们指定了字符数组 `str` 来存储输入的字符串，使用 `sizeof(str)` 来确定字符数组的大小，以防止输入字符串超出缓冲区的范围。



# 第02课结构体指针文件

## 1.静态链表

```c
#include <stdio.h>

int main() {
    FILE *file; // 文件指针
    char filename[] = "成绩.txt"; // 文件名
    char ch;

    // 打开文件
    file = fopen(filename, "r");

    // 检查文件是否成功打开
    if (file == NULL) {
        printf("无法打开文件\n");
        return 1;
    }

    // 逐个字符读取文件内容并显示
    while ((ch = fgetc(file)) != EOF) {
        printf("%c", ch);
    }

    // 关闭文件
    fclose(file);

    return 0;
}

```

## 2.动态链表

```c
//
// Created by 30694 on 2024/1/17.
//
#include "stdio.h"
#include "stdlib.h"

#define LEN sizeof(struct Student)
struct Student {
    long num;
    float score;
    struct Student *next;
};
int n;

struct Student *creat(void) {
    struct Student *head;
    struct Student *p1, *p2;
    n = 0;
    p1 = p2 = (struct Student *) malloc(LEN);
    scanf_s("%1d,%f", &p1->num, &p1->score);
    head = NULL;
    while (p1->num != 0) {
        n = n + 1;
        if (n == 1)head = p1;
        else p2->next = p1;
        p2 = p1;
        p1 = (struct Student *) malloc(LEN);
        scanf_s("%1d,%f", &p1->num, &p1->score);
    }
    p2->next = NULL;
    return (head);
}

int main() {
    struct Student *pt;
    pt = creat();
    printf_s("\nnum:%1d\nscore:%5.1f\n", pt->num, pt->score);
    return 0;
}
```

## 3.分析txt文件

```c
//
// Created by 30694 on 2024/1/19.
//
#include <stdio.h>
#include "stdlib.h"

#define LEN sizeof(struct Student)
struct Student {
    int order;  //序号
    int number;  //学号
    char name[20];  //姓名
    int grade;  //成绩
    struct Student *next;
};

int n;

struct Student *creat() {
    // 定义变量
    FILE *file;
    char line[100];
    struct Student *head = NULL;
    struct Student *p1, *p2;
    n = 0;

    // 打开txt文件
    file = fopen("成绩.txt", "r");
    if (file == NULL) {
        printf("无法打开文件\n");
        return (head);
    }

    //逐行读取学生数据并创建链表
    p1 = p2 = (struct Student *) malloc(LEN);//p2用于保留前一个学生，p1用于开辟新空间
    while (fgets(line, sizeof(line), file)) {
        sscanf(line, "%d %d %s %d", &p1->order, &p1->number, &p1->name, &p1->grade);
        n = n + 1;
        if (n == 1)head = p1;
        else p2->next = p1;
        p2 = p1;
        p1 = (struct Student *) malloc(LEN);
    }
    p2->next = NULL;
    fclose(file);
    return (head);
}

int main() {
    // 定义变量
    float total_num = 0;  //总人数
    float total_grade = 0;  //总成绩
    float average_grade;  //平均成绩
    int max_grade;
    char max_name[20];
    int max_number;
    int min_grade;
    char min_name[20];
    int min_number;
    struct Student *pt;
    struct Student *current;
    int a=0;
    //获取学生链表
    pt = creat();

    //读取学生链表
    current = pt;
    while (current != NULL) {
        a++;
        if(a==1){
            max_grade=current->grade;
            max_number=current->number;
            for (int i = 0; i < 20; ++i) max_name[i]=current->name[i];
            min_grade=current->grade;
            min_number=current->number;
            for (int i = 0; i < 20; ++i) min_name[i]=current->name[i];

        }
        if(max_grade<current->grade){
            max_grade=current->grade;
            max_number=current->number;
            for (int i = 0; i < 20; ++i) max_name[i]=current->name[i];
        }
        if(min_grade>current->grade){
            min_grade=current->grade;
            min_number=current->number;
            for (int i = 0; i < 20; ++i) min_name[i]=current->name[i];
        }
        total_num++;
        total_grade += current->grade;

        current = current->next;
    }

    average_grade = total_grade / total_num;
    printf("平均成绩为：%f\n",average_grade);
    printf("最高分:%d,姓名:%s,学号:%d\n",max_grade,max_name,max_number);
    printf("最低分:%d,姓名:%s,学号:%d\n",min_grade,min_name,min_number);

    return 0;
}
```

# 第03课 中(后)缀表达式

## 1.栈

==**先入后出**==的数据结构

## 2.中缀表达式转后缀表达式

![image-20240120225130069](C:\Users\30694\AppData\Roaming\Typora\typora-user-images\image-20240120225130069.png)

## 3.switch语句

```
switch (expression) {
    case constant1:
        // 代码块1
        break;
    case constant2:
        // 代码块2
        break;
    ...
    default:
        // 默认代码块
        break;
}

```

`switch` 语句由 `switch` 关键字、一个表达式和多个 `case` 分支组成。表达式的值会与每个 `case` 后面的常量进行比较，如果匹配成功，则执行该分支对应的代码块，然后使用 `break` 关键字跳出 `switch` 语句。如果没有匹配的分支，可以提供一个可选的 `default` 分支，用于处理其他情况。

以下是 `switch` 语句的工作原理：

1. 首先，计算表达式的值。
2. 将表达式的值与每个 `case` 后面的常量进行比较，直到找到匹配的分支。如果找到匹配的分支，则执行该分支对应的代码块，并跳出 `switch` 语句。
3. 如果没有找到匹配的分支，且有 `default` 分支，则执行 `default` 分支对应的代码块，并跳出 `switch` 语句。
4. 如果没有找到匹配的分支，且没有 `default` 分支，则直接跳出 `switch` 语句，继续执行下面的代码。

需要注意的是，在每个 `case` 分支的代码块中，通常需要使用 `break` 关键字来显式跳出 `switch` 语句，否则程序会继续执行下一个分支的代码块。如果不希望代码继续执行其他分支，应该在每个 `case` 分支的末尾加上 `break` 语句。

另外，`switch` 表达式的类型可以是整数类型（如 `int`、`char`）或枚举类型。不支持浮点数类型、字符串类型和其他复杂类型作为 `switch` 表达式的类型。

## 4.a++与++a的区别

1. `a++` 是后置自增运算符，它会先使用变量 `a` 的值，然后再将 `a` 的值加1。也就是说，先返回原始值再自增。
2. `++a` 是前置自增运算符，它会先将 `a` 的值加1，然后再使用更新后的 `a` 的值。也就是说，先自增再返回新值。

```c
int a = 5;
int b = a++; // 先将 a 的值赋给 b，再将 a 的值加1
// 此时，a 的值为 6，b 的值为 5

int c = 5;
int d = ++c; // 先将 c 的值加1，再将 c 的值赋给 d
// 此时，c 的值为 6，d 的值为 6

```

## 5.sprintf函数：整数转字符串

`sprintf(postfix + j, "%d", num);` 这行代码将整数 `num` 转换为字符串，并将结果存储在字符数组 `postfix` 中的指定位置。

`sprintf` 函数是 C 标准库中的一个函数，用于将格式化的数据写入字符串中。它的第一个参数是目标字符串的地址，第二个参数是格式化字符串，后续的参数是要填充到格式化字符串中的值。

在这行代码中，`postfix + j` 表示 `postfix` 字符数组中的偏移量，即从第 `j` 个位置开始存储转换后的字符串。`"%d"` 是格式化字符串，表示将整数值按照十进制格式进行转换。`num` 是要填充到格式化字符串中的整数值。

通过这行代码，将整数 `num` 转换为字符串，并将结果存储在 `postfix` 字符数组中指定的位置，以便后续的处理或输出。



sprintf函数是一个在C语言中用于格式化字符串输出的函数。它允许将格式化的数据写入一个字符串中，而不是直接打印到屏幕上。sprintf函数的原型如下：

```
c复制代码int sprintf(char *str, const char *format, ...)
```

其中，`str`是目标字符串的地址，`format`是格式化字符串，`...`表示可变参数列表。

sprintf函数将根据`format`参数的指定格式，将后续的可变参数转换成字符串，并写入到`str`指向的内存中。函数返回值为写入的字符数，不包括结尾的空字符。

下面是一个使用sprintf函数的示例：

```
c复制代码#include <stdio.h>

int main() {
    char buffer[50];
    int num = 123;
    float fnum = 3.14;

    sprintf(buffer, "Number: %d, Float Number: %.2f", num, fnum);
    printf("%s\n", buffer);

    return 0;
}
```

输出结果为：

```
复制代码Number: 123, Float Number: 3.14
```

在上述示例中，sprintf函数将整数`num`和浮点数`fnum`按照指定的格式写入到`buffer`字符串中。

## 6.单引号与双引号的区别

在C语言中，双引号(`"`)和单引号(`'`)具有不同的含义。

1. 双引号(`"`)表示字符串：双引号用于表示一个字符串字面值，在双引号内的字符序列会被视为一个字符串。例如，`"Hello, World!"` 是一个包含字符序列的字符串。
2. 单引号(`'`)表示字符：单引号用于表示一个字符字面值，在单引号内的字符会被视为一个字符常量。例如，`'A'` 表示大写字母A，`'x'` 表示小写字母x。

需要注意的是，双引号括起来的字符序列在内存中会被存储为连续的字符数组，以空字符(`'\0'`)作为字符串的结束标志。而单引号括起来的字符在内存中存储为对应的ASCII码值（或宽字符编码）。

例如，以下代码示例展示了双引号和单引号的使用区别：

```
#include <stdio.h>

int main() {
    // 字符串使用双引号
    char str[] = "Hello, World!";
    printf("%s\n", str); // 输出：Hello, World!

    // 字符使用单引号
    char ch = 'A';
    printf("%c\n", ch); // 输出：A

    return 0;
}
```

总结：

- 双引号(`"`)用于表示字符串，内存中以字符数组的形式存储。

- 单引号(`'`)用于表示字符，内存中存储对应的ASCII码值（或宽字符编码）。

  

## 7.memset函数：初始化

`memset()` 是 C 标准库中的一个函数，用于将一段内存空间的值设置为指定的数值。

函数原型如下：

```c
void *memset(void *s, int c, size_t n);
```

其中，函数参数解释如下：

- `s`：指向要填充的内存空间的指针。
- `c`：要填充的值，通常是一个无符号字符。
- `n`：要填充的字节数。

`memset()` 函数的作用是将 `s` 指向的内存空间中的前 `n` 个字节都设置为 `c` 的值。函数返回指向 `s` 的指针。

以下是一个简单的代码示例，演示了如何使用 `memset()` 函数将数组初始化为指定值：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[20];
    memset(str, 'A', sizeof(str)); // 将 str 数组中的每个元素都设置为 'A'
    printf("%s\n", str);

    return 0;
}
```

上述代码中，定义了一个长度为 20 的字符数组 `str`。通过 `memset()` 函数将数组中的每个元素都初始化为字符 `'A'`，然后使用 `printf()` 输出该数组的内容。输出结果为：

```c
AAAAAAAAAAAAAAAAAAAA
```

需要注意的是，由于 `memset()` 函数在填充内存时是按字节进行的，因此对于非字符类型的变量（如整型、浮点型等），需要进行类型转换后再传入函数。而且，该函数只适用于简单的内存空间填充，对于包含复杂数据结构的内存空间初始化，需要使用其他更加专业的函数或方法。

## 8. 代码案例

### 8.1 中缀表达式转后缀表达式

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

// 栈的实现
typedef struct {
    int *data;          // 栈的数据数组
    int capacity;       // 栈的容量
    int top;            // 栈顶指针
} Stack;

// 初始化栈
void initStack(Stack *stack, int capacity) {
    stack->data = (int *)malloc(sizeof(int) * capacity);
    stack->capacity = capacity;
    stack->top = -1;   // 初始化栈顶指针为-1，表示栈为空
}

// 释放栈
void freeStack(Stack *stack) {
    free(stack->data);
    stack->data = NULL;
    stack->capacity = 0;
    stack->top = -1;
}

// 判断栈是否为空
bool isEmpty(Stack *stack) {
    return stack->top == -1;
}

// 判断栈是否已满
bool isFull(Stack *stack) {
    return stack->top == stack->capacity - 1;
}

// 入栈
void push(Stack *stack, int value) {
    if (isFull(stack)) {
        printf("栈所装数据已满\n");
        exit(1);
    }
    stack->data[++stack->top] = value;   // 将元素放入栈顶，并将栈顶指针加1
}

// 出栈
int pop(Stack *stack) {
    if (isEmpty(stack)) {
        printf("栈数据为空\n");
        exit(1);
    }
    return stack->data[stack->top--];    // 返回栈顶元素，并将栈顶指针减1
}

// 获取栈顶元素
int peek(Stack *stack) {
    if (isEmpty(stack)) {
        printf("栈数据为空\n");
        exit(1);
    }
    return stack->data[stack->top];      // 返回栈顶元素
}

// 判断字符是否为数字
bool isDigit(char c) {
    return (c >= '0' && c <= '9');
}

// 获取运算符优先级
int getPriority(char c) {
    if (c == '+' || c == '-') {
        return 1;
    }
    if (c == '*' || c == '/') {
        return 2;
    }
    return 0;
}

// 将中缀表达式转换为后缀表达式
void infixToPostfix(char *infix, char *postfix) {
    Stack stack;  // 创建一个栈
    initStack(&stack, strlen(infix));  // strlen用于获取所输入的中缀表达式的长度
    int len = strlen(infix);  // 保存中缀表达式的长度
    int j = 0;

    // 循环处理每一个字符
    for (int i = 0; i < len; i++) {
        char c = infix[i];

        if (isDigit(c)) {
            // 如果是数字，找到连续的数字字符并合并成一个数字
            int num = c - '0';  // 通过ASCII码值相减,将字符c转换成整数
            while (i + 1 < len && isDigit(infix[i + 1])) {
                num = num * 10 + (infix[i + 1] - '0');
                i++;
            }
            // 将数字输出到后缀表达式中，并在数字后面添加 #
            sprintf(postfix + j, "%d", num);
            j += strlen(postfix + j);
            postfix[j++] = '#';
        } else if (c == '(') {
            // 如果是左括号，入栈
            push(&stack, c);
        } else if (c == ')') {
            // 如果是右括号，将栈中的运算符弹出并输出到后缀表达式中，直到遇到左括号
            while (!isEmpty(&stack) && peek(&stack) != '(') {
                postfix[j++] = pop(&stack);
            }
            if (!isEmpty(&stack) && peek(&stack) == '(') {
                pop(&stack);
            } else {
                printf("Mismatched parentheses\n");
                exit(1);
            }
        } else {
            // 如果是运算符，将栈中优先级大于等于该运算符的运算符弹出并输出到后缀表达式中，然后将当前运算符入栈
            while (!isEmpty(&stack) && peek(&stack) != '(' && getPriority(peek(&stack)) >= getPriority(c)) {
                postfix[j++] = pop(&stack);
            }
            push(&stack, c);
        }
    }

    // 将栈中剩余的运算符弹出并输出到后缀表达式中
    while (!isEmpty(&stack)) {
        if (peek(&stack) == '(') {
            printf("Mismatched parentheses\n");
            exit(1);
        }
        postfix[j++] = pop(&stack);
    }

    postfix[j] = '\0';   // 在后缀表达式的末尾添加字符串结束符
}

// 计算后缀表达式的值
int evaluatePostfix(char *postfix) {
    Stack stack;
    initStack(&stack, strlen(postfix));
    int len = strlen(postfix);

    for (int i = 0; i < len; i++) {
        char c = postfix[i];

        if (isDigit(c)) {
            // 如果是数字，找到连续的数字字符并合并成一个数字
            int num = c - '0';
            while (i + 1 < len && isDigit(postfix[i + 1])) {
                num = num * 10 + (postfix[i + 1] - '0');
                i++;
            }
            push(&stack, num);
        } else if (c == '#') {
            // 如果是数字字符后面的 # 符号，忽略它
            continue;
        } else {
            // 如果是运算符，弹出栈顶的两个数字进行计算，并将计算结果压入栈中
            int op2 = pop(&stack);
            int op1 = pop(&stack);
            int result;
            switch (c) {
                case '+':
                    result = op1 + op2;
                    break;
                case '-':
                    result = op1 - op2;
                    break;
                case '*':
                    result = op1 * op2;
                    break;
                case '/':
                    result = op1 / op2;
                    break;
                default:
                    printf("Invalid operator\n");
                    exit(1);
            }
            push(&stack, result);
        }
    }

    // 栈中剩余的元素就是表达式的值
    int result = pop(&stack);

    if (!isEmpty(&stack)) {
        printf("Invalid expression\n");
        exit(1);
    }

    return result;
}

int main() {
    char infix[100];
    printf("Enter an infix expression: ");
    scanf("%s", infix);

    char postfix[100];
    infixToPostfix(infix, postfix);
    printf("Postfix expression: %s\n", postfix);

    int result = evaluatePostfix(postfix);
    printf("Result: %d\n", result);

    return 0;
}

```

### 8.2 力扣316题去除重复字母

```c
-#include "stdio.h"
#include "stdlib.h"
#include "string.h"

char *removeDuplicateLetters(char *s) {
    int vis[26], num[26];
    memset(vis, 0, sizeof(vis));  // 字母是否被访问
    memset(num, 0, sizeof(num));  // 相对应的字母有多少个

    int n = strlen(s);  // 一共有多少个字母
    // 统计每个字母出现的次数
    for (int i = 0; i < n; i++) {
        num[s[i] - 'a']++;
    }
    //开辟一块新空间作为栈
    char *stk = malloc(sizeof(char) * 27);  // 26个字母和'/0'
    int stkTop = 0;  // 栈顶指针
    for (int i = 0; i < n; i++) {
        if (!vis[s[i] - 'a']) {  //当前字母未被访问
            while (stkTop > 0 && stk[stkTop - 1] > s[i]) {  // 栈顶指针不为0，并且当前字母ASCII码值小于栈中的最后一个字母
                if (num[stk[stkTop - 1] - 'a'] > 0) {  // 栈中最后一个字母在后面字符串中仍会出现
                    stkTop--;
                    vis[stk[stkTop] - 'a'] = 0;  // 将栈顶字母重新标记为未访问
                } else {
                    break;
                }
            }
            vis[s[i] - 'a'] = 1;  // 将当前字母标记为已访问
            stk[stkTop] = s[i];  // 将当前字母加入栈中
            stkTop++;
        }
        num[s[i] - 'a'] -= 1;
    }
    stk[stkTop] = '\0';  // 作为字符串输出
    return stk;
}

int main() {
    char *a[100];
    char *b;
    scanf("%s", a);
    b = removeDuplicateLetters(a);
    printf("%s",b);
}
```

# 第04课表达式求值

## 1.strcmp函数：字符串大小比较

string.h库函数

strcmp函数是C语言中的字符串比较函数，用于比较两个字符串的大小关系。

函数原型如下：

```c
int strcmp(const char *str1, const char *str2);
```

该函数接受两个参数，分别是要比较的两个字符串的指针。比较过程是按照字典序逐个字符进行比较，直到遇到不同的字符或者其中一个字符串结束（即遇到'\0'空字符）为止。

- 如果两个字符串相等，则返回值为0。
- 如果第一个字符串大于第二个字符串，则返回一个正数。
- 如果第一个字符串小于第二个字符串，则返回一个负数。

下面是一个简单的示例代码，演示了如何使用strcmp函数：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "World";

    int result = strcmp(str1, str2);

    if (result == 0) {
        printf("str1 and str2 are equal\n");
    } else if (result < 0) {
        printf("str1 is less than str2\n");
    } else {
        printf("str1 is greater than str2\n");
    }

    return 0;
}
```

输出结果为："str1 is less than str2"，因为'H'的ASCII码值小于'W'的ASCII码值。

## 2.atoi函数：字符串转整数

atoi函数是C语言中的字符串转整数函数，用于将字符串表示的数字转换为对应的整数值。

函数原型如下：

```c
int atoi(const char *str);
```

该函数接受一个参数，即要转换的字符串的指针。它会从字符串的开头开始解析，直到遇到非数字字符为止，然后将解析到的数字部分转换为对应的整数值。

下面是一个简单的示例代码，演示了如何使用atoi函数：

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char str[] = "12345";
    int num = atoi(str);

    printf("The converted number is: %d\n", num);

    return 0;
}
```

输出结果为："The converted number is: 12345"，将字符串"12345"转换为相应的整数。

需要注意的是，如果字符串无法正确解析成整数，atoi函数会返回0。另外，如果字符串表示的整数超过了int类型的范围，结果也会不准确。

## 3.strtol函数：字符串转长整数

`strtol()` 函数是 C 语言标准库 `<stdlib.h>` 中的一个函数，用于将一个字符串转换为一个长整型数。

其函数原型如下：

```
long int strtol(const char *str, char **endptr, int base);
```

其中：

- `str`：需要转换为长整型数的字符串。
- `endptr`：指向字符指针的指针，用于存储第一个无法转换的字符的指针。也就是说，如果 `str` 中的某个字符无法被解析成数字，则 `endptr` 指向这个字符，否则 `endptr` 为 NULL。该参数可以为 NULL，表示不需要返回无法转换的字符。
- `base`：进制数，即要转换的数字是几进制的。如果 `base` 为 0，则根据字符串的前缀来判断进制数。如果 `str` 不带前缀或前缀无法识别，则默认为十进制；如果带有 `0x` 或 `0X` 前缀，则为十六进制；如果带有 `0` 前缀，则为八进制。

函数返回值为转换后的长整型数。如果发生错误（例如字符串中包含非法字符），则返回 `0`。

例如，下面代码演示了如何使用 `strtol()` 函数将一个字符串转换为长整型数：

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char str[] = "123456";
    char *endptr;
    long int num = strtol(str, &endptr, 10);
    printf("The number is %ld\n", num);
    printf("The end pointer is %s\n", endptr);
    return 0;
}
```

程序输出如下：

```
The number is 123456
The end pointer is
```

在这个例子中，我们将字符串 `"123456"` 转换为长整型数，指定进制数为 `10`。`endptr` 指向的字符指针为 NULL，表示字符串中所有字符都成功转换为数字。最后，我们将转换后的长整型数打印出来。

需要注意的是，在使用 `strtol()` 函数时，一定要根据实际需求设置好进制数和 `endptr` 参数。否则，可能会导致转换错误或无法正确处理字符串中的特殊字符。

## 4.代码示例

### 4.1 后缀表达式求值

```c
//
// Created by 30694 on 2024/1/21.
//
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

// 栈的实现
typedef struct {
    int *data;          // 栈的数据数组
    int capacity;       // 栈的容量
    int top;            // 栈顶指针
} Stack;

// 初始化栈
void initStack(Stack *stack, int capacity) {
    stack->data = (int *)malloc(sizeof(int) * capacity);
    stack->capacity = capacity;
    stack->top = -1;   // 初始化栈顶指针为-1，表示栈为空
}

// 释放栈
void freeStack(Stack *stack) {
    free(stack->data);
    stack->data = NULL;
    stack->capacity = 0;
    stack->top = -1;
}

// 判断栈是否为空
bool isEmpty(Stack *stack) {
    return stack->top == -1;
}

// 判断栈是否已满
bool isFull(Stack *stack) {
    return stack->top == stack->capacity - 1;
}

// 入栈
void push(Stack *stack, int value) {
    if (isFull(stack)) {
        printf("栈所装数据已满\n");
        exit(1);
    }
    stack->data[++stack->top] = value;   // 将元素放入栈顶，并将栈顶指针加1
}

// 出栈
int pop(Stack *stack) {
    if (isEmpty(stack)) {
        printf("栈数据为空\n");
        exit(1);
    }
    return stack->data[stack->top--];    // 返回栈顶元素，并将栈顶指针减1
}

// 获取栈顶元素
int peek(Stack *stack) {
    if (isEmpty(stack)) {
        printf("栈数据为空\n");
        exit(1);
    }
    return stack->data[stack->top];      // 返回栈顶元素
}

// 判断字符是否为数字
bool isDigit(char c) {
    return (c >= '0' && c <= '9');
}

// 获取运算符优先级
int getPriority(char c) {
    if (c == '+' || c == '-') {
        return 1;
    }
    if (c == '*' || c == '/') {
        return 2;
    }
    return 0;
}

// 将中缀表达式转换为后缀表达式
void infixToPostfix(char *infix, char *postfix) {
    Stack stack;  // 创建一个栈
    initStack(&stack, strlen(infix));  // strlen用于获取所输入的中缀表达式的长度
    int len = strlen(infix);  // 保存中缀表达式的长度
    int j = 0;

    // 循环处理每一个字符
    for (int i = 0; i < len; i++) {
        char c = infix[i];

        if (isDigit(c)) {
            // 如果是数字，找到连续的数字字符并合并成一个数字
            int num = c - '0';  // 通过ASCII码值相减,将字符c转换成整数
            while (i + 1 < len && isDigit(infix[i + 1])) {
                num = num * 10 + (infix[i + 1] - '0');
                i++;
            }
            // 将数字输出到后缀表达式中，并在数字后面添加 #
            sprintf(postfix + j, "%d", num);
            j += strlen(postfix + j);
            postfix[j++] = '#';
        } else if (c == '(') {
            // 如果是左括号，入栈
            push(&stack, c);
        } else if (c == ')') {
            // 如果是右括号，将栈中的运算符弹出并输出到后缀表达式中，直到遇到左括号
            while (!isEmpty(&stack) && peek(&stack) != '(') {
                postfix[j++] = pop(&stack);
            }
            // 遇到左括号后，直接将左括号从栈中去除
            if (!isEmpty(&stack) && peek(&stack) == '(') {
                pop(&stack);
            } else {
                printf("括号不匹配\n");
                exit(1);
            }
        } else {
            // 如果是运算符，将栈中优先级大于等于该运算符的运算符弹出并输出到后缀表达式中，然后将当前运算符入栈
            while (!isEmpty(&stack) && peek(&stack) != '(' && getPriority(peek(&stack)) >= getPriority(c)) {
                postfix[j++] = pop(&stack);
            }
            push(&stack, c);
        }
    }

    // 将栈中剩余的运算符弹出并输出到后缀表达式中
    while (!isEmpty(&stack)) {
        if (peek(&stack) == '(') {
            printf("括号不匹配\n");
            exit(1);
        }
        postfix[j++] = pop(&stack);
    }

    postfix[j] = '\0';   // 在后缀表达式的末尾添加字符串结束符
}

// 计算后缀表达式的值
int evaluatePostfix(char *postfix) {
    Stack stack;  // 创建栈结构体
    initStack(&stack, strlen(postfix));  // 初始化栈
    int len = strlen(postfix);  //字符串长度
    // 遍历字符串
    for (int i = 0; i < len; i++) {
        char c = postfix[i];

        if (isDigit(c)) {
            // 如果是数字，找到连续的数字字符并合并成一个数字
            int num = c - '0';  // 将字符变量转换成数字变量
            while (i + 1 < len && isDigit(postfix[i + 1])) {
                num = num * 10 + (postfix[i + 1] - '0');
                i++;
            }
            push(&stack, num);  // 入栈
        } else if (c == '#') {
            // 如果是数字字符后面的 # 符号，忽略它
            continue;
        } else {
            // 如果是运算符，弹出栈顶的两个数字进行计算，并将计算结果压入栈中
            int op2 = pop(&stack);
            int op1 = pop(&stack);
            int result;
            switch (c) {
                case '+':
                    result = op1 + op2;
                    break;
                case '-':
                    result = op1 - op2;
                    break;
                case '*':
                    result = op1 * op2;
                    break;
                case '/':
                    result = op1 / op2;
                    break;
                default:
                    printf("无效运算符\n");
                    exit(1);
            }
            push(&stack, result);  // 将结果入栈
        }
    }

    // 栈中剩余的元素就是表达式的值
    int result = pop(&stack);

    if (!isEmpty(&stack)) {
        printf("表达式无效\n");
        exit(1);
    }

    return result;
}

int main() {
    char infix[100];
    printf("请输入中缀表达式: \n");
    scanf("%s", infix);

    char postfix[100];
    infixToPostfix(infix, postfix);
    printf("转换为后缀表达式的结果为: %s\n", postfix);

    int result = evaluatePostfix(postfix);
    printf("运算结果为: %d\n", result);

    return 0;
}

```

### 4.2 力扣150逆波兰表达式求值

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_SIZE 100

// 定义栈结构
typedef struct {
    int* data;  // 存储栈元素的数组指针
    int top;    // 栈顶指针
} Stack;

// 初始化栈
void initStack(Stack* stack) {
    stack->data = (int*)malloc(MAX_SIZE * sizeof(int));  // 分配栈元素数组的内存空间
    stack->top = -1;  // 初始化栈顶指针为-1，表示栈为空
}

// 入栈
void push(Stack* stack, int value) {
    stack->top++;  // 栈顶指针加一
    stack->data[stack->top] = value;  // 将元素放入栈顶位置
}

// 出栈
int pop(Stack* stack) {
    int value = stack->data[stack->top];  // 获取栈顶元素的值
    stack->top--;  // 栈顶指针减一
    return value;  // 返回栈顶元素的值
}

// 判断是否为操作符
int isOperator(char* token) {
    return (strcmp(token, "+") == 0 || strcmp(token, "-") == 0 ||
            strcmp(token, "*") == 0 || strcmp(token, "/") == 0);
}

// 计算逆波兰表达式
int evalRPN(char** tokens, int tokensSize) {
    Stack stack;
    initStack(&stack);

    for (int i = 0; i < tokensSize; i++) {
        if (isOperator(tokens[i])) {
            int num2 = pop(&stack);
            int num1 = pop(&stack);
            int result;

            if (strcmp(tokens[i], "+") == 0) {
                result = num1 + num2;
            } else if (strcmp(tokens[i], "-") == 0) {
                result = num1 - num2;
            } else if (strcmp(tokens[i], "*") == 0) {
                result = num1 * num2;
            } else if (strcmp(tokens[i], "/") == 0) {
                result = num1 / num2;
            }

            push(&stack, result);
        } else {
            push(&stack, atoi(tokens[i]));
        }
    }

    int result = pop(&stack);
    free(stack.data);

    return result;
}

int main() {
    char* tokens[] = {"2", "1", "+", "3", "*"};
    int tokensSize = sizeof(tokens) / sizeof(tokens[0]);

    int result = evalRPN(tokens, tokensSize);
    printf("结果为: %d\n", result);

    return 0;
}
```

# 第05课成绩计算与查询

## 1.do-while循环语句

do-while 循环语句是一种先执行循环体再判断循环条件的循环语句，保证循环体至少被执行一次。

do-while 语句的基本形式如下：

```
do {
    循环体语句;
} while (循环条件);
```

其中，循环体语句是需要重复执行的语句块，循环条件是一个表达式，用于判断是否继续执行循环体语句。当循环条件为真时，继续执行循环体语句；当循环条件为假时，跳出循环。

下面是一个简单的示例程序，演示了 do-while 循环语句的使用：

```
#include <stdio.h>

int main() {
    int i = 1;
    do {
        printf("%d ", i);
        i++;
    } while (i <= 5);
    return 0;
}
```

上面的程序会输出：1 2 3 4 5

首先，i 被初始化为 1；然后，do-while 循环体语句会被执行，打印出 i 的值，并将 i 加 1。然后，循环条件判断 i 是否小于或等于 5，由于 i 目前是 2，满足条件，所以循环体语句会被再次执行，打印出 i 的值，再将 i 加 1。这个过程会一直重复，直到 i 不满足循环条件为止。由于 i 在第五次循环时的值是 6，不再满足循环条件，所以程序跳出循环。

## 2. sscanf函数：解析字符串

`sscanf` 函数可以用来从一个字符串中按照指定的格式提取数据。它的基本格式如下：

```
int sscanf(const char *str, const char *format, ...);
```

其中，`str` 是要解析的字符串，`format` 是格式字符串，后面可以跟上要被解析的变量，根据 `format` 字符串中的格式控制符来决定如何解析字符串，并将解析结果存储到相应的变量中。

下面是一些常见的格式控制符：

- `%d`：匹配一个整数。
- `%f`：匹配一个浮点数。
- `%s`：匹配一个字符串（以空格或换行符为结束）。
- `%c`：匹配一个字符。
- `%[a-z]`：匹配一个小写字母。
- `%[^a-z]`：匹配一个非小写字母。

例如，假设有如下字符串：

```c
char str[] = "123 John 80";
```

我们可以使用 `sscanf` 将其中的整数、字符串和浮点数提取出来：

```c
int num;
char name[20];
float score;

sscanf(str, "%d %s %f", &num, name, &score);
```

在这个例子中，`%d` 匹配并提取整数，`%s` 匹配并提取字符串，`%f` 匹配并提取浮点数。

需要注意的是，在使用 `sscanf` 解析字符串时，要确保 `format` 字符串与要解析的字符串的格式相匹配，否则可能会导致解析错误或未定义的行为。

## 3.示例

### 3.1 读取数据

```c
//
// Created by 30694 on 2024/1/24.
//
#include "stdio.h"
#include "string.h"

#define MAX_FILENAME_LENGTH 100
#define MAX_NAME_LENGTH 50
#define MAX_NUM_STUDENTS 200

typedef struct {
    int order;  // 序号
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[5];  // 性别
    char class[20];  // 班级
    int grade1;
    int grade2;
    int grade3;
    int average_grade;
} Student;


int main() {
    char filenames[3][MAX_FILENAME_LENGTH] = {
            "598854.txt",
            "598856.txt",
            "598858.txt"
    };

    char newFilenames[3][MAX_FILENAME_LENGTH] = {
            "new_598854.txt",
            "new_598856.txt",
            "new_598858.txt"
    };

    FILE *file;
    FILE *newFile;
    Student students[MAX_NUM_STUDENTS];

    // 处理每个文本文件
    for (int i = 0; i < 3; i++) {
        // 打开原文件
        file = fopen(filenames[i], "r");
        if (file == NULL) {
            printf("无法打开文件: %s\n", filenames[i]);
            return 1;
        }

        // 创建新文件
        newFile = fopen(newFilenames[i], "w");
        if (newFile == NULL) {
            printf("无法创建文件: %s\n", newFilenames[i]);
            fclose(file);
            return 1;
        }
        int numStudents = 0;
        char line[MAX_NAME_LENGTH + 10];

        // 逐行读取原文件
        while (fgets(line, sizeof(line), file) != NULL) {
            // 解析姓名和成绩
            int order;
            int num;
            char name[MAX_NAME_LENGTH];
            char gender[5];
            char class[20];
            int grade1;
            int grade2;
            int grade3;
            sscanf(line, "%d %d %s %s %s %d %d %d",
                   &order, &num, name, gender, class, &grade1, &grade2, &grade3);

            // 添加到结构体数组中
            students[numStudents].order = order;
            students[numStudents].num = num;
            strcpy(students[numStudents].name, name);
            strcpy(students[numStudents].gender, gender);
            strcpy(students[numStudents].class, class);
            students[numStudents].grade1 = grade1;
            students[numStudents].grade2 = grade2;
            students[numStudents].grade3 = grade3;
            students[numStudents].average_grade = (grade1 + grade2 + grade3) / 3;
            numStudents++;
        }


        // 将结果写入新文件
        for (int j = 0; j < numStudents; j++) {
            fprintf(newFile, "%d %d %s %s %s %d %d %d %d\n",
                    students[j].order, students[j].num, students[j].name,
                    students[j].gender, students[j].class,
                    students[j].grade1, students[j].grade2, students[j].grade3,
                    students[j].average_grade);
        }

        // 关闭文件
        fclose(file);
        fclose(newFile);
    }
}
```

### 3.2  查询数据

```c
//
// Created by 30694 on 2024/1/24.
//
#include "stdio.h"
#include "string.h"

#define MAX_FILENAME_LENGTH 100
#define MAX_NAME_LENGTH 100
#define MAX_NUM_STUDENTS 500

// 学生结构体
typedef struct {
    int order;  // 序号
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[5];  // 性别
    char class[20];  // 班级
    int grade1;
    int grade2;
    int grade3;
    int average_grade;
} Student;


// 查询学生成绩函数
void searchStudentScore(Student students[], int numStudents) {
    int searchId;
    char searchName[MAX_NAME_LENGTH];
    int found = 0;
    int option;
    printf("请选择查询方式:\n1.学号\n2.姓名");
    scanf("%d", &option);
    if (option == 1) {
        printf("请输入学号：");
        scanf("%d", &searchId);
    } else if (option == 2) {
        printf("请输入姓名：");
        scanf("%s", searchName);
    }

    // 遍历学生数组，查找匹配的学生信息
    for (int i = 0; i < numStudents; i++) {
        if ((option == 1 && students[i].num == searchId) ||
            (option == 2 && strcmp(students[i].name, searchName) == 0)) {
            printf("序号\t学号\t\t姓名\t性别\t班级\t\t进制转换\t多进制转换\t数值表达逻辑代数\t平均成绩\n");
            printf("%d\t%d\t%s\t%s\t%s\t%d\t\t%d\t\t%d\t\t\t%d\n",
                   students[i].order, students[i].num,
                   students[i].name, students[i].gender, students[i].class,
                   students[i].grade1, students[i].grade2, students[i].grade3,
                   students[i].average_grade);
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("未找到匹配的学生信息。\n");
    }
}

int main() {
    // 定义变量
    Student students[MAX_NUM_STUDENTS];  // 学生结构体
    FILE *file;  // 文件指针
    int numStudents = 0;  // 第几个学生

    // 文件名
    char newFilenames[3][MAX_FILENAME_LENGTH] = {
            "new_598854.txt",
            "new_598856.txt",
            "new_598858.txt"
    };

    // 读取三个文件，写入结构体中
    for (int i = 0; i < 3; ++i) {
        // 写读模式打开文件
        file = fopen(newFilenames[i], "r");

        // 如果为空，结束程序
        if (file == NULL) {
            printf("无法打开文件: %s\n", newFilenames[i]);
            return 1;
        }
        char line[MAX_NAME_LENGTH + 10];

        while (fgets(line, sizeof(line), file) != NULL) {
            // 解析姓名和成绩
            int order;
            int num;
            char name[MAX_NAME_LENGTH];
            char gender[5];
            char class[20];
            int grade1;
            int grade2;
            int grade3;
            sscanf(line, "%d %d %s %s %s %d %d %d",
                   &order, &num, name, gender, class, &grade1, &grade2, &grade3);

            // 添加到结构体数组中
            students[numStudents].order = order;
            students[numStudents].num = num;
            strcpy(students[numStudents].name, name);
            strcpy(students[numStudents].gender, gender);
            strcpy(students[numStudents].class, class);
            students[numStudents].grade1 = grade1;
            students[numStudents].grade2 = grade2;
            students[numStudents].grade3 = grade3;
            students[numStudents].average_grade = (grade1 + grade2 + grade3) / 3;
            numStudents++;
        }
    }

    int n=1;
    while (n==1) {
        searchStudentScore(students, numStudents);
        printf("是否继续查询 1.继续\t2.结束");
        scanf("%d", &n);
    }
}
```

# 第06课二分查找作业

## 1.指针算术

指针算术是指在指针类型上进行数学运算的操作。在C语言中，指针算术可以用于对指针进行偏移、定位和遍历数组等操作。

常见的指针算术操作包括：

- 指针加法：将指针向前移动n个元素大小的偏移量。例如，`ptr + n`将指针ptr增加了n个元素的偏移量。
- 指针减法：将指针向后移动n个元素大小的偏移量。例如，`ptr - n`将指针ptr减少了n个元素的偏移量。
- 指针与整数的加法和减法：可以将整数值直接加到指针上，或者从指针中减去整数值。这会根据指针所指向的类型进行适当的偏移计算。例如，`ptr + 3`将指针ptr向前移动3个元素的偏移量。

指针算术的结果仍然是一个指针，它指向新的内存位置。需要注意的是，指针算术操作应该在有效的内存范围内进行，以避免越界访问。

## 2.rand函数：伪随机数生成

C语言中的rand()函数是一个伪随机数生成函数，它能够生成一个范围在0到RAND_MAX之间的整数（RAND_MAX是一个常量，表示随机数的最大值，它通常被定义为32767）。

在使用rand()函数时，我们通常需要先调用srand()函数来设置随机数生成器的种子。如果不设置种子，则每次程序运行时都会生成相同的随机数序列。一般情况下，我们可以使用time()函数来获取当前时间作为种子，例如:

```
#include <stdlib.h>
#include <time.h>

int main() {
    srand((unsigned)time(NULL));   // 设置随机数种子
    int random_num = rand();    // 生成一个随机数
    return 0;
}
```

如果需要生成一个在指定范围内的随机数，可以使用取余运算对随机数进行限制，例如：

```
复制代码int random_num = rand() % 100;  // 生成一个0-99之间的随机数
```

需要注意的是，C语言中的rand()函数生成的随机数并不是真正的随机数，而是伪随机数。如果需要更高质量的随机性，可以考虑使用C++11引入的<random>头文件中的随机数生成器

## 3.示例

### 3.1 score

```
//
// Created by 30694 on 2024/1/25.
//
//
// Created by 30694 on 2024/1/24.
//
#include "stdio.h"
#include "string.h"

#define MAX_FILENAME_LENGTH 100
#define MAX_NAME_LENGTH 50
#define MAX_NUM_STUDENTS 200

typedef struct {
    int order;  // 序号
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[5];  // 性别
    char class[20];  // 班级
    int grade1;
    int grade2;
    int grade3;
    int average_grade;
} Student;


int main() {
    char filenames[3][MAX_FILENAME_LENGTH] = {
            "598854.txt",
            "598856.txt",
            "598858.txt"
    };

    char newFilenames[3][MAX_FILENAME_LENGTH] = {
            "new2_598854.txt",
            "new2_598856.txt",
            "new2_598858.txt"
    };

    FILE *file;
    FILE *newFile;
    Student students[MAX_NUM_STUDENTS];

    // 处理每个文本文件
    for (int i = 0; i < 3; i++) {
        // 打开原文件
        file = fopen(filenames[i], "r");
        if (file == NULL) {
            printf("无法打开文件: %s\n", filenames[i]);
            return 1;
        }

        // 创建新文件
        newFile = fopen(newFilenames[i], "w");
        if (newFile == NULL) {
            printf("无法创建文件: %s\n", newFilenames[i]);
            fclose(file);
            return 1;
        }
        int numStudents = 0;
        char line[MAX_NAME_LENGTH + 10];

        // 逐行读取原文件
        while (fgets(line, sizeof(line), file) != NULL) {
            // 解析姓名和成绩
            int order;
            int num;
            char name[MAX_NAME_LENGTH];
            char gender[5];
            char class[20];
            int grade1;
            int grade2;
            int grade3;
            sscanf(line, "%d %d %s %s %s %d %d %d",
                   &order, &num, name, gender, class, &grade1, &grade2, &grade3);

            // 添加到结构体数组中
            students[numStudents].order = order;
            students[numStudents].num = num;
            strcpy(students[numStudents].name, name);
            strcpy(students[numStudents].gender, gender);
            strcpy(students[numStudents].class, class);
            students[numStudents].grade1 = grade1;
            students[numStudents].grade2 = grade2;
            students[numStudents].grade3 = grade3;
            students[numStudents].average_grade = (grade1 + grade2 + grade3) / 3;
            numStudents++;
        }


        // 将结果写入新文件
        for (int j = 0; j < numStudents; j++) {
            fprintf(newFile, "%d %s %s %s %d %d %d %d\n",
                    students[j].num, students[j].name,
                    students[j].gender, students[j].class,
                    students[j].grade1, students[j].grade2, students[j].grade3,
                    students[j].average_grade);
        }

        // 关闭文件
        fclose(file);
        fclose(newFile);
    }
}
```

### 3.2 循环

```
//
// Created by 30694 on 2024/1/25.
//
#include "stdio.h"
#include "stdlib.h"
#include "string.h"

#define MAX_NAME_LENGTH 50  // 学生姓名长度
#define MAX_NUM_STUDENTS 400  // 学生结构体数量

// 学生结构体
typedef struct {
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[5];  // 性别
    char class[20];  // 班级
    float grade1;
    float grade2;
    float grade3;
    float average_grade;
} Student;

Student students[MAX_NUM_STUDENTS];  // 学生结构体数组
int numStudents = 0;  // 学生数量

// 读取数据
void ReadScore() {
    FILE *file;  // 文件指针

    // 打开原成绩文件
    file = fopen("score.txt", "r");
    if (file == NULL) {
        printf("无法打开文件: %s\n", "score.txt");
        exit(1);
    }

    // 将学生数据存入数组
    char line[MAX_NAME_LENGTH + 10];
    while (fgets(line, sizeof(line), file) != NULL) {
        // 解析姓名和成绩
        int num;
        char name[MAX_NAME_LENGTH];
        char gender[5];
        char class[20];
        float grade1;
        float grade2;
        float grade3;
        sscanf(line, "%d %s %s %s %f %f %f",
               &num, name, gender, class, &grade1, &grade2, &grade3);

        // 添加到结构体数组中
        students[numStudents].num = num;
        strcpy(students[numStudents].name, name);
        strcpy(students[numStudents].gender, gender);
        strcpy(students[numStudents].class, class);
        students[numStudents].grade1 = grade1;
        students[numStudents].grade2 = grade2;
        students[numStudents].grade3 = grade3;
        students[numStudents].average_grade = (grade1 + grade2 + grade3) / 3;
        numStudents++;
    }
}

// 按照学号排序
void SortByNumber() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (students[j].num > students[j + 1].num) {
                // 交换位置
                Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
}

// 按照姓名排序
void SortByName() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (strcmp(students[j].name, students[j + 1].name) > 0) {
                // 交换位置
                Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
}

// 按照平均成绩排序
void SortByAverageGrade() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (students[j].average_grade > students[j + 1].average_grade) {
                // 交换位置
                Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            } else if (students[j].average_grade == students[j + 1].average_grade) {
                // 平均成绩相同，按照学号排序
                if (students[j].num > students[j + 1].num) {
                    // 交换位置
                    Student temp = students[j];
                    students[j] = students[j + 1];
                    students[j + 1] = temp;
                }
            }
        }
    }
}

// 按照学号查询学生
int SearchByNumber(int targetNum) {
    SortByNumber();
    int left = 0;
    int right = numStudents - 1;

    while (left <= right) {
        int mid = (left + right) / 2;
        if (students[mid].num == targetNum) {
            return mid;  // 找到目标学号，返回下标
        } else if (students[mid].num < targetNum) {
            left = mid + 1;  // 目标学号在右半部分，缩小搜索范围
        } else {
            right = mid - 1;  // 目标学号在左半部分，缩小搜索范围
        }
    }

    return -1;  // 没有找到目标学号，返回 -1
}

// 按照姓名查询学生
int SearchByName(char *targetName) {
    SortByName();
    int left = 0;
    int right = numStudents - 1;

    while (left <= right) {
        int mid = (left + right) / 2;
        int cmpResult = strcmp(students[mid].name, targetName);
        if (cmpResult == 0) {
            return mid;  // 找到目标姓名，返回下标
        } else if (cmpResult < 0) {
            left = mid + 1;  // 目标姓名在右半部分，缩小搜索范围
        } else {
            right = mid - 1;  // 目标姓名在左半部分，缩小搜索范围
        }
    }

    return -1;  // 没有找到目标姓名，返回 -1
}

// 按照平均成绩查询
int SearchByAverageGrade(float targetGrade) {
    SortByAverageGrade();
    int left = 0;
    int right = numStudents - 1;

    while (left <= right) {
        int mid = (left + right) / 2;
        if (students[mid].average_grade == targetGrade) {
            return mid;  // 找到目标平均成绩，返回下标
        } else if (students[mid].average_grade < targetGrade) {
            left = mid + 1;  // 目标平均成绩在右半部分，缩小搜索范围
        } else {
            right = mid - 1;  // 目标平均成绩在左半部分，缩小搜索范围
        }
    }

    return -1;  // 没有找到目标平均成绩，返回 -1
}

// 打印学生信息
void printStudentInfo(int index) {
    printf("学号\t\t姓名\t性别\t班级\t\t进制转换\t多进制转换\t数值表达逻辑代数\t平均成绩\n");
    printf("%d\t%s\t%s\t%s\t%.0f\t\t%.0f\t\t%.0f\t\t\t%.2f\n",
           students[index].num,
           students[index].name, students[index].gender, students[index].class,
           students[index].grade1, students[index].grade2, students[index].grade3,
           students[index].average_grade);
}

// 选择查找方法
void SelectSearch() {
    int select;
    printf("请选择查询方式：1.学号\t2.姓名\t3.平均成绩\t");
    scanf("%d", &select);

    switch (select) {
        case 1: {
            int targetNum;
            printf("请输入要查询的学号");
            scanf("%d", &targetNum);
            int index = SearchByNumber(targetNum);
            if (index != -1) {
                printStudentInfo(index);
            } else {
                printf("没有找到该学号对应的学生数据。\n");
            }
            break;
        }
        case 2: {
            char targetName[20];
            printf("请输入学生姓名：");
            scanf("%s", targetName);
            int index = SearchByName(targetName);
            if (index != -1) {
                printStudentInfo(index);
            } else {
                printf("没有找到该学号对应的学生数据。\n");
            }
            break;
        }
        case 3: {
            float targetAverageGrade;
            printf("请输入平均成绩：");
            scanf("%f", &targetAverageGrade);
            int index = SearchByAverageGrade(targetAverageGrade);
            if (index != -1) {
                printStudentInfo(index);
                for (int found = 0; found < numStudents; ++found) {
                    if (students[found].average_grade == students[index].average_grade) {
                        printf("%d\t%s\t%s\t%s\t%.0f\t\t%.0f\t\t%.0f\t\t\t%.2f\n",
                               students[found].num,
                               students[found].name, students[found].gender, students[found].class,
                               students[found].grade1, students[found].grade2, students[found].grade3,
                               students[found].average_grade);
                    }
                }
            } else {
                printf("没有找到该学号对应的学生数据。\n");
            }
            break;
        }
        default:
            printf("输入错误！");
    }

    int n;
    printf("是否继续查询 1.继续\t2.结束");
    scanf("%d", &n);
    if (n == 1) {
        SelectSearch();
    }
}

int main() {
    ReadScore();  // 读取学生数据
    SelectSearch();  // 开始查询
    return 0;
}


```

### 3.3 递归

```
#include <stdio.h>
#include <string.h>
#include "stdlib.h"
#include "wchar.h"

#define MAX_NAME_LENGTH 50  // 学生姓名长度
#define MAX_NUM_STUDENTS 400  // 学生结构体数量

struct Student {
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[5];  // 性别。
    char class[20];  // 班级
    float grade1;
    float grade2;
    float grade3;
    float average_grade;
};

struct Student students[MAX_NUM_STUDENTS];  // 学生结构体数组
int numStudents = 0;  // 实际学生数量

// 读取数据
void ReadScore() {
    FILE *file;  // 文件指针

    // 打开原成绩文件
    file = fopen("score.txt", "r");
    if (file == NULL) {
        printf("无法打开文件: %s\n", "score.txt");
        exit(1);
    }

    // 将学生数据存入数组
    char line[MAX_NAME_LENGTH + 10];
    while (fgets(line, sizeof(line), file) != NULL) {
        // 解析姓名和成绩
        int num;
        char name[MAX_NAME_LENGTH];
        char gender[5];
        char class[20];
        float grade1;
        float grade2;
        float grade3;
        sscanf(line, "%d %s %s %s %f %f %f",
               &num, name, gender, class, &grade1, &grade2, &grade3);

        // 添加到结构体数组中
        students[numStudents].num = num;
        strcpy(students[numStudents].name, name);
        strcpy(students[numStudents].gender, gender);
        strcpy(students[numStudents].class, class);
        students[numStudents].grade1 = grade1;
        students[numStudents].grade2 = grade2;
        students[numStudents].grade3 = grade3;
        students[numStudents].average_grade = (grade1 + grade2 + grade3) / 3;
        numStudents++;
    }
}

// 按学号排序
void SortByNumber() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (students[j].num > students[j + 1].num) {
                // 交换位置
                struct Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
}

// 按姓名排序
void SortByName() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (strcmp(students[j].name, students[j + 1].name) > 0) {
                // 交换位置
                struct Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
}

// 按平均成绩排序
void SortByAverageGrade() {
    for (int i = 0; i < numStudents - 1; i++) {
        for (int j = 0; j < numStudents - i - 1; j++) {
            if (students[j].average_grade > students[j + 1].average_grade) {
                // 交换位置
                struct Student temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            } else if (students[j].average_grade == students[j + 1].average_grade) {
                // 平均成绩相同，按照学号排序
                if (students[j].num > students[j + 1].num) {
                    // 交换位置
                    struct Student temp = students[j];
                    students[j] = students[j + 1];
                    students[j + 1] = temp;
                }
            }
        }
    }
}

// 输出学生信息
void printStudentInfo(int index) {
    printf("学号\t姓名\t\t性别\t班级\t\t进制转换\t多进制转换\t数值表达逻辑代数\t平均成绩\n");
    printf("%d\t%s\t%s\t%s\t%.0f\t\t%.0f\t\t%.0f\t\t\t%.2f\n",
           students[index].num,
           students[index].name, students[index].gender, students[index].class,
           students[index].grade1, students[index].grade2, students[index].grade3,
           students[index].average_grade);
}

// 按照属性递归查询学生
int SearchRecursive(void* target, int left, int right, int (*cmp)(const struct Student*, const void*)) {
    /*
    target：指向目标信息的指针
    left：需要查询的区间左端点
    right：需要查询的区间右端点
    cmp：一个函数指针，指向比较函数
     */
    if (left > right) {
        return -1;
    }

    int mid = (left + right) / 2;
    if (cmp(students+mid, target) == 0) {  // 指针算术
        return mid;
    } else if (cmp(students+mid, target) < 0) {
        return SearchRecursive(target, mid + 1, right, cmp);
    } else {
        return SearchRecursive(target, left, mid - 1, cmp);
    }
}

// 比较函数：按学号
int cmpByNumber(const struct Student* s, const void* targetNum) {
    return s->num - *((int*)targetNum);
}

// 比较函数：按姓名
int cmpByName(const struct Student* s, const void* targetName) {
    return strcmp(s->name, (const char*)targetName);
}

// 比较函数：按平均成绩
int cmpByAverageGrade(const struct Student* s, const void* targetGrade) {
    if (s->average_grade < *((float*)targetGrade)) {
        return -1;
    } else if (s->average_grade > *((float*)targetGrade)) {
        return 1;
    } else {
        return 0;
    }
}

int SearchByName(char *targetName) {
    SortByName();
    int left = 0;
    int right = numStudents - 1;

    while (left <= right) {
        int mid = (left + right) / 2;
        int cmpResult = strcmp(students[mid].name, targetName);
        if (cmpResult == 0) {
            return mid;  // 找到目标姓名，返回下标
        } else if (cmpResult < 0) {
            left = mid + 1;  // 目标姓名在右半部分，缩小搜索范围
        } else {
            right = mid - 1;  // 目标姓名在左半部分，缩小搜索范围
        }
    }

    return -1;  // 没有找到目标姓名，返回 -1
}

// 选择查找方法
void SelectSearchRecursive() {
    int select;
    printf("请选择查询方式：1.学号\t2.姓名\t3.平均成绩\t");
    scanf("%d", &select);

    switch (select) {
        case 1: {
            int targetNum;
            printf("请输入要查询的学号：");
            scanf("%d", &targetNum);
            int index = SearchRecursive(&targetNum, 0, numStudents - 1, cmpByNumber);
            if (index != -1) {
                printStudentInfo(index);
            } else {
                printf("没有找到该学号对应的学生数据。\n");
            }
            break;
        }
        case 2: {
            char targetName[20];
            printf("请输入学生姓名：");
            scanf("%s", targetName);
            int index = SearchByName(targetName);
            if (index != -1) {
                printStudentInfo(index);
            } else {
                printf("没有找到该姓名对应的学生数据。\n");
            }
            break;
        }
        case 3: {
            float targetAverageGrade;
            printf("请输入平均成绩：");
            scanf("%f", &targetAverageGrade);
            int index = SearchRecursive(&targetAverageGrade, 0, numStudents - 1, cmpByAverageGrade);
            if (index != -1) {
                printStudentInfo(index);
                for (int found = 0; found < numStudents; ++found) {
                    if (students[found].average_grade == students[index].average_grade) {
                        printf("%d\t%s\t%s\t%s\t%.0f\t\t%.0f\t\t%.0f\t\t\t%.2f\n",
                               students[found].num,
                               students[found].name, students[found].gender, students[found].class,
                               students[found].grade1, students[found].grade2, students[found].grade3,
                               students[found].average_grade);
                    }
                }
            } else {
                printf("没有找到该平均成绩对应的学生数据。\n");
            }
            break;
        }
        default:
            printf("输入错误！");
    }

    int n;
    printf("是否继续查询？1.继续\t2.结束：");
    scanf("%d", &n);
    if (n == 1) {
        SelectSearchRecursive();
    }
}

int main() {
    ReadScore();
    SelectSearchRecursive();  // 开始查询
    return 0;
}

```

### 3.4 跳跃表

```c
#include <stdio.h>
#include <stdlib.h>
#include "string.h"

#define MAX_LEVEL 6 // 跳跃表的最大层数
#define MAX_NAME_LENGTH 50  // 学生姓名长度
#define MAX_GENDER_LENGTH 50  // 学生姓名长度
#define MAX_CLASS_LENGTH 50  // 学生姓名长度

typedef struct {
    int num;  // 学号
    char name[MAX_NAME_LENGTH];  // 姓名
    char gender[MAX_GENDER_LENGTH];  // 性别。
    char class[MAX_CLASS_LENGTH];  // 班级
    int grade1;
    int grade2;
    int grade3;
    int average_grade;
} Student;

// 跳跃表节点结构
typedef struct skipListNode {
    int key; // 键值
    Student *student;
    struct skipListNode **forward; // 指向前进节点的指针数组
} skipListNode;

// 跳跃表结构
typedef struct skipList {
    int level; // 当前跳跃表的最高层数
    struct skipListNode *header; // 跳跃表头节点指针
} skipList;


// 创建新节点
skipListNode *createNode(int key, int level, Student *student) {
    skipListNode *newNode = (skipListNode *) malloc(sizeof(skipListNode));
    if (newNode == NULL) {
        printf("内存分配失败！");

    }
    newNode->key = key;
    newNode->student = student;

    newNode->forward = (skipListNode **) malloc(sizeof(skipListNode *) * (level + 1)); // 根据跳跃表的随机层数动态分配指针数组空间
    return newNode;
}


// 创建跳跃表
skipList *createSkipList() {
    skipList *newSkipList = (skipList *) malloc(sizeof(skipList));
    newSkipList->level = 0;
    newSkipList->header = createNode(-1, MAX_LEVEL, NULL); // 头节点键值为 -1，用于辅助查找
    for (int i = 0; i <= MAX_LEVEL; i++) {
        newSkipList->header->forward[i] = NULL; // 初始时所有前进节点指针为空
    }
    return newSkipList;
}

// 生成随机层数
int randomLevel() {
    int level = 0;
    while (rand() < RAND_MAX / 2 && level < MAX_LEVEL) // 随机生成层数，保证层数不超过最大层数
        level++;
    return level;
}

// 插入节点到跳跃表中
void insert(skipList *list, int key, Student *student) {
    skipListNode *update[MAX_LEVEL + 1]; // 用于记录在每层中要插入新节点的前一个节点指针，本质是数组，只不过数组中存放的元素都是地址
    skipListNode *current = list->header; // 从头节点开始查找

    for (int i = list->level; i >= 0; i--) { // 从最高层开始向下查找
        while (current->forward[i] != NULL && current->forward[i]->key < key) { // 在当前层中找到最后一个键值小于要插入的键值的节点
            current = current->forward[i];
        }
        update[i] = current; // 记录当前层中要插入新节点的前一个节点指针
    }

    current = current->forward[0]; // 切换到第 0 层，即最底层的节点

    if (current == NULL || current->key != key) { // 如果找到的节点为空或者键值不等于要插入的键值
        int newLevel = randomLevel(); // 随机生成新节点的层数

        if (newLevel > list->level) { // 如果新节点的层数大于当前跳跃表的最高层数，需要更新最高层数
            for (int i = list->level + 1; i <= newLevel; i++) {
                update[i] = list->header; // 所有新层中的前一个节点指针都指向头节点
            }
            list->level = newLevel; // 更新跳跃表的最高层数
        }

        skipListNode *newNode = createNode(key, newLevel, student); // 创建新节点

        for (int i = 0; i <= newLevel; i++) { // 将新节点插入到每一层中
            newNode->forward[i] = update[i]->forward[i];
            update[i]->forward[i] = newNode;
        }
    }
}

// 在跳跃表中查找指定的键值
skipListNode *search(skipList *list, int key) {
    skipListNode *current = list->header;

    for (int i = list->level; i >= 0; i--) { // 从最高层开始向下查找
        while (current->forward[i] != NULL && current->forward[i]->key < key) { // 在当前层中找到最后一个键值小于要查找的键值的节点
            current = current->forward[i];
        }
    }

    current = current->forward[0]; // 切换到第 0 层，即最底层的节点

    if (current != NULL && current->key == key) { // 如果找到的节点不为空且键值等于要查找的键值
        return current; // 返回找到的节点指针
    } else {
        return NULL; // 否则返回空指针
    }
}

// 输出学生信息
void printStudentInfo(Student *student) {
    printf("学号\t\t姓名\t性别\t班级\t\t进制转换\t多进制转换\t数值表达逻辑代数\t平均成绩\n");
    printf("%d\t%s\t%s\t%s\t%d\t\t%d\t\t%d\t\t\t%d\n",
           student->num,
           student->name, student->gender, student->class,
           student->grade1, student->grade2, student->grade3,
           student->average_grade);
}

// 打印跳跃表
void printSkipList(skipList *list) {
    printf("跳跃表:\n");
    for (int i = list->level; i >= 0; i--) { // 从最高层开始向下打印
        skipListNode *current = list->header->forward[i];
        while (current != NULL) {
//            printf("%d ", current->key);
            printStudentInfo(current->student);
            current = current->forward[i];
        }
        printf("\n");
    }
}

// 按照学号读取数据
void ReadScoreByNum(skipList *list) {
    FILE *file;  // 文件指针

    // 打开原成绩文件
    file = fopen("score.txt", "r");
    if (file == NULL) {
        printf("无法打开文件: %s\n", "score.txt");
        exit(1);
    }

    // 将学生数据存入数组
    char line[500];
    while (fgets(line, sizeof(line), file) != NULL) {
        // 解析姓名和成绩
        Student *student = (Student *) malloc(sizeof(Student));
        int num;
        char name[MAX_NAME_LENGTH];
        char gender[10];
        char class[50];
        int grade1;
        int grade2;
        int grade3;
        sscanf(line, "%d %s %s %s %d %d %d",
               &num, name, gender, class, &grade1, &grade2, &grade3);
        student->num = num;
        strcpy(student->name, name);
        strcpy(student->gender, gender);
        strcpy(student->class, class);
        student->grade1 = grade1;
        student->grade2 = grade2;
        student->grade3 = grade3;
        student->average_grade = (grade1 + grade2 + grade3) / 3;
        insert(list, num, student);
    }
}

// 按照平均成绩读取数据
void ReadScoreByAverageGrade(skipList *list) {
    FILE *file;  // 文件指针

    // 打开原成绩文件
    file = fopen("score.txt", "r");
    if (file == NULL) {
        printf("无法打开文件: %s\n", "score.txt");
        exit(1);
    }

    // 将学生数据存入数组
    char line[500];
    while (fgets(line, sizeof(line), file) != NULL) {
        // 解析姓名和成绩
        Student *student = (Student *) malloc(sizeof(Student));
        int num;
        char name[MAX_NAME_LENGTH];
        char gender[10];
        char class[50];
        int grade1;
        int grade2;
        int grade3;
        sscanf(line, "%d %s %s %s %d %d %d",
               &num, name, gender, class, &grade1, &grade2, &grade3);
        student->num = num;
        strcpy(student->name, name);
        strcpy(student->gender, gender);
        strcpy(student->class, class);
        student->grade1 = grade1;
        student->grade2 = grade2;
        student->grade3 = grade3;
        student->average_grade = (grade1 + grade2 + grade3) / 3;
        insert(list, (grade1 + grade2 + grade3) / 3, student);
    }
}

void searchAndPrintByAverageGrade(skipList *list, int key) {
    skipListNode *current = list->header;

    for (int i = list->level; i >= 0; i--) { // 从最高层开始向下查找
        while (current->forward[i] != NULL && current->forward[i]->key < key) { // 在当前层中找到最后一个键值小于要查找的键值的节点
            current = current->forward[i];
        }
    }

    current = current->forward[0]; // 切换到第 0 层，即最底层的节点

    while (current != NULL && current->key == key) { // 如果找到的节点不为空且键值等于要查找的键值
        printStudentInfo(current->student);
        current = current->forward[0];
    }
}

skipListNode *searchByName(skipList *list, const char *name) {
    skipListNode *current = list->header;

    for (int i = list->level; i >= 0; i--) { // 从最高层开始向下查找
        while (current->forward[i] != NULL && strcmp(current->student->name, name) < 0) { // 在当前层中找到最后一个键值小于要查找的键值的节点
            current = current->forward[i];
        }
    }

    current = current->forward[0]; // 切换到第 0 层，即最底层的节点

    if (current != NULL && strcmp(current->student->name, name) == 0) { // 如果找到的节点不为空且键值等于要查找的键值
        return current;
    } else {
        return NULL;
    }
}

// 主函数
int main() {
    // 创建跳跃表
    skipList *list = createSkipList();
    while (1) {
        int select;
        printf("请选择查询方式:1.学号2.姓名3.平均成绩(退出请输入0)\n");
        scanf("%d", &select);
        if (select == 0) {
            exit(0);
        } else if (select == 1) {
            ReadScoreByNum(list);
            int key;
            printf("请输入要查询的学生学号");
            scanf("%d", &key);
            skipListNode *result = search(list, key);
            if (result != NULL) {
                printStudentInfo(result->student);
            } else {
                printf("未查询到相关学生信息\n");
            }
        } else if (select == 2) {
            char name[MAX_NAME_LENGTH];
            printf("请输入学生姓名");
            scanf("%s", name);
            skipListNode *result=searchByName(list, name);
            if (result != NULL) {
                printStudentInfo(result->student);
            } else {
                printf("未查询到相关学生信息\n");
            }
        } else if (select == 3) {
            ReadScoreByAverageGrade(list);
            int key;
            printf("请输入要查询的平均成绩");
            scanf("%d", &key);
            searchAndPrintByAverageGrade(list, key);
        } else {
            printf("输入错误\n");
        }
    }


}
```

# 第07课哈夫曼树

## 1. 二叉树，哈夫曼树

![image-20240212151404318](C:\Users\30694\AppData\Roaming\Typora\typora-user-images\image-20240212151404318.png)



![image-20240212151415747](C:\Users\30694\AppData\Roaming\Typora\typora-user-images\image-20240212151415747.png)

## 2. 构建哈夫曼树

哈夫曼树的节点个数为==**(2n-1)**==

![image-20240212151634882](C:\Users\30694\AppData\Roaming\Typora\typora-user-images\image-20240212151634882.png)

## 3. 示例

```c
#include <stdio.h>
#include <stdlib.h>
#include <limits.h> // 为了使用INT_MAX

// 定义哈夫曼树的节点结构
typedef struct {
    int weight; // 节点的权重
    int parent, lchild, rchild; // 父节点、左孩子、右孩子在数组中的索引
} HTNode, *HuffmanTree;

// 选择两个最小的节点
void select(HuffmanTree HT, int end, int *s1, int *s2) {
    int min1 = INT_MAX, min2 = INT_MAX;
    for (int i = 1; i <= end; ++i) {
        if (HT[i].parent == 0) { // 只考虑还没有父节点的节点
            if (HT[i].weight < min1) { // 找到比当前最小还小的节点
                min2 = min1;
                *s2 = *s1; // 更新第二最小的节点
                min1 = HT[i].weight;
                *s1 = i; // 更新最小的节点
            } else if (HT[i].weight < min2) { // 找到比第二小的还小，但比最小的大的节点
                min2 = HT[i].weight;
                *s2 = i;
            }
        }
    }
}

// 创建哈夫曼树
void CreateHuffmanTree(HuffmanTree *HT, int *w, int n) {
    if (n <= 1) return; // 如果只有一个或没有字符，则不进行操作
    int m = 2 * n - 1; // 计算总节点数
    *HT = (HTNode *) malloc((m + 1) * sizeof(HTNode)); // 分配空间，0号位置不用
    HuffmanTree ht = *HT;
    for (int i = 1; i <= n; ++i) { // 初始化叶子节点
        ht[i].weight = w[i - 1];
        ht[i].parent = ht[i].lchild = ht[i].rchild = 0;
    }
    for (int i = n + 1; i <= m; ++i) { // 初始化非叶子节点
        ht[i].weight = ht[i].parent = ht[i].lchild = ht[i].rchild = 0;
    }

    // 构建哈夫曼树
    for (int i = n + 1; i <= m; ++i) {
        int s1, s2;
        select(ht, i - 1, &s1, &s2); // 选择最小的两个节点
        ht[s1].parent = i;
        ht[s2].parent = i; // 设置选中节点的父节点
        ht[i].lchild = s1;
        ht[i].rchild = s2; // 设置新节点的子节点
        ht[i].weight = ht[s1].weight + ht[s2].weight; // 新节点的权重是两个子节点权重之和
    }
}

// 显示哈夫曼树数组
void DisplayHuffmanTree(HuffmanTree HT, int n) {
    int m = 2 * n - 1; // 总节点数
    printf("索引\t权重\t父结点\t左孩子\t右孩子\n");
    for (int i = 1; i <= m; ++i) { // 遍历打印每个节点
        // 注意：非叶子节点的字符可能不是有效字符
        printf("%d\t%d\t%d\t%d\t%d\n", i, HT[i].weight, HT[i].parent, HT[i].lchild,
               HT[i].rchild);
    }
}

int main() {
    int w[5];
    for (int i = 0; i < 5; ++i) {
        printf("请输入权重");
        scanf("%d", &w[i]);
    }
    int n = sizeof(w) / sizeof(w[0]); // 权重的数量
    HuffmanTree HT;

    CreateHuffmanTree(&HT, w, n); // 创建哈夫曼树
    DisplayHuffmanTree(HT, n); // 显示哈夫曼树

    free(HT); // 释放分配的内存
    return 0;
}

```

# 第08课哈夫曼编码

## 1.strcat函数：字符串连接

`strcat`函数是C语言中用来实现字符串连接的函数，其原型定义在`<string.h>`头文件中：

```c
char *strcat(char *dest, const char *src);
```

它的作用是将字符串`src`连接到字符串`dest`的末尾，并返回指向连接后的字符串`dest`的指针。使用`strcat`函数时需要注意确保目标字符串`dest`有足够的空间来容纳连接后的结果，否则可能导致内存溢出。

下面是一个简单的例子，演示了如何使用`strcat`函数将两个字符串连接起来：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20] = "Hello, ";
    const char *src = "world!";
    
    strcat(dest, src);
    printf("连接后的字符串: %s\n", dest);
    
    return 0;
}
```

在这个例子中，`strcat(dest, src)`将字符串`src`连接到`dest`的末尾，最终`dest`的内容变为"Hello, world!"。

需要注意的是，`strcat`函数会将`src`中的内容追加到`dest`之后，直到遇到`src`的结束符`\0`为止。因此，在使用`strcat`时要确保`dest`字符串已经以`\0`结尾，而且有足够的空间容纳`src`的内容。

## 2.isdight函数：判断字符串是否为数字

`isdigit()` 函数是一个用于判断字符是否为数字的函数。它是C语言和C++语言中的标准库函数，位于 `<ctype.h>` 头文件中。

函数原型如下：

```c
int isdigit(int c);
```

该函数接受一个整数参数 c（通常是一个字符），并返回一个非零值（true）表示该字符是一个数字字符（0-9），返回 0（false）则表示该字符不是一个数字字符。

以下是一个示例代码，演示如何使用 `isdigit()` 函数判断字符是否为数字：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = '7';

    if (isdigit(ch)) {
        printf("字符 %c 是一个数字\n", ch);
    } else {
        printf("字符 %c 不是一个数字\n", ch);
    }

    return 0;
}
```

输出：

```c
字符 7 是一个数字
```

## 3.strtok函数：分割字符串

`strtok` 函数是 C 标准库中的一个字符串处理函数，用于将一个字符串按照指定的分隔符进行分割。

函数原型如下：

```c
char *strtok(char *str, const char *delim);
```

其中 `str` 是要被分割的字符串，`delim` 是分隔符。`strtok` 函数通过返回一个指向被分割出来的子字符串的指针来逐个返回被分割后的子字符串，直到所有的子字符串都被返回完毕。

使用 `strtok` 函数时，第一次调用需要传入被分割的字符串 `str` 和分隔符 `delim`，之后每次调用只需要传入 `NULL` 作为第一个参数即可。例如：

```c
#include <string.h>
#include <stdio.h>

int main() {
    char str[] = "Hello, world! This is a test string.";
    char *token = strtok(str, " ,.!"); // 分割出第一个子字符串
    while (token != NULL) {
        printf("%s\n", token); // 输出当前分割出的子字符串
        token = strtok(NULL, " ,.!"); // 继续分割下一个子字符串
    }
    return 0;
}
```

在上面的例子中，`strtok` 函数会根据第二个参数 `" ,.!"` 来分割字符串 `str` 中的子字符串，每个子字符串都会被依次返回并输出，直到所有的子字符串都被返回完毕为止。

## 4.strtop函数：字符串复制

`strdup` 函数是 C 标准库中的一个字符串处理函数，用于创建一个新的字符串，并将给定字符串的内容复制到新创建的字符串中。

函数原型如下：

```c
char *strdup(const char *str);
```

其中 `str` 是要被复制的字符串。`strdup` 函数会分配足够的内存来存储给定字符串的副本，并返回指向新字符串的指针。如果内存分配失败，则返回 `NULL`。

使用 `strdup` 函数时，它会自动为新字符串分配足够的内存空间，并将原始字符串的内容复制到新字符串中。你可以像使用任何其他字符串一样使用这个新字符串。需要注意的是，使用完 `strdup` 返回的字符串后，应当使用 `free` 函数释放内存。

下面是一个示例：

```c
c复制代码解释#include <string.h>
#include <stdio.h>

int main() {
    const char *original = "Hello, world!";
    char *duplicate = strdup(original);

    if (duplicate != NULL) {
        printf("Original string: %s\n", original);
        printf("Duplicate string: %s\n", duplicate);

        // 使用 duplicate 字符串

        free(duplicate); // 释放内存
    } else {
        printf("Memory allocation failed.\n");
    }

    return 0;
}
```

在上面的例子中，`strdup` 函数会将字符串 `"Hello, world!"` 复制到 `duplicate` 字符串中，并输出原始字符串和复制字符串的内容。最后，使用 `free` 函数释放 `duplicate` 字符串所占用的内存。

## 5.fprintf函数：输出内容到文件

`fprintf` 函数是 C 标准库中的一个函数，用于将格式化的数据输出到指定的文件流中。它的用法类似于 `printf` 函数，但 `printf` 将输出内容到标准输出流（通常是显示器），而 `fprintf` 可以将输出内容发送到指定的文件流。

`fprintf` 函数的原型如下：

```c
int fprintf(FILE *stream, const char *format, ...);
```

其中 `stream` 是指向文件流的指针，`format` 是格式化字符串，`...` 表示可变数量的参数，用来填充格式化字符串中的格式化标记。

下面是一个示例，假设我们要将格式化的数据输出到一个文件中：

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w"); // 打开文件流
    if (file != NULL) {
        int num1 = 10;
        double num2 = 3.14;
        char str[] = "Hello, world!";
        
        fprintf(file, "Integer: %d, Double: %f, String: %s\n", num1, num2, str);

        fclose(file); // 关闭文件流
    } else {
        printf("Failed to open the file.\n");
    }

    return 0;
}
```

在上面的例子中，我们首先使用 `fopen` 函数打开文件流，并将输出重定向到 `output.txt` 文件中。然后使用 `fprintf` 函数将格式化的数据输出到文件中，最后使用 `fclose` 函数关闭文件流。

在执行完上述代码后，文件 `output.txt` 中将包含一行内容：

```c
Integer: 10, Double: 3.140000, String: Hello, world!
```

这就是 `fprintf` 函数的基本用法。

## 6. 位操作运算符

### 6.1 解释

- 按位与(&)：将两个操作数的对应位都设为1时，结果的对应位才为1，否则为0。
- 按位或(|)：将两个操作数的对应位只要有一个为1时，结果的对应位就为1，否则为0。
- 按位异或(^)：将两个操作数的对应位不相同时，结果的对应位为1，相同时为0。
- 按位取反(~)：对操作数的每个位取反，即0变为1，1变为0。
- 左移(<<)：将一个数的所有位向左移动指定的位数，右侧空出的位用0填充。
- 右移(>>)：将一个数的所有位向右移动指定的位数，左侧空出的位根据操作数的符号进行填充

### 6.2示例

- 按位与(&)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010
    unsigned int b = 12; // 二进制为 1100

    unsigned int result = a & b; // 二进制为 1000，十进制为 8

    printf("Result: %u\n", result);

    return 0;
}
```

- 按位或(|)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010
    unsigned int b = 12; // 二进制为 1100

    unsigned int result = a | b; // 二进制为 1110，十进制为 14

    printf("Result: %u\n", result);

    return 0;
}
```

- 按位异或(^)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010
    unsigned int b = 12; // 二进制为 1100

    unsigned int result = a ^ b; // 二进制为 0110，十进制为 6

    printf("Result: %u\n", result);

    return 0;
}
```

- 按位取反(~)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010

    unsigned int result = ~a; // 二进制为 0101，十进制为 5

    printf("Result: %u\n", result);

    return 0;
}
```

- 左移(<<)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010

    unsigned int result = a << 2; // 左移 2 位，二进制为 101000，十进制为 40

    printf("Result: %u\n", result);

    return 0;
}
```

- 右移(>>)示例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 10; // 二进制为 1010

    unsigned int result = a >> 2; // 右移 2 位，二进制为 10，十进制为 2

    printf("Result: %u\n", result);

    return 0;
}
```

## 7. unsigned char 与 char 的区别 

`unsigned char` 和 `char` 在 C 语言中是两种不同的数据类型。

1. `char` 类型：`char` 是一种字符类型，用于存储 ASCII 码字符，在内存中占用 1 个字节。它可以表示包括字母、数字和符号等在内的所有 ASCII 字符。
2. `unsigned char` 类型：`unsigned char` 是一种无符号字符类型，也用于存储 8 位的数据，在内存中同样占用 1 个字节。与 `char` 不同的是，`unsigned char` 存储的是非负整数值，范围从 0 到 255。

区别总结如下：

- char` 类型可以存储有符号整数和字符，而 `unsigned char` 只能存储非负整数。
- `char` 类型的范围是 -128 到 127，而 `unsigned char` 的范围是 0 到 255。
- 在使用 `char` 类型时，负数会被解释为对应的字符编码，而 `unsigned char` 则将负数作为正数处理。

需要注意的是，根据编译器和平台的不同，`char` 类型的默认有无符号属性可能会有所不同。因此，在使用这两种类型时，最好明确指定是使用有符号还是无符号。

在压缩文件时，通常会使用无符号字符类型 `unsigned char`。因为在压缩文件时，需要对原始数据进行编码和解码操作，并将其转换为比特流，而比特流仅包含 0 和 1 两种状态，因此无符号整数类型 `unsigned char` 的范围正好满足这个需求。同时，由于 `unsigned char` 只能存储非负整数，因此可以保证压缩后的数据不会出现负数，避免了数据解码时的错误。

此外，无符号字符类型 `unsigned char` 占用的内存空间比有符号字符类型 `char` 更小，通常只占用一个字节，可以更有效地利用内存资源。在压缩大文件时，这显得尤为重要，因为需要处理大量的数据，而内存资源又是有限的。

综上所述，无符号字符类型 `unsigned char` 在压缩文件时具有更好的适用性和效率。

## 8. fwrite函数

`fwrite` 函数是 C 语言标准库中用于将数据块写入文件的函数。其原型通常如下所示：

```c
size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream);
```

- `ptr`：指向要写入数据的指针。
- `size`：要写入每个数据项的字节数。
- `nmemb`：要写入的数据项的数量。
- `stream`：指向要写入的文件的流。

`fwrite` 函数将 `nmemb` 个数据项，每个数据项的大小为 `size` 字节，从指针 `ptr` 指向的内存区域写入到 `stream` 指向的文件中。函数返回实际写入的数据项数量，如果返回值与 `nmemb` 不相等，可能意味着写入失败或出现错误。

这个函数通常用于将数据块写入二进制文件，例如在文件压缩、图像处理、网络传输等场景中经常会用到。在使用 `fwrite` 函数时，需要注意确保文件以二进制模式打开，并且要正确处理函数返回值以及可能出现的错误情况。

## 9.strncpy函数

strcspn函数是C语言中的一个字符串处理函数，它用于计算字符串中第一个不包含指定字符集合中任何字符的位置。

函数原型如下：

```c
size_t strcspn(const char *str1, const char *str2);
```

参数说明：

- str1：要搜索的字符串。
- str2：包含要搜索的字符集合的字符串。

函数返回值为一个 size_t 类型的整数，表示在 str1 中第一个不包含 str2 中任何字符的位置索引。

示例用法：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello World";
    const char *str2 = "aeiou";

    size_t result = strcspn(str1, str2);

    printf("第一个不包含 %s 中的字符的位置是：%zu\n", str2, result);

    return 0;
}
```

输出结果：

```c
第一个不包含 aeiou 中的字符的位置是：1
```

在上述示例中，str1 是要搜索的字符串，str2 是字符集合。函数 strcspn 将从 str1 的首字符开始搜索，并返回第一个不包含 str2 中任何字符的位置索引。在这个例子里，str1 中第一个不包含 "aeiou" 中任何字符的位置是索引 1，即字符 'e'。

