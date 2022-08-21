---
title: Qt
date: 2021-07-27 20:31:46
tags:
---

*和老大提出辞职之后，商量了关于我的工作后续的事情，便开始寻找新工作......*
	目的地是在重庆的一家公司，具体什么名字，暂时不透露了，面的`C++ & Qt`，按照面试官的说法，这是一个纯`Qt`的岗位，所以接下来的问题大概全部是和`Qt`相关的，当然也会有部分C++的问题在其中。

<!-- more -->

<font style="color:pink">废话不多说，我们进入正题：</font>

## C++部分的问题：

- 第一部分是关于C++这门语言的，面向对象是什么？

  ```C++
   // OOP
   // 封装,继承,多态
  ```

- 对于多态的理解?

  ```C++ 
  // 首先是如何实现多态？
  1. 多态发生在继承关系中。
  2. 需要重写虚函数。
  3. 父类的指针指向子类的对象。
  4. 通过父类指针对重写的虚函数发起调用，最终调用你要想调用的函数。
  ```
example：
  ```C++
class A
  {
  public:
      A(){std::cout<<"A"<<std::endl;}
  
      virtual void function_virtual()
      {
          std::cout<<"function_A"<<std::endl;
      }
  private:
      int menber;
  
  };
  
  class B: public A
  {
  public:
      B():A(){std::cout<<"B"<<std::endl;}
  
      virtual void function_virtual()
      {
          std::cout<<"function_B"<<std::endl;
      }
  };
  
  class D: public A
  {
  public:
      D():A(){std::cout<<"D"<<std::endl;}
  
      virtual void function_virtual()
      {
          std::cout<<"function_D"<<std::endl;
      }
  };
  
  int main()
  {
      A * a = new A;
      B * b = new B;
      D * d = new D;
  
      A * ptr = b;
      ptr->function_virtual();
  
      ptr = a;
      ptr->function_virtual();
  
      ptr = d;
      ptr->function_virtual();
  	
      return 0;
  }
  
  ```
	<font style="color:red">结果如下：</font>
	![polymorphism](https://raw.githubusercontent.com/CuntBoy/images/main/polymorphism.png "polymorphism")


- 多态的实现 -- <font style="color:red">虚函数表</font>

  - 验证虚函数表：

    ```C++
    // 一个简单的C 不带有虚函数 
    class C
    {
    public:
        C(){std::cout<<"C"<<std::endl;}
    private:
        long long member;
    };
    ```
	<font style="color:red">输出结果:</font> ![virtual_table](https://raw.githubusercontent.com/CuntBoy/images/main/virtual_table_1.png "virtual table 1")
  	
  	![virtual table 2](https://raw.githubusercontent.com/CuntBoy/images/main/virtual_table_2.png "virtual table 2")
  	
  	- 上面的结果可以看出存在一个成员(存在虚函数的情况)，大小为8个字节(64位软件)。

---

## Qt部分

- 元对象系统
- 窗口刷新机制
- 内存托管(删除机制)
- Qquick
- Qt的布局



## OPENGL部分

- 缓冲(双缓冲)

- 着色器程序(语言)

  