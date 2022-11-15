# C++ Primer 读书笔记

## 0、说明

个人QQ: **1048092863** ；微信: **lgz031130**      

 [博客](http://47.108.53.149/)       [B站空间](https://space.bilibili.com/618240282)

***c++primer 第一次阅读笔记***

## 1、第一章

## 2、第二章  变量和基本类型

### 2.1 基本内置类型

#### 2.1.0 基本内置类型

#### 2.1.1 算术类型

| **`int`**           | 4 个字节 | 整数值的默认选择。                                           |
| ------------------- | -------- | ------------------------------------------------------------ |
| **`double`**        | 8 字节   | 浮点值的默认选择。                                           |
| **`bool`**          | 1 个字节 | 表示可为 true 或 false 的值。                                |
| **`char`**          | 1 个字节 | 用于早期 C 样式字符串或 std:: 字符串对象中无需转换为 UNICODE 的 ASCII 字符。 |
| **`wchar_t`**       | 2 个字节 | 表示可能以 UNICODE 格式进行编码的“宽”字符值（Windows 上为 UTF-16，其他操作系统上可能不同）。 **`wchar_t`** 是在 类型字符串中使用的字符类型 `std::wstring`。 |
| **`unsigned char`** | 1 个字节 | C++ 没有内置字节类型。 使用 **`unsigned char`** 来表示字节值。 |
| **`unsigned int`**  | 4 个字节 | 位标志的默认选项。                                           |
| **`long long`**     | 8 字节   | 表示更大的整数值范围。                                       |

| ASCII值 | 控制字符 | ASCII值 | 控制字符 | ASCII值 | 控制字符 | ASCII值 | 控制字符 |
| :------ | :------- | :------ | :------- | :------ | :------- | :------ | :------: |
| 0       | NUT      | 32      | (space)  | 64      | @        | 96      |    、    |
| 1       | SOH      | 33      | !        | 65      | A        | 97      |    a     |
| 2       | STX      | 34      | "        | 66      | B        | 98      |    b     |
| 3       | ETX      | 35      | #        | 67      | C        | 99      |    c     |
| 4       | EOT      | 36      | $        | 68      | D        | 100     |    d     |
| 5       | ENQ      | 37      | %        | 69      | E        | 101     |    e     |
| 6       | ACK      | 38      | &        | 70      | F        | 102     |    f     |
| 7       | BEL      | 39      | ,        | 71      | G        | 103     |    g     |
| 8       | BS       | 40      | (        | 72      | H        | 104     |    h     |
| 9       | HT       | 41      | )        | 73      | I        | 105     |    i     |
| 10      | LF       | 42      | *        | 74      | J        | 106     |    j     |
| 11      | VT       | 43      | +        | 75      | K        | 107     |    k     |
| 12      | FF       | 44      | ,        | 76      | L        | 108     |    l     |
| 13      | CR       | 45      | -        | 77      | M        | 109     |    m     |
| 14      | SO       | 46      | .        | 78      | N        | 110     |    n     |
| 15      | SI       | 47      | /        | 79      | O        | 111     |    o     |
| 16      | DLE      | 48      | 0        | 80      | P        | 112     |    p     |
| 17      | DCI      | 49      | 1        | 81      | Q        | 113     |    q     |
| 18      | DC2      | 50      | 2        | 82      | R        | 114     |    r     |
| 19      | DC3      | 51      | 3        | 83      | S        | 115     |    s     |
| 20      | DC4      | 52      | 4        | 84      | T        | 116     |    t     |
| 21      | NAK      | 53      | 5        | 85      | U        | 117     |    u     |
| 22      | SYN      | 54      | 6        | 86      | V        | 118     |    v     |
| 23      | TB       | 55      | 7        | 87      | W        | 119     |    w     |
| 24      | CAN      | 56      | 8        | 88      | X        | 120     |    x     |
| 25      | EM       | 57      | 9        | 89      | Y        | 121     |    y     |
| 26      | SUB      | 58      | :        | 90      | Z        | 122     |    z     |
| 27      | ESC      | 59      | ;        | 91      | [        | 123     |    {     |
| 28      | FS       | 60      | <        | 92      | \        | 124     |    \|    |
| 29      | GS       | 61      | =        | 93      | ]        | 125     |    }     |
| 30      | RS       | 62      | >        | 94      | ^        | 126     |    `     |
| 31      | US       | 63      | ?        | 95      | _        | 127     |   DEL    |

**运算符优先级**

| Precedence           | Operator                                         | Description                                             | Associativity |
| :------------------- | :----------------------------------------------- | :------------------------------------------------------ | :------------ |
| 1                    | `::`                                             | Scope resolution                                        | Left-to-right |
| 2                    | `++`  `--`                                       | Suffix/postfix increment and decrement                  |               |
| `()`                 | Function call                                    |                                                         |               |
| `[]`                 | Array subscripting                               |                                                         |               |
| `.`                  | Element selection by reference                   |                                                         |               |
| `−>`                 | Element selection through pointer                |                                                         |               |
| 3                    | `++`  `--`                                       | Prefix increment and decrement                          | Right-to-left |
| `+`  `−`             | Unary plus and minus                             |                                                         |               |
| `!`  `~`             | Logical NOT and bitwise NOT                      |                                                         |               |
| `(*type*)`           | Type cast                                        |                                                         |               |
| `*`                  | Indirection (dereference)                        |                                                         |               |
| `&`                  | Address-of                                       |                                                         |               |
| `sizeof`             | Size-of                                          |                                                         |               |
| `new`, `new[]`       | Dynamic memory allocation                        |                                                         |               |
| `delete`, `delete[]` | Dynamic memory deallocation                      |                                                         |               |
| 4                    | `.*`  `->*`                                      | Pointer to member                                       | Left-to-right |
| 5                    | `*`  `/`  `%`                                    | Multiplication, division, and remainder                 |               |
| 6                    | `+`  `−`                                         | Addition and subtraction                                |               |
| 7                    | `<<`  `>>`                                       | Bitwise left shift and right shift                      |               |
| 8                    | `<`  `<=`                                        | For relational operators < and ≤ respectively           |               |
| `>`  `>=`            | For relational operators > and ≥ respectively    |                                                         |               |
| 9                    | `==`  `!=`                                       | For relational = and ≠ respectively                     |               |
| 10                   | `&`                                              | Bitwise AND                                             |               |
| 11                   | `^`                                              | Bitwise XOR (exclusive or)                              |               |
| 12                   | `|`                                              | Bitwise OR (inclusive or)                               |               |
| 13                   | `&&`                                             | Logical AND                                             |               |
| 14                   | `||`                                             | Logical OR                                              |               |
| 15                   | `?:`                                             | Ternary conditional                                     | Right-to-Left |
| 16                   | `=`                                              | Direct assignment (provided by default for C++ classes) |               |
| `+=`  `−=`           | Assignment by sum and difference                 |                                                         |               |
| `*=`  `/=`  `%=`     | Assignment by product, quotient, and remainder   |                                                         |               |
| `<<=`  `>>=`         | Assignment by bitwise left shift and right shift |                                                         |               |
| `&=`  `^=`  `|=`     | Assignment by bitwise AND, XOR, and OR           |                                                         |               |
| 17                   | `throw`                                          | Throw operator (for exceptions)                         |               |
| 18                   | `,`                                              | Comma                                                   |               |

| 序列 | 意义              |
| :--- | :---------------- |
| \b   | 一个退格符        |
| \n   | 新行              |
| \r   | 回车              |
| \t   | Tab               |
| \Z   | CTRL+Z (ASCII 26) |
| \”   | 一个双引号字符    |
| \\   | 一个反斜杠字符    |
| \0   | 一个 ASCII 空字符 |

#### 2.1.2 类型转换

类型转换超过取值范围时,会从左端开始重新运算

### 2.2 变量

#### 2.2.0 变量

变量提供一个具名,特工程序操作的存储空间;

#### 2.2.1 变量定义

语法为: type name;    初始化 : name = 值;

可以在定义时初始化 type name = 值;

初始化方式有多种,例如

```c++
int i = 5 ;
int s = { 5};
int t {5};
int x (5);   //四种初始化方式均正确
```

使用{}进行**列表初始化**时,如果遇到精度丢失,会报错,而不是警告

#### 2.2.2 变量声明和定义的关系

变量只能被定义一次,但是可以进行多次声明,使用extern 进行文件内声明

#### 2.2.3 标识符

pass

#### 2.2.4 名字的作用域

示例:

```c++
#include<iostream>
using namespace std;
int i=5;
int main()
{
    int i =4;
    cout<<i<<endl; //此时 main函数体内的i 为局部变量,会覆盖掉函数体外的全局变量i  ,因此值为4
    cout<<::i<<endl; //此时在i 前加:: 说明调用的是全局变量i ,此时值为5
}
```

### 2.3 复合类型

#### 2.3.0 复合类型

**复合类型**： 基于其他类型定义的新类型。

简单的复合类型: 引用和指针 。

#### 2.3.1 引用

**引用** 的实义为起别名，代码为: type & another_name = name，引用必须在定义时进行初始化，例如

```c++
int i=5;
int &x=i; //将x与i绑定， x为i的别名。
int &s; //错误，引用的实质为*const 因此必须初始化
```

无法定义引用的引用，引用本身并非对象，定义引用的引用即两个引用绑定到同一个原始变量身上。

除了2.4.1中指向常量的引用和15.2.3外，引用不允许发生基础的类型转换，与指针相同，也不允许指向整形字符，例如

```C++
int &a=10;//错误，不可引用整形字符
int i=5;
double &s=i ;// 错误，不可发生类型转换
```

##### 练习2.15

```c++
(a)不合法，但是会发生强制的类型转换
(b)不合法，不可以定义指向整型字符的引用
(c)合法
(d)不合法，引用必须初始化
```

##### 练习2.16

```C++
均合法，只是有些发生和强制类型转换精度丢失
```

##### 练习2.17

```c++
i与ri均为10
```

#### 2.3.2 指针

**指针** 的定义 type *name;

指针的值为一个地址，即指针指向一个地址，且指针本身就是一个对象，可以赋值和运算拷贝，且普通指针无需在定义时初始化。

指针存放一个地址，因此用&来赋值指针，例如

```c++
int i=5;
int *p=&i; //&i为i的地址，指针接收的值，i即为指针的指向
//因为引用不是对象，没有实际地址，因此不能定义指向引用的指针
```

除了2.4.2和15.2.3中情况，指针需要有严格的类型匹配，例如

```c++
int i=5;
double *p=&i ;//错误，类型不匹配
```

使用指针访问对象,如果指针指向了一个带有确定值的对象,可以通过*来解引用来获取值,例如:

```c++
int i=5;
int *p=&i;
cout<<*p<<endl;  //此时*p即为i的值5
*p=4;// 将*p复制为4,i的值即为4
cout<<*p<<endl;  //此时*p的值为4
```

定义一个指针,可以先使他指向空,在c++11中,使用nullptr来代表空,例如:

```c++
int *ptr = nullptr; //说明ptr指向了空 
int zero=0;
int *p=zero; //错误,即使zero为0.也不可直接把变量赋值给指针
```

指针与引用的区别: 引用本身并非一个对象,而指针是一个实体对象,可以赋值以及算数运算,引用一旦实现无法改变引用,但是非常量指针可以改变指针的指向,即指针接收到的地址,例如:

```c++
int i=2,b=3;
int &ia=i;
int &ia=b; //错误,引用ia已经绑定到了i,无法再改变绑定对象
int *ptr=&i;
ptr=&b ;//正确,可以改变指针的指向
int *ptr_1=nullptr;
ptr_1=ptr; //正确 ,可以把ptr赋值给ptr_1,此时ptr_1也指向了b;
```

**Void* 指 针**

  **void***可以存放任意类型的指针,但是无法直接操作所指的对象

##### 练习2.18-2.24

```c++
pass
```

#### 2.3.3 理解复合类型的声明

连续定义时,常产生误导,例如

```c++
int *p,i=5; //连续定义,第一个定义为 int *p;定义了一个未初始化的指针,第二个定义为int i=5 ;定义了一个整型变量而不是指针
int *p1,p2;// p1为指针,p2为int 变量
```

**指向指针的指针**

可以通过*的个数来判断定义的类型,*       *代表指针   **代表指向指针的指针,例如

```c++
int i=4;
int *p=&i; //定义了一个指针p
int* *p2 =&p ; //定义了一个指向指针的的指针 此时分组应该为int* *p = =&p ;说明指针*p指向的是一个int*类型,即指向指针
//上述理论可以分辨,实际p2为int **类型 ;
```

##### 练习2.25

```c++
(a)ip是个int指针,r是个int 类型的引用;
(b)i是一个int 类型的变量,ip是一个int 指针变量
(c)ip2是int变量
```

### **2.4 const限定符**

#### 2.4.0 const限定符

const: const typename 变量名 = 值;

const使用时一定要初始化，例如

```c++
const int i = 5; //正确
const int x;
x=5;  //错误 必须定义的同时初始化
```

const 可以被调用 但是不可以被修改

```c++
const int ci=5;
int i=ci; //正确 const用来定义 i 但是对ci本身并未任何修改，正确
ci=2; //const无法修改
```

const只在单文件中生效，要在全文件夹中使用，需要使用extern进行声明，一般来说，const常在函数实现cpp里进行定义，如fun.cpp

注意，定义中也需要使用extern进行声明，说明其他文件夹也可以使用此常量。

```c++
extern const int weekly = 7; //在cpp源文件中进行了定义
```

要想在其他文件使用weekly，需要进行声明后使用，一般声明统一放到.h头文件中，其他cpp源文件只需要包含此头文件即可使用const字符，此特性与函数类似，例如

```c++
extern const int weekly;  //单声明，不可再赋值，如果再赋值则两文件中均含有weekly且含义不同。
```

##### 练习2.26

```c++
(a)const 只定义未初始化赋值，错误，必须同时进行
(b)正确
(c)正确，用一个值来初始化const常量;
(d)错误，cnt为非常量，可以进行++操作，但sz为常量，不可++
```

#### 2.4.1 const的引用

可以定义一个const类型的引用，来引用const常量，但是不可以使用非常量引用来引用const常量，例如:

```C++
const int r=1;
const int &a=r; //正确，不可通过a 来修改r的值，双方均为引用，合理
int &b=r;  //错误，b为非const引用，则可以修改b的值，但是显然r为const常量无法修改，矛盾显然成立，编译器报错
```

对const的引用，一般称为 **常量引用**

const引用可以用来给其他变量赋初值，只要自身不发生改变即可。

```c++
double dval = 3.14
const int &a = dval;
//此代码发生了一个隐藏的类型转换，但并非dval进行类型转换变为了int dval =3，而是系统引出了一个默认的temp值
const int temp = dval;
const int &a = temp;
//系统创建了一个临时变量，因此a和dval关系不大，且const也无法修改。
```

对const的引用可以使用一个非常量来进行初始化引用，例如

```C++
int i = 5;
const int &a = i;
//这是显然正确的，你无法通过a 来修改i的值，但是可以通过 i来修改a。
//a仍然为const常量，但是i 还仅仅只是一个int 变量，并不会也变为const常量.
```

#### 2.4.2 指针和const

**指向常量的指针**不能通过指针来修改对应的值，同时，想要指向一个const常量，指针也必须使用const修饰，但是与引用类似，一个const类型的指针可以指向非常量类型，这也不会改变被指向变量的类型，例如：

```c++
const int i =5;
int *ptr=&i ; //显然错误，const为常量，如果可以则会导致可以通过ptr来改变i的值，错误
const int *ptr_1=& i; //正确,const 指向 const  且不能解引用赋值
int x=4;
const int *ptr_2=x; //正确，无法通过ptr_2指针修改x,但可以通过其他方式修改x,x仍为int 变量
```

**常量指针** 是指对指针本身进行const修饰，使指针无法改变指向，与引用的本质类似，绑定到了初次指向对象的身上，实际含义为，const修饰指针本身，指针确定指向即为对指针赋初值——地址，指针的值（地址）无法修改，则指向无法修改。例如

```c++
int i=5;
int *const ptr=i; //正确 此时ptr本身是一个常量即ptr的值&i 例如0X00001010 无法改变，指针将一直指向这个地址，即一直指向i
*ptr=0;//正确，ptr的指向没有改变，而是对指向的值进行修改，本身地址不变，此时仍指向i，且i的值为0。
const int *const ptr_1=i; //正确，指向常量的常量指针，无法修改ptr_1的值和指向。
// const int 中const 说明指向常量。 *const 中const 说明是一个常量指针。
```

##### 练习2.27

```C++
(a)int &r=0 //错误，指向一块未知的地址，修改为const int &r=0即为正确，无法改变才可以实现
(b)正确 常量指针可以指向非const常量
(c)正确，要想引用整形字符必须使用const 限定
(d)正确 指向常量的常量指针
(e)正确 指向常量的指针可以指向非const常量，只是无法修改指针的值来修改变量
(f)常量指针必须初始化 错误
(g)正确
```

##### 练习2.28

```C++
(c)const 常量必须定义时进行初始化 非法
(d)常量指针必须定义时确定指向 非法
(e)正确 指向常量的指针可以不进行初始化，后确定指向可以。
```

##### 练习2.29

```C++
pass 
```

#### 2.4.3 顶层const

**指针本身是常量         **   * const          **指针指向常量**       const int *ptr

用名词 ***顶层const*** 指指针本身是个常量    用名词 ***底层const*** 表示指针的指向是个常量

更一般的，顶层const 可以指代更多，如算数类型 ，类，指针等,比如

```c++
const int i = 5; //为顶层const,与指针和引用并不一致
int *const p= &i ;//为顶层const ,顶层const的实义便是指定义的对象本身是常量
const int *ptr;//为底层const 指指向的值是一个Const常量
const int &r=i;//与指针一致，为底层const 引用的值 是一个const常量
```

##### 练习2.30

```C++
顶层
底层
顶层和底层
```

##### 练习2.31

```c++
pass
```

#### 2.4.4 constexpr和常量表达式

***常量表达式*** 指值不会改变且在编译过程中得到结果

const初始化赋值操作本身就是一个常量表达式

```c++
const int i-5;
const int s=i+5;  //1,2均为常量表达式,因为在编译中得到了结果
const int t=get_size();//非常量表达式 因为要在运行get_size()函数才可以获得值
```

***constexpr*** 声明

使用constexpr声明来验证是否是一个常量表达式, 赋值中一定为常量表达式，例如

```c++
constexpr int i=5 ;//赋值操作，显然为一个常量表达式
constexpr int x=size(); //如果siez函数也是一个constexpr 声明类型，即在编译阶段调用，则为常量表达式，否则不然
```

*(关于constexpr函数 见 6.5.2)*

在定义指针中，如果使用constexpr声明，则仅仅对指针本身生效，对所指向的值无作用，例如

```C++
int i =5;
constexpr int *ptr = & i ;//ptr是常量指针，指向不可修改
const int *ptr_1=5;// ptr_1 是指向常量的指针，值不可修改
```

##### 练习2.32

```C++
错误 null为值，指针应指向地址 改为int *p =& null;
```

### 2.5 处理类型

#### 2.5.0 处理类型

#### 2.5.1 类型别名

**typedef** 给一个类型起别名,例如int double 或者自己定义的类名,语法为: typedef 原类名 别名, 例如:

```c++
typedef int zx; //zx是int型的别名
int i=4;
zx i=4 ; //效果相同,都是int 类型
zx *ptr= &i;//定义了一个int类型的指针指向i
```

 新标准中 一种新的定义方式 语法为: using 别名 = 类名, 例如:

```c++
using zx = int ;//与typedef int zx;效果相同
```

#### 2.5.2 auto类型说明符号

当把表达式赋值给一个变量时,有时系统定义的表达式的返回类型未知,因此引入了 **auto** 类型说明符 , 自动判断变量的类型,因此,auto 定义的变量与const变量相同, 必须在定义时同时进行初始化,auto才起作用,例如:

```c++
auto i = size();//正确,程序根据size函数返回的类型自动给i一个相同的类型
auto x; x =5;//错误,必须定义时初始化 
```

同时,在使用auto进行连续定义时,即使可以自动判断类型,但连续定义变量类型需相同,例如:

```c++
auto i=5,b=1.2;//错误,i 和 b 的类型不相同
auto i=4, x=5; //正确, i 与 x 均为int 型
```

**复合类型 常量和auto**

  当auto 判断引用时,通常根据引用绑定的对象来进行判断

​    auto 一般会忽略顶层const,但是会保留底层const,例如:

```c++
const int i=3,&x=i;
int i1=5;
auto a=i; //auto 会忽略掉 i 前的顶层const 因此a是一个变量而非const常量,可以额外添加const
const auto a= i ;//此时 a 为一个const 常量,不可以修改a 
auto b=&i;// b是一个指向常量的指针,其中 &自带的顶层const 被忽略,因此可以改变 b的指向,但是 底层 const auto 继承
//b 是一个指向常量的指针,指针的值不可以改变,指针的指向可以改变
auto c=&i1; //&自带的顶层const 忽略 ,为一个普通的int 型指针
```

符号*和&只是属于一个声明符，而并非属于一个基本的数据类型，例如:

```c++
auto t=2, &i=t; //正确 t为 int类型 , i为 int&类型 即Int类型的引用
const int i =3;
auto &k = i ，*p=&t;//正确 k是一个const int&的引用， 即常量整型引用，p为指向t的const int型指针
auto &m=t,*ptr_1=i;//错误，t为int类型，则m为int类型的引用auto为int i为const常量 ptr为指向常量的指针为const int
```

##### 练习2.33

```c++
pass
```

##### 练习2.34

```c++
pass
```

##### 练习2.35

```c++
i 为 const int类型， k为 const int类型的引用 , p为指向常量的指针
const auto j2=i; 原本g2的顶层Const被忽略 ,自行加上const 则j2为const int类型 常量 k2为const int类型的引用
```

#### 2.5.3 decltype 类型指示符

  decltype 调用函数，接收函数的返回值类型，而不接收函数的返回值，语法 decltype(函数()) name = 值 ; 例如:

```c++
decltype(fun()) i = 5; //i的值类型即为函数fun return值类型，但没有调用fun()返回的值
```

同时，decltype处理顶层const和引用的方式与auto 不同，decltype会接收Const并且读取引用符号，例如:

```c++
int i = 4, &s= i ;
const int j=4 ; 
auto x=s; //使用auto 时，利用s给x赋值,auto 自动读取到s引用的对象i的类型，即利用s为过程链接到i上。
auto y=j;// 使用auto 右侧为const常量时，会忽略顶层const常量，因此y是一个普通的int变量
decltype(s) x = 5; // 使用decltype获得类型，不会跳过引用，而是视作一种类型，因此x的类型为int &，语句错误
decltype(s) x = i; // int &类型，x要用一个变量进行初始化绑定
decltype(j) y = 4 ; // decltype不会忽视const 因此y为const int类型
```

引用一直都是作为绑定对象的同义词，只有在decltype处有特殊含义

***decltype和引用***

decltype使用的表达式不是变量，而是一个运算式的时候，返回运算式类型，例如:

```c++
int i = 4 , *p=&i , &r = i ;
decltype(i) x = 5 ; //x为int类型
decltype(r) x = i ; //x为int&类型，必须有一个变量来初始化
decltype(r+0) x= 4; //r+0返回类型为int,因此 x 为int 类型
decltype (*p) x = i; //p是一个指针，*p对指针解引用得到一个对象，因此decltype一个指针时，返回一个int&,需要一个变量初始化
```

上述234较为好理解，**关于5，解指针得到一个对象，并且可以给对象赋值，因此decltype一个指针时，得到的是int&类型而非int类型**

对于decltype，如果变量名加上了括号，则一定返回一个引用类型，例如：

```c++
int i=5;
decltype (i) x =3 ; //x 为 int类型
decltype ( (i) ) x = i ; //decltype返回一个int&类型，必须需要一个变量初始化
```

赋值会产生引用，例如i=x,如果i是int ,则i=x的表达式的类型为int &,因此：

```c++
int a=3 ,b=4;
decltype(a=b) x= a; //a=b返回一个a的引用类型，即int& 则需要一个变量进行初始化
```

##### 练习2.36

```c++
a int类型， b int类型, c int类型, d int&类型，绑定a
a=3,b=5,c=4,d=5
```

##### 练习2.37-2.38

```c++
pass
```

### 2.6 自定义数据结构

#### 2.6.0 自定义数据结构

在本小节我们将学习定义自己的简单类，**struct**结构体

#### 2.6.1 定义一个结构体

语法为: struct name {   type name; type name2}; 例如:

```c++
struct people 
{
  string name;
  int age;
  string address;
};
people a,b; //定义了people类下的两个变量a,b
```

上述代码定义了一个结构体类 people ,一般来说，不在结构体后进行变量定义，而用分号隔开重新使用结构体进行定义变量。

类内的数据成员比如name,age等，如果不进行显式初始化则进行默认初始化，字符型变量都被初始化为0，字符串初始化为空

#### 2.6.2 使用struct 结构体

在2.6.1中定义了people结构体，即类似于int类，使用people类必须进行实例化，我们已经这样做了

```c++
people a,b //定义了两个people 类a ,b
```

同时，我们还可以进行数据的读入和读取，访问结构体内部的变量，使用 **.** (成员运算符)进行，例如:

```c++
cin>>a.name>>a.age;//a是一个people 类下的对象,a.name是一个string变量
//同时，你也可以通过成员运算符访问这些变量，例如
cout<<a.name; //输出a的姓名
```

#### 2.6.3 编写自己的头文件

有关分文件编写，首先我们要搞清楚头文件.h和源文件.cpp中分别应该放什么:

借鉴[博客园](https://www.cnblogs.com/fenghuan/p/4794514.html)和[菜鸟](https://www.runoob.com/w3cnote/cpp-header.html)中的说明，总的来说，头文件中可以放变量和函数的声明，而不要定义，但是有三个例外：

**一，头文件中可以写 const 对象的定义。**

**二，头文件中可以写内联函数（inline）的定义。**

**三，头文件中可以写类（class）的定义。**值得一提的是，类的定义中包含着数据成员和函数成员。数据成员是要等到具体的对象被创建时才会被定义（分配空间），但函数成员却是需要在一开始就被定义的，这也就是我们通常所说的类的实现。一般，我们的做法是，把类的定义放在头文件中，而把成员函数的实现代码放在一个 .cpp 文件中。

总上所述: .h文件中能包含：

- 类成员数据的声明，但不能赋值

- 类静态数据成员的定义和赋值，但不建议，只是个声明就好。

- 类的成员函数的声明,成员函数的定义一般习惯放在一个单独的cpp源文件中

- 非类成员函数的声明,一般与类成员函数的定义放到一起，如果存在的话。

- 常数的定义：如：const int a=5;

- 静态函数的定义

- 类的内联函数的定义

  ​             不能包含：

  1、 所有非静态变量（不是类的数据成员）的声明

  2、 默认命名空间声明不要放在头文件，using namespace std;等应放在.cpp中，在 .h 文件中使用 std::string

例如: 在people.h头文件中

```c++
// .h头文件中
struct people
{
  string name;
  void getname();
};
```

在people.cpp源文件中

```c++
#include "people.h"
std::cout;
void people::getname()
{
    cout<<this->name;
}
```

在main.cpp主体源文件中

```c++
#include<iostream>
#include "people.h"
using namespace std;
int main()
{
    people a;
    cin>>a.name;
    a.getname(); //输出a.name
}
```

## 3、第三章

### 3.1 命名空间的using声明

可以使用using对命名空间中进行声明，例如:

```c++
using namespace std; //使用全局命名空间std,一般不常用
using std::cin;using std::cout;//对cin,cout使用命名空间std,常用
std::cout<<"hello world"<<std::endl; //可以对每次出现进行std::作用域声明，一般在头文件中使用
```

**一般来说，头文件不使用using声明，而是对每个cin,cout等进行std作用域声明**

### 3.2 标准库类型string

#### 3.2.0 标准库类型string

要使用string类，要包含string头文件，且string类属于std命名空间中，因此常：

```c++
#include<string>  //使用string类下的函数时一定要包含string头文件
using std::string
```

#### 3.2.1 定义和初始化string对象

定义一个string 对象 语法： string name;初始化方式有多种:

```c++
string x； //定义一个string对象，默认初始化为空字符串
string x="hello world"; //定义并初始化了一个字符串x,其值为字符串"hello world"
string s=x; //定义了一个string类下的s ,并用x初始化了s,此时s的值也为"hello world "
string s(x); //与3相同，定义一个s并把x赋值给s
string s("hello world") //与2相同，定义并用"hello world "初始化了s
string x(n,'c') ; //将字符c循环n次后赋值给x,如x(10,'c')。则x="cccccccccc"
```

**拷贝初始化和直接初始化**

拷贝初始化是利用等号=进行初始化，如上述的23即为拷贝初始化，直接初始化是利用括号进行初始化，如上述的5

#### 3.2.2 string对象上的操作

**读写string对象**

同其他基本类型一样，可以使用cin,cout进行读写string类，并且可以连续读写，但是使用cin读入字符串时，string对象会自动忽略开头的空白，从第一个真正有意义的字符开始读取，并且一直到空白停止，例如

```c++
string x,y;
cin>>x>>Y; //如果输入"hello world ",则x被赋值为“hello”,y被赋值为“world” ,因为cin读取遇到空格就会停止
cout<<X<<Y; //此时cout结果为helloworld
```

**读取未知数量的string对象**

可以通过while循环持续的读取字符串直到遇到文件尾截止，例如:

```c++
string x;
while(cin>>x)
{
    cout<<x<<endl;
}  //当你输入"hello world"时，第一行会输出hello，然后进行endl换行，第二行会输出world,因为while遇到空白或者换行符即结束
```

检测读取是否有效，正常Cin,则返回true进行再读取

**使用getline读取一整行**

因为使用cin会忽视空白，因此如果想要读取空格，则必须读取一整行，需要使用getline运算符，getline运算符的参数一个是输入流，一个是string对象，语法为: getline(is,string),注意，想要使用getline()函数，必须包含string.h，例如

```c++
string x;
getline(cin,x); //读取一整行
```

注意，getline遇到换行符停止，并且读取换行符，然后输入流输入到string变量中的时候，会丢弃换行符，因此getline一遇到换行符便返回结果，且丢弃换行符，如果一开始便输入一个换行符，则string对象为空,可以使用getline进行循环读入，例如：

```c++
string x;
while(getline(cin,x))
{
    cout<<x<<endl; //换行符会被丢弃，因此需要手动添加endl;
}
```

**sring的empty和size函数**

empty函数根据string对象是否为空返回一个bool类型，如果为空，则返回true，如果不为空则返回falsew，想要调用empty函数，必须实例化一个string对象才可使用成员运算符调用，例如:

```c++
string x;
cin>>x;
if(!x.empty())   //!运算符，如果x为空则返回false,不为空则为true
{
    cout<<"x不为空"<<endl;
}
```

同样的，要使用size函数，则必须实例化一个string对象并且使用成员运算符，因为string本质是一个tring类，size函数则返回string对象的长度，不包括\0空字符，但是包括中间的空白空格等，例如:

```c++
string x;
getline(cin,x);  //如果输入"hello world"
cout<<x.size();   //则输出11
```

**string::size_type类型**

实际上，string类中的size函数返回的函数类型并非是unsighed int类型，而是一种string::size_type类型的值。

size_type类型在具体使用时要通过作用域操作符来说明是在string类中定义的，用来存放一个unsighed类型的值，可以使用auto或者是decltype函数来获取和使用此类型，例如:

```c++
string x="hello world";
auto i=x.size(); //此时i的类型为string::size_type ,值为11。
decltype(x.size()) i=1; //通过decltype接收size()返回值的类型string::size_type ,并把i赋值为1
```

因此，如果表达式中出现了size函数，则最好不要使用int类，防止出现问题。

**比较string对象**

string类对象可以进行比较，对大小写以及size长度敏感,例如==和!=分别检验两个字符串的长度是否相等，以及每个字符是否一致，包括大小写是否一致。

**为String对象赋值**

string类的对象与其他类一样，允许使用另一个string对象进行拷贝初始化赋值。也可以定义后用字符串常量进行赋值，例如:

```c++ 
string x="hello world";
string s=x;  //正确，x拷贝给s
string a;
a="hello world";  //正确，使用字符串常量进行赋值
```

**两个string对象相加**

string类是可以延长的字符串，因此允许两个string类对象相加，即把一个string类对象加到另一个对象上，例如:

``` c++
string a="hello";string b="world";
a+=b; //此时a为"helloworld" ,将b加到了a并重新赋值给a。
```

同时，string对象还允许将string类对象与单个字符相加或与字符串字面值相加，例如:

```c++
string a="world";
a+='s'; //此时a为"worlds"。
a+=" hello";//此时a为"worlds hello“ 。
```

注意，当string类与单字符，字符串字面值混用时，至少保证加号两侧有一个是string对象，如上述代码a:

```c++
string b=a+'s'; //正确，此时b为worlds hellos;
string c="hello"+'s'; //错误，加号两侧至少有一个是string类下的对象
```

**字符串字面值，如"hello"与string并非是同一类型**

##### 练习3.2

```c++
string s;
getline(cin,s);
s='\0';
cin>>s;
```

##### 练习3.3

```c++
cin开头忽视空白，从第一个有效字符读起，遇到空白结束，遇到换行符结束。
getline开头中间结尾均不忽视空格，遇到换行符结束，会读入换行符，但是给string对象赋值时会丢弃换行符
```

##### 练习3.4

```c++
string a,b;
cin>>a>>b;
if(a==b)
{
    cout<<a<<endl;
}
else 
{
  if(a.size()>b.size())
  {
      cout<<a<<endl;
  }
    else   cout<<b<<endl;

}  //变式同理
```

##### 练习3.5

```c++
string x;
while(cin>>x)
{
    cout<< x<<" ";
}
```

#### 3.2.3 处理string对象中的字符



## 4、第四章

## 5、第五章

## 6、第六章

## 7、第七章

## 8、第八章

## 9、第九章

## 10、第十章

## 11、第十一章





