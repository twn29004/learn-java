## Java中类的定义
如果有面向对象编程的经验的话，那表示能够对类有一个很好的理解了，这里不再赘述。

```java
[public][abstract|final]class<class_name>[extends<class_name>][implements<interface_name>] {
    // 定义属性部分
    <property_type><property1>;
    <property_type><property2>;
    <property_type><property3>;
    …
    // 定义方法部分
    function1();
    function2();
    function3();
    …
}
```

- public表示共有的意思，每个java程序的主类必须都是public,而且一个java文件只能有一个public，而且名字必须与文件名一致
- abstract，如果类被abstrace修饰，则该类为抽象类，该类不能被实例化。抽象类中可以有抽象方法，也可以有具体方法(没有使用abstract修饰)，继承该修饰类必须实现该类中的所有抽象方法
- 如果类被final修饰，则不允许继承
- extends:表示继承其他的类
- implements：实现的接口
- property_type 成员变量的类型
- property：成员变量的名称
- function()：表示成员的方法
- 成员变量和方法也是需要public,private等来修饰的
- 类名最好以下划线和字母开头，最好以字母开头，建议使用驼峰命名法。即类名中每个单词的首个字母采用大写字母 

举个例子,一个简单的学生类
```java
public class Student{
   public String name;
   public int age;
   public String StuNum;    //学号
   private double Score;
   public void  SetScore(double  s){   //如果是private的属性的话，实例是无法直接访问的。需要定义一个方法
       this.Score = s;
   }
   public double OutScore(){
       return this.Score;
   }
   public void tell(){
       System.out.println(StuNum +"今年的成绩为" + this.Score);
   }
}
```

## java类中的属性
`[public|protected|private][static][final]<type><variable_name>`
关于权限修饰符
修饰词 | 本类 | 同一个包中的类 | 继承类 | 其他类
:-: | :-: | :-: | :-: | :-:
private | True | False | False | False
protected | True | True | True | False
public | True | True | True | True

## java类中的方法
```java
public class Test {
    [public|private|protected][static]<void|return_type><method_name>([paramList]) {
        // 方法体
    }
}
```
注意，这里的方法的权限修饰词是可以去省略的，对于省略的权限。
修饰词 | 本类 | 同一个包中的类 | 继承类 | 其他类
:-: | :-: | :-: | :-: | :-:
private | True | False | False | False
无(默认) | True | True | False | False
protected | True | True | True | False
public | True | True | True | True

- 关于protected    

    1. 父类的protected成员是包内可见的，并且对子类可见
    2. 若子类与父类不在同一个包中，那么子类中，子类的实例可以访问其从父类继承来的protected方法，而不能访问父类中的protected方法


 - static 表示该方法为静态方法
 - final表示该方法不能被重写或重载
 - abstract表示该方法为抽象方法，所属的类必须是抽象类

 ## java类中的this关键字
 其实可以把this看作目前类的一个实例，具体使用方法为this.属性，this.functon().this还可以构造函数的重载。
 ```java
 public class Dog(){
     private name;
     public Dog(){  //注意构造函数与其他函数的区别
         this("小明"); //注意this()只能在构造函数中使用，这里的是this()不是this
     }
     public Dog(String n){  //带参数的构造函数
         this.name = n;
     }
 }
 ```

 - this()只能在构造函数中使用，而且必须放在第一条句


