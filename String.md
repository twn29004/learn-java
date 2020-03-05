# java中的String类

## 定义String
```java
//直接定义法
String str = "HelloWorld";
String str;
str = "HelloWorld";
//使用String类定义
String str = new String();   //创建一个空字符序列
String str1 = new String("HelloWorld");
String str2 = new String(str1);   //str1 = str2
//使用字符数组创建String
char a[] = {'H','e','l','l','o'};
String str = new String(a);
String str = new String(a,1,4);  //这里的str为"ello"
/*使用的方法为String(char[],int offset,int count)
offset表示子数组第一个字符的索引，count表示长度
*/
```

## String字符串和整形int的相互转换

### String转化为int
String字符串转为整形主要有两中方法:
```java
String str = "123";
int n = 0;
int m = 0;
n = Integer.parseInt(str);   //第一种方法
m = Integer.valueOf(str).intValue();
```

### int转String
int转String共有三种方法：
```java
String s = String.valueOf(i);  //括号中的值不能为空，否则会有空指针错误
String s = Integer.toString(i);
String s ="" + i;   //耗时较长
```

## String的连接
1. 使用连接运算符"+";当定义的字符串较长时，可以分作多行来写，这样比较容易阅读。
2. 使用concat()方法。`str1.concat(str2);`.如果要连接多个字符串，需要多次调用concat()。
3. 还可以连接其他类型的数据，与整形，浮点型相连并输出结果，使用+就可以了。

## 获取字符串的长度(length())
`str.length()`

## 字符串处理

### 截取子字符串

```java
str.toLowerCase();   //将字符串中的字母全部转化为小写
str.toUpperCase();   //将字符串中的字母全部转化为大写
//非字母字符不受影响
str.trim();         //取出字符串中的空格，同时返回的字符串的长度也会变化，但是这个方法只能去除英文状态的空格
str.substring(int begin_index);  //截取从索引位置处到结束的子字符串
str.substring(int begin_index,int end_index)
//注意java截取子字符串是按字符数来截取的，不是按字节数。也就是说汉字算一个字符，不是按两个字节算
```
### java分割字符串
String类中的split()方法可以按指定的分隔符对目标字符串进行分割，分割后的字符串凡在字符串数组中。
```java
str.split(String sign);
str.split(String sign,int limit);   //其中sign为指定的分隔符，Limit表示分割后生成的字符串的限制个数，如果不指定，到分割完为止
```
使用分割符时应注意如下内容:
1. "."和"|"都是转义字符，必须加"\\";eg str.split("\\.");
2. 如果需要多个分割符分割，可以这用'|'来表示。eg str.split("and | or");
3. 当加入limit后，当数量达到要求的时候，后面的字符串就不再会被分割。

### java字符串替换
```java
str.replace(String oldChar,String newChar);
str.replaceFirst();
str.replaceAll();
```

### 字符串比较
```java
str.equals(String str);  //区分大小写
str.equalsIgnoreCase();   //不区分大小写
str.compareTo();          //按字典顺序比较
```

### 字符串查找
```java
str.indexOf(value);
str.indexOf(value,int fromIndex);
str.lastIndexOf(value);
str.lastIndexOf(value,int fromIndex);
```

