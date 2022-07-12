# [从C到C++（附B站视频）](https://www.bilibili.com/video/BV1rL4y1s7Tw)  

## 1. [const](https://www.runoob.com/w3cnote/cpp-const-keyword.html)

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

e.g.3
```cpp
int a = 8;
const int* const p = &a;  //这种前后都是const，咋都改不了
```

## 2. [C++中的引用](https://blog.51cto.com/yang/2892138)

`int&`即为C++中的引用(reference)，实际上就是一个变量的别名  

它与指针变量有很多相似之处，很多人说`int& p <=> int* const p`，但是实际上二者还是有着区别的  

另外**在main函数中调用swap函数时实参不必再变量名前加&以表示地址，系统传递的是`实参的地址`不是实参的值。**

以下为原博文内容：

<p>这里的&amp;不是取地址符号，而是引用符号，引用是C++对C的一个重要补充。变量的引用就是变量的别名，讲的通俗一点就是另外一个名字，比如：“张三这个人在家里，老爸老妈叫他三娃子，那么这个三娃子就是指张三这个人，如果叫张三去做某事，就是叫三娃子去做某事，这两个名字指的是同一个人。”同样可以理解如果变量b是变量a的引用 那么无论a，b中任<br /> 何一个值改变，另外一个也相应的改变，在声明一个引用时，必须同时使之初始化，即声明它代表哪一个变量。请注意：由于引用不是独立的变量，编译系统不给它单独分配存储单元，因此在建立引用时只有声明没有定义，只是声明它与原有的某一变量的关系。</p> 
<p>在声明一个变量的引用后，在本函数执行期间，该引用一直与其代表的变量相联系，不能再作为其他变量的别名。说得简单点：张三和三娃子是指同一个人，不能李四也叫三娃子，如果可以这样，叫三娃子去做什么，是叫李四呢还是张三呢，这就会乱套了。所以在C++中一个引用变量只能对应一个原始的变量，不能对应两个或多个原始的变量；</p> 
<p>下面简单说明引用：</p> 
<ul><li>a)声明引用时必须指定它代表的是哪一个变量，即对它初始化。</li></ul><pre><code class="prism language-cpp"><span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>b<span class="token punctuation">;</span>
</code></pre> 
<p>这样是声明a是变量b的引用<br /> 如果是int &amp;a;这样就是错的，没有指定a代表哪一个变量。</p> 
<ul><li> <p>b)引用与其所代表的变量共享同一内存单元，系统并不为引用另外分配存储单元；这个应该好理解；就像前面所说的，张三和三娃子都是同一个人，三娃子只是张三的别名。因此，对于 int &amp;a=b;这个例子来说，要输出a和b 的地址，肯定是相同的。</p> </li>
<li> <p>c)怎样区分&amp;是引用还是取地址符呢？方法是：判断&amp;a这样的形式前是否有类型符即int &amp;a=b;如果有类型符(int)则是引用，否则是取地址运算符。</p> </li>
<li> <p>d)对引用的初始化，可以是一个变量名，也可以是另一个引用。<br /> 换句话说：张三的别名可以是三娃子，三小子……及其他多个别名<br /> 而三娃子也可以有其他的别名，比如说：老三，小三等</p> </li>
</ul><p>用程序可以这样：</p> 
<pre><code class="prism language-cpp"><span class="token keyword">int</span> a<span class="token operator">=</span><span class="token number">1</span><span class="token punctuation">;</span> <span class="token comment">//这里是定义一个整形变量</span>
<span class="token keyword">int</span> <span class="token operator">&amp;</span>b<span class="token operator">=</span>a<span class="token punctuation">;</span><span class="token comment">//声明b是整型变量a的别名</span>
<span class="token keyword">int</span> <span class="token operator">&amp;</span>c<span class="token operator">=</span>b<span class="token punctuation">;</span><span class="token comment">//声明c是整型引用变量b的别名</span>
<span class="token keyword">int</span> <span class="token operator">&amp;</span>d<span class="token operator">=</span>a<span class="token punctuation">;</span><span class="token comment">//声明d是整型变量a的别名</span>
</code></pre> 
<ul><li>e)引用初始化后不能再被重新声明为另一变量的别名<br /> 即三娃子既然是指张三这个人，就不能让其他人也叫三娃子<br /> 即一个别名只能对应一个原始变量，但是一个原始变量可以有多个别名，而且别名也可以由自己的别名。</li></ul><hr /><p>C++中增加引用主要是作为函数参数，进行数据传递的功能；</p> 
<p>我们知道如果用变量名作为实参，其传递方向是单向的，而用引用作为实参其传递方向是双向的；</p> 
<p>也许你会问，在c语言中不是有指针吗，用指针进行参数传递不也是双向的吗？其实其本质上也是值传递，只不过是将变量的地址传给指针，通过指针获取变量的值，这样做虽能得到结果，但通过指针运算符去访问有关变量，比较麻烦。</p> 
<p>下面分析一下使用引用和使用指针变量作为函数形参的不同(以例子1中的swap函数为例)：</p> 
<p>1、如果使用引用，则不必在swap函数设立指针变量，指针变量要另外开辟内存单元，其内容是地址。而引用不是一个独立的变量，并不占用内存单元<br /> 2、在main函数中调用swap函数时实参不必再变量名前加&amp;以表示地址，系统传递的是实参的地址不是实参的值。<br /> 3、使用指针变量时，为了表示指针变量所指向的变量，必须使用指针运算符，而使用引用时，引用就代表该变量，不必使用指针运算符；<br /> 4、用引用完成的工作，用指针也能完成。但引用比指针的使用直观、方便，直截了当，</p> 
<p>不必“兜圈子”，容易理解。有些过去只能用指针来处理的问题，现在可以用引用来代替，</p> 
<p>从而降低了程序设计的难度。<br /> 对引用进一步说明：</p> 
<ul><li>1、不能建立void类型的引用。<br /> 因为任何实际存在的变量都是属于非void类型的，void的含义是无类型或空类型，<br /> void只是在语法上相当于一个类型而已。</li>
<li>2、不能建立引用的数组。<br /> 如：</li>
</ul><pre><code class="prism language-cpp"><span class="token keyword">char</span> c<span class="token punctuation">[</span><span class="token number">6</span><span class="token punctuation">]</span><span class="token operator">=</span><span class="token string">"hello"</span><span class="token punctuation">;</span>
<span class="token keyword">char</span> <span class="token operator">&amp;</span>rc<span class="token operator">=</span>c<span class="token punctuation">;</span><span class="token comment">//错误</span>
</code></pre> 
<p>因为数组名是数组首元素的地址，本身不是一个占有存储空间的变量。</p> 
<ul><li>3、可以将变量的引用的地址赋给一个指针，此时指针指向的是原来的变量。<br /> 这句话可以这样说：将引用变量的地址赋给一个指针，此时指针指向的是引用变量，相当于指向原来的变量</li></ul><pre><code class="prism language-cpp"><span class="token keyword">int</span> a<span class="token operator">=</span><span class="token number">2</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token operator">&amp;</span>b<span class="token operator">=</span>a<span class="token punctuation">;</span><span class="token comment">//这个声明语句中的&amp;是一个引用</span>
<span class="token keyword">int</span> <span class="token operator">*</span>p<span class="token operator">=</span><span class="token operator">&amp;</span>b<span class="token punctuation">;</span><span class="token comment">//这个指针初始化语句中的&amp;是取地址运算符</span>
</code></pre> 
<p>上面一行等价于</p> 
<pre><code class="prism language-cpp"> <span class="token keyword">int</span> <span class="token operator">*</span>p<span class="token operator">=</span><span class="token operator">&amp;</span>a<span class="token punctuation">;</span>
</code></pre> 
<p>但是不能定义指向引用类型的指针变量，不能写成</p> 
<pre><code class="prism language-cpp"><span class="token keyword">int</span> <span class="token operator">&amp;</span> <span class="token operator">*</span>p<span class="token operator">=</span><span class="token operator">&amp;</span>a<span class="token punctuation">;</span><span class="token comment">//企图定义指向引用类型的指针变量p，错误</span>
</code></pre> 
<p>因为引用不是一种独立的数据类型，因此不能建立指向引用类型的指针变量。</p> 
<ul><li>4、可以建立指针变量的引用如</li></ul><pre><code class="prism language-cpp"><span class="token keyword">int</span> i<span class="token operator">=</span><span class="token number">5</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token operator">*</span>p<span class="token operator">=</span><span class="token operator">&amp;</span>i<span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token operator">*</span> <span class="token operator">&amp;</span>pt<span class="token operator">=</span>p<span class="token punctuation">;</span><span class="token comment">//建立指针变量p的引用pt</span>

