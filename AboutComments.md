## 类注释
类注释一般放在所有的import之前，类定义之前，应该声明类是干什么的，以及创建者，创建日期，版本，包名等信息。
```java
/**
 * @projectName（项目名称）: project_name
 * @package（包）: package_name.file_name
 * @className（类名称）: type_name
 * @description（类描述）: 一句话描述该类的功能
 * @author（创建人）: user 
 * @createDate（创建时间）: datetime  
 * @updateUser（修改人）: user 
 * @updateDate（修改时间）: datetime
 * @updateRemark（修改备注）: 说明本次修改内容
 * @version（版本）: v1.0
 */
```
显示这是一个文档注释，可以通过命令行生成关于这个类的文档

## 方法的注释
方法注释必须紧靠在方法定义的前面，主要声明方法参数、返回值、异常等信息。除了可以使用通用标签外，还可以使用下列的以@开始的标签。
- @param 变量描述：对当前方法的参数部分添加一个说明，可以占据多行。一个方法的所有 @param 标记必须放在一起。
- @return 返回类型描述：对当前方法添加返回值部分，可以跨越多行。
- @throws 异常类描述：表示这个方法有可能抛出异常。
```java
/**
 * @param num1: 加数1
 * @param num2: 加数2
 * @return: 两个加数的和
 */
public int add(int num1,int num2) {
    int value = num1 + num2;
    return value;
}
```

## 字段注释
```java
/**
 * 用户名
 */
public String name;
```