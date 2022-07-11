## Note 4

### API & 字符串

java.lang.String()

字符串的内容一经创建，内容是不可更改的

字符串的创建方式：

```java
String st1 = "abcd";
System.out.println(st1);

// 创建空字符串
String st2 = new String();
System.out.println(st2);

//根据传入的字符串，创建字符串对象
String st3 = new String("abcd");
System.out.println(st3);

//根据字符数组创建字符串对象
// 由于字符数组是可以更改的，因此可以用这种方式方便地堆字符串进行改变
char[] chs = {'a', 'b', 'c', 'd'};
String st4 = new String(chs);
System.out.println(st4);

//根据字节数组 创建字符串对象
// 网络传输种中使用
byte[] bytes = {97, 98, 99, 100};
String st5 = new String(bytes);
System.out.println(st5);
```

使用 String st = "abcd" 这种方式创建地字符串，创建之前系统会现在 StringTable  串池 中进行扫描，这样对于已经存在的字符串，直接返回地址值，节省空间

而使用 new 方式创建的字符串，则不会复用



### == 号比较内容

- 对于基本数据类型的数据，其比较的内容是就是数据本身
- 对于引用数据类型，其比较的是地址值（因此，使用直接赋值的方式创建的 String ，由于是保存在串池中，所以是相等的，但是如果都使用 new 方式进行创建，地址值不同，因此也不相等）

String 内容的比较：

- boolean equals()  内容完全一样
- boolean equalsIgnoreCase()  忽略大小写



**注意：**

通过键盘录入（next()）方法输入的字符串最终是通过 new 关键字定义的，因此对于内容一致的两个字符串，直接使用 String 定义和通过 键盘录入 的结果使用 == 号进行比较是不同的。



### 遍历与长度

```
String st.charAt(int index)
```

获取字符串 st 在 index 索引处的字符

因此，对于字符串的遍历可以通过 st.length() 方法来得到，这里注意对于数组，length 是其属性，而对于 String ，长度是其方法

应用场景：



### 截取

使用方法:

```
String result = str.substring(int beginIndex, int endIndex)
```

所截取的内容左闭右开 [a, b )，返回的是截取的字符串字串

第二种方式：

```
String result = str.substring(int beginIndex)
```

截取到末尾

从字符串中截取单个字符：

```
char ch = str.charAt(index)
```

姑且也算是一种截取吧



### 替换

格式：

```
String result = oriString.replace(oldStr, newStr)
```

result 才是替换之后的值

如果需要多次替换，例如实现敏感词替换功能，需要首先定义一个敏感词数组，随后循环遍历，进行替换即可



### StringBuilder

相较于 String 是可变的，可以看作是一个容器，可以随时改变内容，从而提高字符串的操作效率。

例如，直接使用 String 进行多次拼接，会造成内存的浪费，并且效率极低，而 StringBuilder 则是创建一个容器，所有的拼接操作均在这个容器之上进行改变，提高效率

构造方法：

```
public StringBuilder() // 空

public StringBuilder(String str)  // 直接使用字符串初始化
```

常用成员方法：

```
StringBuilder.append()  // 添加内容

StringBuilder.reverse()  // 反转容器的内容

int StringBuilder.length()  // 长度

String StringBuilder.toString()  // 转化为 String 类型
```

Java底层对 StringBuilder 进行了特殊处理，因此可以直接使用 println(StringBuilder) 









### 其他

#### IDEA 将部分代码快速包裹

使用快捷键 `Ctrl + Alt + T`，选择使用 if 或者 for 等代码进行包裹





