## 1. Java 基础

### 1.1. Java 入门

#### 1.1.1 关于Java技术

​	Java 技术既是编程语言又是平台。

##### 1.1.1.1 Java编程语言

​	Java 是一种编译和解释共存的语言。在 Java 编程语言中，所有源代码都是以 .java 扩展名结尾的纯文本文件。javac 编译器会讲 .java 文件编译为后缀为 .class 的文件，它包含字节码（Java虚拟机的机器语言）。之后 Java 虚拟机的实例会解释（将字节码转化为机器码）并运行该程序。

![](..\images\getStarted-compiler.gif)

​	

​	由于不同的平台（x86、ARM等）CPU 的指令集不同 ，Java 官方针对不同平台编写了虚拟机（JVM），每个平台都有对应的 JVM，不同平台的虚拟机负责加载字节码并执行，这样就实现了“一次编写，多处运行”的效果。 	

![](..\images\helloWorld.gif)

##### 1.1.1.2 Java 平台

​	一个平台是程序运行的硬件或软件环境。 我们已经提到了一些最受欢迎的平台，例如 Microsoft Windows，Linux，  Mac OS 等。 大多数平台可以描述为操作系统和底层硬件的组合。 Java平台与大多数其他平台的不同之处在于，它是一个基于软件的平台，可以在其他基于硬件的平台上运行。  



Java 平台版本

- Java SE（ Standard Edition ）
- Java EE（ Enterprise Edition ）
- JAVA ME（ Micro Edition ）

三者的关系：

```ascii
┌───────────────────────────┐
│Java EE                    │
│    ┌────────────────────┐ │
│    │Java SE             │ │
│    │    ┌─────────────┐ │ │
│    │    │   Java ME   │ │ │
│    │    └─────────────┘ │ │
│    └────────────────────┘ │
└───────────────────────────┘
```

 	简单来说，Java SE 就是标准版，包含标准的 JVM 和标准库，而 Java EE 是企业版，它只是在 Java SE 的基础上加上了大量的 API 和库，以便方便开发Web应用、数据库、消息服务等，Java EE 的应用使用的虚拟机和 Java SE完全相同。 

​	 Java ME 就和 Java SE 不同，它是一个针对嵌入式设备的“瘦身版”，Java SE 的标准库无法在 Java ME 上使用，Java ME 的虚拟机也是“瘦身版”。 



 Java平台具有两个组件： 

- Java VM（ Java Virtual Machine ）
- Java Application Programming Interface (API) 

JVM 是 Java 平台的基础，并且已经移植到各种基于硬件的平台上。

API 是大量现成的软件组件的集合，这些组件提供了许多有用的功能。它分为相关类和接口的库。这些库称为**软件包**。 

![](..\images\getStarted-jvm.gif)

##### 1.1.1.3 Java 常用名词解释

- JDK：Java Development Kit
- JRE：Java Runtime Environment



​	简单地说，JRE 就是运行 Java 字节码的虚拟机。但是，如果只有 Java 源码，要编译成 Java 字节码，就需要 JDK，因为 JDK 除了包含 JRE，还提供了编译器、调试器等开发工具。 

![1612510798734](..\images\1612510798734.png)



### 1.2. Java 语法

#### 1.2.1 Hello World

第一个 Java 程序

 打开文本编辑器，输入以下代码： 

```java
/**
 class：声明类，Java当中组织代码的基本单位
 Hello：类名，大小写敏感，可自定义,必须与文件名一致
 public：访问权限修饰符，全局，表示这个类是公开的，现为固定写法
 static：静态修饰符，静态，现为固定写法
 void：返回值类型，无返回值，现为固定写法
 main：方法名，主方法名，现为固定写法
 String[]:参数类型，形参为字符串数组，现为固定写法
 args：参数名，可以自定义修改，建议固定写为args
 System.out.println(); 是一个固定的输出语句，记住要以分号结束
*/

public class Hello {
    public static void main(String[] args) {
        // 它用来打印一个字符串到屏幕上
        System.out.println("Hello, world!");
    }
}
```

​	方法是可执行的代码块，一个方法除了方法名`main`，还有用`()`括起来的方法参数，这里的`main`方法有一个参数，参数类型是`String[]`，参数名是`args`，`public`、`static`用来修饰方法，这里表示它是一个公开的静态方法，`void`是方法的返回类型，而花括号`{}`中间的就是方法的代码。 

 `public static void main(String[] args)`  是 Java 程序的固定入口方法， 因此，Java程序总是从`main`方法开始执行。 最后，当我们把代码保存为文件时，文件名必须是`Hello.java`，而且文件名也要注意大小写，因为要和我们定义的类名`Hello`完全保持一致。 

####  1.2.2 Java 程序基础结构

 Java 是面向对象的语言，一个程序的基本单位就是`class`，`class`是关键字，这里定义的`class`名字就是`Hello` 

```java
/**
 * 可以用来自动创建文档的注释
 */
public class Hello {
    public static void main(String[] args) {
        // 向屏幕输出文本:
        System.out.println("Hello, world!");
        /* 多行注释开始
        注释内容
        注释结束 */
    }
} // class定义结束
```



类名定义

- 类名必须以英文字母开头，后接字母，数字和下划线的组合
- 习惯以大写字母开头

要注意遵守命名习惯，好的类命名：

- Hello
- NoteBook
- VRPlayer

