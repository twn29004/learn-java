Java的大部分流程控制语句与c,cpp一致，这里介绍几个不一样的；
## foreach语句
首先我们知道for语句的格式为
```
for(条件表达式1，条件表示式2，条件表达式3){   //如果满足条件表示2，则循环可以继续
    语句块
}
```

下面我们介绍foreach语句:
```
for(类型:变量名:集合){
    语句块
}
```
foreach循环语句是java1.5的新特征之一，在遍历数组和集合方面的表现特别优异。
```java
int[] numbers = {43,25,26,37,48};
for(int item : numbers){
    System.out.println("Count is " + item);
}
```