</code></pre> 
<p>引用变量pt代表一个int *类型的数据对象(即指针变量)</p> 
<ul><li>5、可以用const对引用加以限定，不允许直接改变该引用的值，但是可以改变原变量的值去改变引用的值；</li></ul><pre><code class="prism language-cpp"><span class="token keyword">int</span> i<span class="token operator">=</span><span class="token number">5</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>i<span class="token punctuation">;</span>
a<span class="token operator">=</span><span class="token number">3</span><span class="token punctuation">;</span><span class="token comment">//错误，因为引用a是const int 类型不能直接改变引用的值</span>

</code></pre> 
<p>但是可以这样修改：</p> 
<pre><code class="prism language-cpp">
i<span class="token operator">=</span><span class="token number">3</span><span class="token punctuation">;</span>
</code></pre> 
<p>此时输出i和a都是3</p> 
<ul><li>6、可以用常量或表达式对引用进行初始化，但此时必须用const作声明。</li></ul><pre><code class="prism language-cpp"><span class="token keyword">int</span> i<span class="token operator">=</span><span class="token number">5</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>i<span class="token operator">+</span><span class="token number">1</span><span class="token punctuation">;</span>
</code></pre> 
<p>此时编译系统是这样处理的：生成一个临时变量，用来存放该表达式的值，引用是</p> 
<p>该临时变量的别名、系统将“const int &amp;a=i+1;”转换为</p> 
<pre><code class="prism language-cpp"><span class="token keyword">int</span> temp<span class="token operator">=</span>i<span class="token operator">+</span><span class="token number">1</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>temp<span class="token punctuation">;</span>

