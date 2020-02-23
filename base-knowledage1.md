## 关键字

1. 数据类型: boolean、int、long、short、byte、float、double、char、class、interface;
2. 流程控制: if、else、do、while、for、switch、case、default、break、continue、return、try、catch、finally;
3. 修饰符:public、protected、private、final、void、static、strict、abstract、transient、synchronized、volatile、native;
4. 动作: package、import、throw、throws、extends、implements、this、supper、instanceof、new;
5. 保留字:true、false、null、goto、const。

由于Java是区分大小写的，所以public是关键字，Public不是关键字，但是一般不这么使用。毕竟这太迷惑了。


## 注释
1. 单行注释，类似于c,cpp
2. 多行注释，同样类似于c,cpp
3. 文档注释，大概类似于下面这种情况,文档注释使用的注释符号为`\** *\`
```java
/**
 * 文档注释，一般用于类或者方法的前面，用于说明类或者方法特性
 */
public class HelloWorld {
    /*
        多行注释
        可以注释多行
    */
    public static void main(String[] args){
        System.out.println("hello world"); //单行注释
    }
}
```
关于文档注释和多行注释的区别大概是文档注释可以通过`javadoc file_name.java`生成一个文档。关于javadoc中阅读，可以搜索网上资料自行查阅

## Java常量

### 基本概念
- 常量就是在程序运行过程中不能改变的量，常量值就是字面意思，常量的值。
### 常量值的类型 

#### 整数常量值
1. 十进制整数，就是常见的整数
2. 八进制整数，java中的八进制整数一般以0开头
3. 十六进制整数，0x开头。
4. 长整型在java中的表示形式为数字后面夹L护着l,注意是小写不是1.int占32位,long占64位

#### 实型常量值
1. 十进制形式，正常的小数点形式
2. 科学计数法，也和c,cpp中一致1e5+3,表示10^5+3,1.75e5,表示1.75*10^5。java中默认是double,当要求精度不是很高的时候，可以在数字后面加f或者F，以提高程序运行的速度，降低内存的消耗。

#### 布尔型常量值
就是`true or false`

#### 字符型或者字符串常量值
字符使用'j',字符串使用"java",切记不可混用，不要被python误导了。还有java中的转义字符也应该了解。

### 定义常量
定义常量的语法如下：
`final data_type variable_name = value`
类似于下面这种：
```java
public class HelloWorld {
    // 静态常量
    public static final double PI = 3.14;
    // 声明成员常量
    final int y = 10;

    public static void main(String[] args) {
        // 声明局部常量
        final double x = 3.3;
    }
}
```
对于静态常量的说明:其作用域是全局的，不需要创建对象就可以访问他。   
此外，显然常量是不能在程序运行过程中是不能被改变的，否则会抛出异常。同时，为了于变量名区别，常量取名一般用大写字符。

## 变量
java的变量有两种类型，一种是成员变量，另一种是局部变量。
### 成员变量
java中的成员变量有两种全局变量和静态变量(类变量)，定义在方法或者语句快之外，不属于任何一个方法，作用域属于一个类。    
名称 | 修饰 | 访问 | 生命周期 
:-:  | :-: | :-: | :-: 
全局变量 | 无static修饰 | object_name.variable_name | 只有对象被当作引用，实列变量就讲存在
静态变量 | 用static修饰 | class_name.object_name.variable_name | 其生命周期取决于类的生命周期。类被挥手的时候才被销毁。

```java
class DataClass{
    String name = "twn";
    int age = 20;
    static int test1 = 5;
    static String test2 = "test2";
}
public class MemVar{
        public static void main(String[] argc){
        DataClass cd1 = new DataClass();
        DataClass cd2 = new DataClass();
        System.out.println(cd2.test1);   //先输出cd2的test1
        System.out.println(cd2.age);
        cd1.age = cd1.age + 1;
        cd1.test1 = cd1.test1 + 1;      //修改cd1的test1
        System.out.println(cd2.test1);  //再次输出长度的test1
        System.out.println(cd2.age);
    }
}
```

通过上述代码我们可以看出，虽然更改的是cd1的test1,但是cd2的test1也发生了变化。这也体现出了静态变量于成员变量的区别,但是变化age并没有引起其他实例的变化。

补充一个小知识:
1. 一个`.java`文件中只能有一个`public`类，而且这个`public`类的名字必须和文件名一致，包括大小写。当然一个文件中不含`public`也是可以的，这时我们就可以对文件名任意命名了.
2. 关于修饰类和变量作用域或者适用范围的关键字:
    1. public:表示公开的类或变量，既所有的类都可以引用
    2. protected:表示受保护的类，只有子类或者本类可以引入使用
    3. 默认package:表示同包和本类中可以引入使用
    4. private:表示私有的，只有在本类中才能引用

    所以，如果一个class前面没有添加任何关键字，则默认位package,可以被同包中的类和本类引入使用。

### 局部变量

指其作用域为一个代码块。可以分为以下三种:
1. 方法参数变量，其作用域为整个方法。
2. 方法局部变量，其作用域为定义的那个方法中的代码块。
3. 代码块局部变量，起作用域为定义的那个代码块。
局部变量使用前必须主动初始化。
```java
public class part_var{
    public static void Fun(int var1){
        System.out.println(var1);    //var1为方法参数变量
     }
     public static void main(String[] argv){
         int a = 7;   //a为方法局部变量
         if(a > 5){
             int s = 6;    //s为代码块局部变量
             Fun(s);
         }
     }
}
```