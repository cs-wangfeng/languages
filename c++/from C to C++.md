# [从C到C++（B站视频）](https://www.bilibili.com/video/BV1rL4y1s7Tw)  

## [const](https://www.runoob.com/w3cnote/cpp-const-keyword.html)

`const`是`constant`的缩写，本意是**不变的，不易改变的**意思。在 C++ 中是用来修饰**内置类型变量，自定义对象，成员函数，返回值，函数参数**。

C++ const 允许指定一个**语义约束**，编译器会强制实施这个约束，允许程序员告诉编译器某值是保持不变的。如果在编程中确实有某个值保持不变，就应该明确使用const，这样可以获得编译器的帮助。

一旦被`const`修饰之后，就不能够继续进行修改了，因为对于一个常量进行修改是违法的。

### const修饰指针
> A: const 修饰指针指向的内容，则内容为不可变量。
> 
> B: const 修饰指针，则指针为不可变量。
>
> C: const 修饰指针和指针指向的内容，则指针和指针指向的内容都为不可变量。

- 口诀：左定值，右定向，const修饰不变量

例如：

e.g.1 
```cpp
const int* p = 8;
```
这个定义，相当于将`p`指向的值固定下来了，也就是所说的“左定值”

e.g.2
```cpp
int a = 8;
int* const p = &a;
int b = 9;
p = &b;  //不行，因为p这个指针是const，不能改变
*p = 9;  //可以，因为int* p不是const
```
右定向（也就是指针），相当于指针（地址）是constant，但是指针所指的东西并不是constant