</code></pre> 
<p>临时变量是在内部实现的，用户不能访问临时变量；</p> 
<p>用这种办法不仅可以用表达式对引用进行初始化，还可以用不同类型的变量对之</p> 
<p>初始化；如</p> 
<pre><code class="prism language-cpp"><span class="token keyword">double</span> d<span class="token operator">=</span><span class="token number">3.1415926</span><span class="token punctuation">;</span>
<span class="token keyword">const</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>d<span class="token punctuation">;</span>

以上等价为：

<span class="token keyword">double</span> d<span class="token operator">=</span><span class="token number">3.1415926</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> temp<span class="token operator">=</span>d<span class="token punctuation">;</span>
<span class="token keyword">const</span> <span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>temp<span class="token punctuation">;</span>

如果在上面不用<span class="token keyword">const</span>则会发生错误

<span class="token keyword">double</span> d<span class="token operator">=</span><span class="token number">3.1415926</span><span class="token punctuation">;</span>
<span class="token keyword">int</span> <span class="token operator">&amp;</span>a<span class="token operator">=</span>d<span class="token punctuation">;</span><span class="token comment">//未加const，错误</span>
</code></pre> 
<p>为什么？因为如果可以这样做，那么修改引用a的值(如a=3.56),则临时变量temp的值也变为3.56，即修改了临时变量temp的值，但不能修改变量d的值，这往往不是用户所希望的，即存在二义性。与其允许修改引用的值而不能实现用户的目的，还不如不允许修改引用的值。这就是C++规定对这类引用必须加const的原因。</p> 

<a></a>区别实例 
<p><img src="https://s2.51cto.com/images/blog/202106/10/339a5ae3bb918d6a8c36534facc684a2.png?x-oss-process=image/watermark,size_16,text_QDUxQ1RP5Y2a5a6i,color_FFFFFF,t_30,g_se,x_10,y_10,shadow_20,type_ZmFuZ3poZW5naGVpdGk=" alt='C++中int int& int * int**的区别、联系和用途_C/C' /><br /><strong>结果</strong>：<br /><img src="https://s2.51cto.com/images/blog/202106/10/831cadd14165e176faf10e495a69a31f.png?x-oss-process=image/watermark,size_16,text_QDUxQ1RP5Y2a5a6i,color_FFFFFF,t_30,g_se,x_10,y_10,shadow_20,type_ZmFuZ3poZW5naGVpdGk=" alt='C++中int int& int * int**的区别、联系和用途_C/C_02' /></p>
                </div>
                </div>
            </div>
