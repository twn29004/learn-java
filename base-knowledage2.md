## java的数据类型转化
### 隐式转化(自动类型转化)
自动类型转化需要满足2个条件:
1. 两中数据类型彼此兼容
2. 目标类型的取值范围大于源数据类型(低级数据类型转化为高级数据类型)
eg:数值型的数据转化:byte->short->int->long->float->double
字符型转换:char->int
```java
public class tran{
    public static void main(String[] argv){
        byte a = 19;   //范围为-128-127
       // a = a * 2;     //这句会有"报错不兼容的类型: 从int转换到byte可能会有损失"，
        /*原因是a * 2执行的类型转化是从byte转化到int,最终得到的结果也是int，但是讲结果赋值给a,就需要转化为byte,
        这是违反原则的*/ 
        //正确的操作
        a = (byte)(a * 2);   //强制类型转换
        System.out.print(a);
    }
}
```

### 显示类型转化(强制类型转换)
转化的代码为`(type)variable_name`

## 关于java的运算符
- java中的算术运算符大部分和c,cpp中的一致，需要注意的是关于标准输入输出部分,也和c,cpp很相似，其中`%d`表示整数，`%c`表示字符，如果需要控制输出格式的话，可以使用printf函数。
- java中的逻辑运算符，比c,cpp中多了两个。   

运算符 | 标识 | 含义
:-:  | :-: | :-: 
`&&` | a`&&`b | a,b都为true是，结果为true.只要a为false，就停止判断b
`||` | a `||` b | a,或b都为false才为false,只要a为ture,就停止判断b
`&` | a `&` b | 结果同`&&`，不同的是a,b都要计算
`|` | a `|` b | 结果同`|`，不同也是a,b都要计算

因此`||`,`&&`也被称为短路或和短路与，其优势是可以减少计算量。所以在实际使用中，我们应该优先考虑使用短路与和短路或。

## java的位运算符
java的位运算符同c,cpp中的基本一致。

## java中的三目运算符有基本与c,cpp一致
`result = <expression> ? <statement1> : statement<2>`,如果表达式为真，则结果为statament1,否则为statement2.
```java
a = (x > y) ? (x -= y) ； (x += y);
```

## java运算符优先级啊
![java运算符优先级表](https://s2.ax1x.com/2020/02/23/3114FH.png)

