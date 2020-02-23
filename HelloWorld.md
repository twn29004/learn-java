
前面已经完成了IDEA的安装和JDK的安装，下面我们将进行第一个程序HelloWolrd的编写

---

## 创建新项目
`File->New->Project->java`,如果前面配置好的话，我们可以看到默认的SDK是java8，当然这是可以根据开发需要更换的.然后就一路`next`,来到了这个页面。填写和是的`project name`,同时选择合适的路径。然后点击`finish`

---

## 写代码
项目创建成功之后，会打开一个新的窗口，在窗口的右侧，查看项目中的文件。可以看到一个`src`文件夹。我们的源代码就是放在这里。右键新建一个java类，填入一下代码
```java
public class HelloWorld {
    public static void main(String[] args){
        System.out.println("Helllo,World");
    }
}
```
---
## 运行程序
菜单栏选择`run`,然后再选择HelloWorld。或者直接再右上角的`Edit Configuration`,下拉菜单选择HelloWorld


---
## 输出结果
结果自动输出在下方的终端中