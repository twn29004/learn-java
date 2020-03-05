## 对象的创建
### 显示创建
1. 使用new关键字创建对象
`class_name object_name = new class_name(); `
2. 调用对象的clone()方法
`class_name object_name = (类名)object_name1.clone();`
其中，object_name1的是一个已经存在的对象的名称
两者的区别是，使用new创建的对象会调用类的构造函数，而使用clone的时候不会调用类的构造函数，而是复制一个对象，他的内容与原对象一致。
### 隐含创建对象
eg `String strName = "StrValue";`
StrValue就是一个String对象。有Java虚拟机隐含的创建


无论采用哪种方式创建对象，都包括以下步骤:

- 给对象分配内存
- 将对象实例变量自动初始化为默认值
- 初始化对象，给实例赋予正确的初始值


### 匿名对象
如果一个对象只是用一次，我们可以采用匿名对象的方法，这样可以减少内存空间的开销。具体方法如下`new class_name().function()`;使用这种方法创建的对象不会占用内存空间，使用的是堆空间，在这条语句执行完之后，他使用的空间就会被垃圾回收机制回收。

## java访问对象的属性和行为
如果一个对象要被使用，则对象必须被实例化，如果一个对象没有被实例化而直接调用属性或方法，例如:
```java
Student stu;
stu.name = "test";
```
则程序运行会抛出如下异常:
`Exception in thread "main" java.lang.NullPointerException`
其实这个很好理解，你创建了一个对象，但是系统并没有为这个对象分配内存空间。必然报错。

## java对象的销毁
在消除对象的时候，由系统自动进行内存回收，不需要用户进行额外的处理。一个对象被销毁的情况有以下两种:
1. 对象的引用超过其作用范围
```java
//代码块
{
    Object o = new Object();
}
{
    在这个代码块中,o被销毁
}
```
2. 对象被赋为null
```java
Object o = new Object();
o = null;
```

