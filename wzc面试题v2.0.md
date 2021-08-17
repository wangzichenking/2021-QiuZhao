# wangzichen面经大全（V3.0终版）

## 更新进度（参考牛客面经）

**Java开发工程师(2021.5.18——2021.7.3)**

**美团提前批客户端(2021.7.19——2021.8.3)**

**用友Java开发工程师(2021.4.9——2021.8.12)**

**百度测试开发工程师(2021.6.1——2021.8.13)**

**携程测试开发工程师(XXX——2021.4.26秋招还没有)**

## Java基础和集合

### 面向对象设计的优点（用友Java）？

1. **维护简单：**面向对象程序设计的一个特征就是模块化。实体可以被表示为类以及同一名字空间中具有相同功能的类，可以在名字空间中添加一个类而不影响该名字空间的其他成员。这种特征为程序的维护提供了便捷性。
2. **可扩充性：**如果有一个具有某一种功能的类，就可以扩充这个类，创建一个具有扩充功能的类。
3. **代码重用：**功能是被封装在类中的，类是作为一个独立实体而存在的，因此可以很简单的提供类库，使代码得以重复使用。

### 怎么理解面向对象？（知乎测开）

面向对象就是看事物的一种方式，一种视觉角度，分析方式，我们可以把任意一个事物看成是一个对象，分析它身上具备的主要特征，这个就是面向对象思维。

我们把事物当做一个对象，分析它的主体特征，注意力聚焦在主体特征，而不是聚焦于更细节的内容及实现，如我们把手机当做一对象，现在我们要开发手机，手机是个对象，它有哪些特征呢，比如颜色、手机壳、打电话、发短信等等，而我们不会去想到发短信具体是怎么实现的，集成电路如何设计，如何接收信号，电磁波如何发出，甚至更加细节的问题。

**把事物当做对象，宏观分析它的具备的主体特征，这已经是面向对象的思维了。**

### 面向对象三大特性？（用友Java，知乎测开）

#### 封装

封装把⼀个对象的属性私有化，同时提供⼀些可以被外界访问的属性的⽅法，如果属性不想被外界访问，我们⼤可不必提供⽅法给外界访问

#### 继承

> 继承是从已有的类中派生出新的类， 新的类能吸收已有类的数据属性和行为，并能扩展新的能力。

继承是使⽤已存在的类的定义作为基础建⽴新类的技术，新类的定义可以增加新的数据或新的功能，也可以⽤⽗类的功能，但不能选择性地继承⽗类。通过使⽤继承我们能够⾮常⽅便地复⽤以前的代码

- ⼦类拥有⽗类对象所有的属性和⽅法（包括私有属性和私有⽅法），但是⽗类中的私有属性和⽅法⼦类是⽆法访问，**只是拥有**
- ⼦类可以拥有⾃⼰属性和⽅法，即⼦类可以对⽗类进⾏扩展
- ⼦类可以⽤⾃⼰的⽅式实现⽗类的⽅法

#### 多态（用友Java）

> 同一操作作用于不同的对象，可以有不同的解释，产生不同的执行结果。

多态就是指程序中定义的引⽤变量所指向的具体类型和通过该引⽤变量发出的⽅法调⽤在编程时并不确定，⽽是在程序运⾏期间才确定，即⼀个引⽤变量到底会指向哪个类的实例对象，该引⽤变量发出的⽅法调⽤到底是哪个类中实现的⽅法，必须在由程序运⾏期间才能决定

### JDK和JRE区别？（用友Java）

JDK是（Java Development Kit）的缩写，它是功能齐全的 Java SDK。它`拥有 JRE 所拥有的一切`，还有
编译器（javac）和工具（如 javadoc 和 jdb），`它能够创建和编译程序`。

JRE是Java Runtime Environment缩写，它是运行已编译 Java 程序所需的所有内容的集合，包括 Java 虚
拟机（JVM），Java 类库，java 命令和其他的一些基础构件。但是，它不能用于创建新程序。

### 一个类可以被加载多次吗？

不可以，原因是双亲委派机制

### Java为什么可以跨平台？

因为Java程序编译之后的代码不是能被硬件系统直接运行的代码，而是一种“中间码”——字节码。然后不同的硬件平台上安装有不同的Java虚拟机(JVM)，由JVM来把字节码再“翻译”成所对应的硬件平台能够执行的代码。因此对于Java编程者来说，不需要考虑硬件平台是什么，所以Java可以跨平台。

因为它有虚拟机（JVM），JAVA程序不是直接在电脑上运行的，是在虚拟机上进行的，每个系统平台都是有自己的虚拟机（JVM），所以JAVA语言能跨平台。 

### == 和 equals区别？（用友Java）

`== `: 它的作⽤是判断两个对象的地址是不是相等。即，判断两个对象是不是同⼀个对象(基本数据
类型`==⽐较的是值，引⽤数据类型==`⽐较的是内存地址)

equals() : 它的作⽤也是判断两个对象是否相等。但它⼀般有两种使⽤情况：

- 情况 1：`类没有覆盖 equals() ⽅法`。则通过 equals() ⽐较该类的两个对象时，等价于通过“==”⽐较这两个对象
- 情况 2：`类覆盖了 equals() ⽅法`。⼀般，我们都覆盖 equals() ⽅法来⽐较两个对象的内容是否相等；若它们的内容相等，则返回 true (即，认为这两个对象相等)

### 有了基本数据类型后，为什么还要有包装类？

我们知道Java是一个面相对象的编程语言，基本类型并不具有对象的性质，为了让基本类型也具有对象的特征，就出现了包装类型（如我们在使用集合类型Collection时就一定要使用包装类型而非基本类型），它相当于将基本类型“包装起来”，使得它具有了对象的性质，并且为其添加了属性和方法，丰富了基本类型的操作。

另外，当需要往ArrayList，HashMap中放东西时，像int，double这种基本类型是放不进去的，因为容器都是装object的，这是就需要这些基本类型的包装器类了。

**1. 包装类里面有一些很有用的方法和属性，如HashCode,ParseInt**

**2. 基本类型不能赋null值，某些场合需要。**

**3. 有些地方不能直接用基本类型，比如集合**

### Object类有那些方法？

1. **getClass方法：**获取运行时类型,返回值为Class对象

2. **hashCode方法：**该方法用于哈希查找，可以减少在查找中使用equals的次数，重写了equals方法一般都要重写hashCode方法。这个方法在一些具有哈希功能的Collection中用到。

> 一般必须满足`obj1.equals(obj2)==true`。可以推出`obj1.hashCode()==obj2.hashCode()`，但是hashCode相等不一定就满足equals。不过为了提高效率，应该尽量使上面两个条件接近等价。如果不重写hashcode(),在HashSet中添加两个equals的对象，会将两个对象都加入进去。

3. **equals方法：**判断两个对象是否相等，在Object源码中equals就是使用去判断，所以在Object中equals是等价于`==`的，但是在String及某些类对equals进行了重写，实现不同的比较。

4. **clone方法：**主要是JAVA里除了8种基本类型传参数是值传递，其他的类对象传参数都是引用传递，我们有时候不希望在方法里将参数改变，这时就需要在类中复写clone方法。

> 保护方法，实现对象的浅复制，只有实现了Cloneable接口才可以调用该方法，否则抛出CloneNotSupportedException异常。

5. **toString方法：**返回一个String字符串,用于描述当前对象的信息,可以重写返回对自己有用的信息，默认返回的是当前对象的类名+hashCode的16进制数字。

6. **wait方法：**多线程时用到的方法，作用是让当前线程进入等待状态，同时也会让当前线程释放它所持有的锁。直到其他线程调用此对象的 notify() 方法或 notifyAll() 方法，当前线程被唤醒

7. **notify方法：**多线程时用到的方法，唤醒该对象等待的某个线程

8. **notifyAll方法：**多线程时用到的方法，唤醒该对象等待的所有线程

9. **finalize：**对象在被GC释放之前一定会调用finalize方法，对象被释放前最后的挣扎,因为无法确定该方法什么时候被调用，很少使用。

### 数组为什么按索引访问那么快？

==数组可以用基地址和偏移量访问的==

-  一个数组中的元素在内存中的存放是连续的，一条链表中的元素在内存中的存放不一定是连续的
- 计算机读写内存中的数据是建立在地址之上的，即根据给定的地址进行相应操作
- 数组下标的实际意义是：相对于数组起始地址的地址偏移量

### 如何让一个类不能被实例化？（百度测开）

```java
public final class Math {
  private Math() {}
}
```

**<font color='blue'>使用私有构造器+final修饰类</font>**

### 集合之间的继承关系？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/collection.png">

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/Map.png">

### ArrayList和LinkedList区别（用友Java）？

1. **是否保证线程安全：** `ArrayList` 和 `LinkedList` 都是不同步的，也就是不保证线程安全；
2. **底层数据结构：** `Arraylist` 底层使用的是 **`Object` 数组**；`LinkedList` 底层使用的是 **双向链表** 数据结构（JDK1.6 之前为循环链表，JDK1.7 取消了循环。注意双向链表和双向循环链表的区别，下面有介绍到！）
3. 插入和删除是否受元素位置的影响：
   - `ArrayList` 采用数组存储，所以插入和删除元素的时间复杂度受元素位置的影响。 比如：执行`add(E e)`方法的时候， `ArrayList` 会默认在将指定的元素追加到此列表的末尾，这种情况时间复杂度就是 O(1)。但是如果要在指定位置 i 插入和删除元素的话（`add(int index, E element)`）时间复杂度就为 O(n-i)。因为在进行上述操作的时候集合中第 i 和第 i 个元素之后的(n-i)个元素都要执行向后位/向前移一位的操作。
   - `LinkedList` 采用链表存储，所以，如果是在头尾插入或者删除元素不受元素位置的影响（`add(E e)`、`addFirst(E e)`、`addLast(E e)`、`removeFirst()` 、 `removeLast()`），近似 O(1)，如果是要在指定位置 `i` 插入和删除元素的话（`add(int index, E element)`，`remove(Object o)`） 时间复杂度近似为 O(n) ，因为需要先移动到指定位置再插入。
4. **是否支持快速随机访问：** `LinkedList` 不支持高效的随机元素访问，而 `ArrayList` 支持。快速随机访问就是通过元素的序号快速获取元素对象(对应于`get(int index)`方法)。
5. **内存空间占用：** ArrayList 的空间浪费主要体现在在 list 列表的结尾会预留一定的容量空间，而 LinkedList 的空间花费则体现在它的每一个元素都需要消耗比 ArrayList 更多的空间（因为要存放直接后继和直接前驱以及数据）。

### 什么情况下使用继承和接口？

1. 当代码重合率达到80%时用继承
2. 重合率达到50%用接口

抽象类和接口的区别在于使用动机,使用抽象类是为了代码的复用，而使用接口的动机是为了实现多态性。

### String和Integer中的“==”问题？

```java
String str1 = "a";
String str2 = "b";
String str3 = "ab";
String str4 = str1 + str2;
System.out.println(str3 == str4); //输出结果？
String str5 = str4.intern();
System.out.println(str3 == str5); //输出结果？
```

第一行："a"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str1;

第二行："b"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str2;

第三行：“ab"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str3;

第四行：str1 + str2,当+号两边存在变量时(两边或任意一边)，在编译期是无法确定其值的，所以要等到运行期再进行处理,处理方法：先new一个StringBuilder，然后append str1 和 str2,所以：str4引用变量指向的是堆中new出来的一个对象，而str3引用变量指向的是字符串池中常量"ab"的地址；

第五行：str3 == str4 比较的str3和str4的引用地址，so false;

第六行：String的intern()方法会将该对象的值转到字符串池中去，如果字符串池已有同样的值，则直接返回地址，如果没有，则在字符串池中新建一个，然后返回地址。再看此例子，显然"ab"已经在字符串池中存在了(第三行)，所以str5和str3均指向字符串池中的"ab”，且语法str3 == str5比较是引用地址，所以输出结输出结果为：true；

注：intern()这个方法API里的解释是：**“当调用 intern 方法时，如果池已经包含一个等于此 String 对象的字符串 (用equals(Object) 方法确定)，则返回池中的字符串。否则，将此 String 对象添加到池中，并返回此 String 对象的引用。”**

---------------

```java
String str1 = "ab";
String str2="a"+"b";
System.out.println(str1 == str2);//输出结果？
```

第一行："ab"作为一个常量存放于字符串池中，并把引用地址赋值给str1;

第二行：“a"和"b"作为两个常量相加，由于编译器优化，在编译期就将+两边拼接合并了，直接认为成是一个常量"ab”，结果发现字符串池中已经有一个常量"ab"了，就直接把"ab"的引用地址赋值给了str2；

第三行：str1 == str2比较的str1和str2的引用地址，当然是一样的，so输出结果： true ;

--------------------------

```java
final String str1 = "a";
final String str2 = "b";
String str3 = "ab";
String str4 = str1 + str2;
System.out.println(str3 == str4);//输出结果？
```

第一行："a"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str1; final使得变量str1被当作一个常量对待

第二行：“b"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str2; final使得变量str2被当作一个常量对待

第三行：“ab"作为一个常量存放于字符串池中，并将它的引用地址赋值给了str3;

第四行：str1 + str2,此时+号两边都是常量哦，在编译期就可以确定其值了

即：String str4 = str1 + str2;

就等价于 String str4 = “a” + “b”;

就等价于 String str4 = “ab”;

第五行：str4指向常量"ab”，str3指向常量"ab”(第三行)，所以str3 == str4 等于true

--------------------

1. 由于Integer变量实际上是对一个Integer对象的引用，所以两个通过new生成的Integer变量永远是不相等的（因为new生成的是两个对象，其内存地址不同）

```java
Integer i = new Integer(100);
Integer j = new Integer(100);
System.out.print(i == j); //false
```

2. Integer变量和int变量比较时，只要两个变量的值是向等的，则结果为true（因为包装类Integer和基本数据类型int比较时，java会自动拆包装为int，然后进行比较，实际上就变为两个int变量的比较）

```java
Integer i = new Integer(100);
int j = 100；
System.out.print(i == j); //true
```

3. 非new生成的Integer变量和new Integer()生成的变量比较时，结果为false。（因为 ①当变量值在-128~127之间时，非new生成的Integer变量指向的是java常量池中的对象，而new Integer()生成的变量指向堆中新建的对象，两者在内存中的地址不同；②当变量值在-128~127之间时，非new生成Integer变量时，java API中最终会按照new Integer(i)进行处理（参考下面第4条），最终两个Interger的地址同样是不相同的）

```java
Integer i = new Integer(100);
Integer j = 100;
System.out.print(i == j); //false
```

4. 对于两个非new生成的Integer对象，进行比较时，如果两个变量的值在区间-128到127之间，则比较结果为true，如果两个变量的值不在此区间，则比较结果为false

```java
Integer i = 100;
Integer j = 100;
System.out.print(i == j); //true
Integer i = 128;
Integer j = 128;
System.out.print(i == j); //false
```

---------------

```java
1.public class Test{
2.    public static void main(String[] args) {
3.        Integer a = new Integer(200);
4.        Integer b = new Integer(200);
5.        Integer c = 200;
6.        Integer e = 200;
7.        int d = 200;
8.
9.          System.out.println("两个new出来的对象    ==判断"+(a==b));
10.        System.out.println("两个new出来的对象    equal判断"+a.equals(b));
11.        System.out.println("new出的对象和用int赋值的Integer   ==判断"+(a==c));
12.        System.out.println("new出的对象和用int赋值的Integer   equal判断"+(a.equals(c)));
13.        System.out.println("两个用int赋值的Integer    ==判断"+(c==e));
14.        System.out.println("两个用int赋值的Integer    equal判断"+(c.equals(e)));
15.        System.out.println("基本类型和new出的对象   ==判断"+(d==a));
16.        System.out.println("基本类型和new出的对象   equal判断"+(a.equals(d)));
17.        System.out.println("基本类型和自动装箱的对象   ==判断"+(d==c));
18.        System.out.println("基本类型和自动装箱的对象   equal判断"+(c.equals(d)));
19.    }
20.}
```

```shell
两个new出来的对象    ==判断false
两个new出来的对象    equal判断true
new出的对象和用int赋值的Integer   ==判断false
new出的对象和用int赋值的Integer   equal判断true
两个用int赋值的Integer    ==判断false
两个用int赋值的Integer    equal判断true
基本类型和new出的对象   ==判断true
基本类型和new出的对象   equal判断true
基本类型和自动装箱的对象   ==判断true
基本类型和自动装箱的对象   equal判断true
----------------------------------------------------------------------------
附加：https://blog.csdn.net/w112736112736/article/details/77986283
```

### String和StringBuilder和StringBuffer？

1. **<font color='red'>可变与不可变？</font>**String类中使用字符数组保存字符串，因为有“final”修饰符，所以string对象是不可变的。对于已经存在的String对象的修改都是重新创建一个新的对象,然后把新的值保存进去.StringBuilder与StringBuffer都继承自AbstractStringBuilder类，在AbstractStringBuilder中也是使用字符数组保存字符串，这两种对象都是可变的。
2. **<font color='red'>是否线程安全？</font>**String中的对象是不可变的，也就可以理解为常量，显然线程安全。StringBuilder是非线程安全的。StringBuffer对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。

```java
@Override
public synchronized StringBuffer append(String str) {
    toStringCache = null;
    super.append(str);
    return this;
}
```

3. 如果你只是在单线程中使用字符串缓冲区，那么StringBuilder的效率会更高些。而且StringBuilder是在JDK1.5版本中增加的。以前版本的JDK不能使用该类。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/stringbuilder.png">

**为什么String是不可变的？**

- String类是用final关键字修饰，这说明String不可继承
- String类的主力成员字段value是个`char[ ]数组`，而且是用`final`修饰的

### HashMap头插法为什么导致死循环（用友Java）？

- 第一个状态

**当线程一刚刚扩容好数组，此时刚要准备进行rehash，但是此时线程二强行插入进来执行，并且线程二已经rehash完成之后的状态图（上半部分表示的线程一，下半部分表示的是线程二）**

<img src="https://img-blog.csdnimg.cn/20190125231950932.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1,size_16,color_FFFFFF,t_70">

- 第二个状态

**此时线程一已经被唤醒了，要开始进行操作rehash操作，把key为5的节点还是挂在数组下标为1的位置上，并且key为5的后面是9这个节点（==这里其实吧之前的数组扩容为4个了，然后肯定需要重新定位下标啊，所以这里是对4进行取余，然后对应查到对应的数组下标下的链表中==）**

<img src="https://img-blog.csdnimg.cn/20190125232018560.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1,size_16,color_FFFFFF,t_70">

- 第三个状态

**从第一个状态开始继续接着处理key为9的节点，所以应该是都挂在桶数组下标为1的链表上顺序为9---->5---->NULL**

<img src="https://img-blog.csdnimg.cn/20190125232045459.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1,size_16,color_FFFFFF,t_70">

- 第四个状态

**此时在第三步时候处理9完毕之后，他发现节点9后面还有一个节点5（这个节点5是因为线程二中已经rehash完毕之后留下的），此时他又会把节点5放在线程一中的首部此时也就是5---->9----5(后面这部分的9–>5是保留的第三个状态留下的)，到这里就形成了死循环**

<img src="https://img-blog.csdnimg.cn/2019012523211371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NTIwMjM1,size_16,color_FFFFFF,t_70">

### HashMap超详细详解

Map接口与Collection接口是不同的，Map接口有两个主要实现类`HashMap类`、`TreeMap类`，**HashMap类按哈希算法来存取键值对象，而TreeMap类可以对键值对象进行排序。**

| 方法名                | 说明                                                         |
| --------------------- | ------------------------------------------------------------ |
| V get(Object key)     | 返回Map结合中指定键值对所对应的值                            |
| V put(K key, V value) | 向Map集合中添加键-值对，返回key以前对应的value，如果没有，则返回null |
| V remove(Object key)  | 从Map集合中删除key对应的键值对，返回key对应的value，如果没有则返回null |
| Set entrySet()        | 返回Map集合中所有键值对的Set集合，类型为Map内部类，Map.Entry |
| Set keySet()          | 返回Map集合中所有**键对象**的Set集合                         |

HashMap在我们Map接口的实现类中的使用中占有很高的频率，在初始化时将会给定`默认容量为16`,扩容的`加载因子为0.75`，当实例内的`结点数量>16*0.75`就会进行扩容，每次扩容都是`1<<2也就是2倍`。

```java
Map hashMap=new HashMap(3);
hashMap.put("小林",666);
hashMap.put("小马",777);
```

在HashMap中数据结构就应该只存了一个Node，其中这个`Node[]数组的index`是通过key对象的hash值取模得出的，源码公式采用位运算`(length-1)&hash`取模然后放置到Node数组的`Node[(length-1)&hash]`。

如果**小林和小马的hash值可能相同(`发生哈希碰撞`)**，则将会在小林的出追加一个结点，形成了链表。

<img src="https://img-blog.csdnimg.cn/2021032617594616.png#pic_center">

<img src="https://img-blog.csdnimg.cn/20210326180030481.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI2MTI1ODY1,size_16,color_FFFFFF,t_70#pic_center">

----------

#### 为什么Java8要使用尾插法呢？

在Java7中Map的链表新增还是头插法，而在Java8中使用的就是尾插法了，其原因有两个：

- 头插法会造成死链
- Java7考虑是热点数据可能会更早的用到，**如果发生链表迁移，头插法还是会扰乱插入的顺序**

```java
/**
     * 默认初始化容量，值为16，必须是2的n次方
     */
static final int DEFAULT_INITIAL_CAPACITY = 1 << 4; // aka 16

/**
     * 默认加载因子
     * 当size>capacity*DEFAULT_LOAD_FACTOR时则进行resize(扩容)
     */
static final float DEFAULT_LOAD_FACTOR = 0.75f;  

/**
     * 链表需要转红黑树时的长度。
     * 此时未必会做换红黑树的操作，需要结合MIN_TREEIFY_CAPACITY，即链表长度达到8且容量达到64时，才会做红黑树的转换；
     * 否则，进行扩容操作。
     */
static final int TREEIFY_THRESHOLD = 8;    

/**
     * 红黑树转链表时的元素个数
     */
static final int UNTREEIFY_THRESHOLD = 6;


/**
     * 链表树形化，最小数组容量阈值
     * 数组容量超过这个，链表将会树形化
     */
static final int MIN_TREEIFY_CAPACITY = 64;        
```

---------------

无论是`LinkedMap`还是`HashMap`内部都离不开Node节点、这是我们数据存储的最基本结构，`在Java7叫Entry，在Java8叫Node`，其本质都是Map.Entry的实现，但其内部结构却不太一样，可能是HashMap中是链表，LinkedMap中是双向链表，在TreeMap中可以排序，又可以是红黑树。

```java
/**
     * 链表结点，实现Map.Entry接口
     */
static class Node<K,V> implements Map.Entry<K,V> {
    final int hash;
    final K key;
    V value;
    Node<K,V> next;

    // ... 
}

/**
     * LinkedHashMap中元素的结点类型
     */
static class Entry<K,V> extends HashMap.Node<K,V> {
    Entry<K,V> before, after;
    Entry(int hash, K key, V value, Node<K,V> next) {
        super(hash, key, value, next);
    }
}    

/**
     * 红黑树结点，继承了LinkedHashMap.Entry，间接继承了HashMap.Node，所以也具有链表的性质。
     * 实际上该结点类型既可以作为红黑树结点，又可以作为双向链表结点。
     */
static final class TreeNode<K,V> extends LinkedHashMap.Entry<K,V> {
    TreeNode<K,V> parent;  // red-black tree links
    TreeNode<K,V> left;
    TreeNode<K,V> right;
    TreeNode<K,V> prev;    // needed to unlink next upon deletion
    boolean red;

    // ...
}    
```

```java
//put操作
public V put(K key, V value) {
    return putVal(hash(key), key, value, false, true);
}

/**
     * Implements Map.put and related methods
     *
     * @param hash 键对象的hash值
     * @param key 键对象
     * @param value 键值对中的值对象，主要就是用于存储这个对象
     * @param onlyIfAbsent 如果同样的键对象是否替换当前已存在的值对象
     * @param evict if false, the table is in creation mode.
     * @return 如果是替换的话则返回oldValue，否则返回null
     */
final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
               boolean evict) {
    Node<K,V>[] tab; Node<K,V> p; int n, i;
    if ((tab = table) == null || (n = tab.length) == 0)
        n = (tab = resize()).length;
    if ((p = tab[i = (n - 1) & hash]) == null)
        tab[i] = newNode(hash, key, value, null);
    else {
        Node<K,V> e; K k;
        if (p.hash == hash &&
            ((k = p.key) == key || (key != null && key.equals(k))))
            e = p;
        else if (p instanceof TreeNode)
            e = ((TreeNode<K,V>)p).putTreeVal(this, tab, hash, key, value);
        else {
            for (int binCount = 0; ; ++binCount) {
                if ((e = p.next) == null) {
                    p.next = newNode(hash, key, value, null);
                    if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                        treeifyBin(tab, hash);
                    break;
                }
                if (e.hash == hash &&
                    ((k = e.key) == key || (key != null && key.equals(k))))
                    break;
                p = e;
            }
        }
        if (e != null) { // existing mapping for key
            V oldValue = e.value;
            if (!onlyIfAbsent || oldValue == null)
                e.value = value;
            afterNodeAccess(e);
            return oldValue;
        }
    }
    ++modCount;
    if (++size > threshold)
        resize();
    afterNodeInsertion(evict);
    return null;
}
```

```java
/**
    * treeifyBin树形化链表
     * 当达到两个阈值后，替换所有数组上的链表节点
     */
final void treeifyBin(Node<K,V>[] tab, int hash) {
    int n, index; Node<K,V> e;
    if (tab == null || (n = tab.length) < MIN_TREEIFY_CAPACITY)
        resize();
    else if ((e = tab[index = (n - 1) & hash]) != null) {
        TreeNode<K,V> hd = null, tl = null;
        do {
            TreeNode<K,V> p = replacementTreeNode(e, null);
            if (tl == null)
                hd = p;
            else {
                p.prev = tl;
                tl.next = p;
            }
            tl = p;
        } while ((e = e.next) != null);
        if ((tab[index] = hd) != null)
            hd.treeify(tab);
    }
}
```

--------

#### resize扩容

resize扩容：Node数组的容量是优先的，当数据多次插入达到一定数量就会进行扩容`resize()`，当Map的长度大于`capacity * load factor`，如容量为16时，当Map中节点数量超过12则需要进行扩容。

1. 判断旧数组的容量是否大于等于最大容量`1<<30`，将新**数组容量**和**阈值**参数扩大2倍

```java
Node<K,V>[] oldTab = table;
//判断当前数组的长度，如果是0则新建数组，容量和负载因子都是默认值16*0.75
int oldCap = (oldTab == null) ? 0 : oldTab.length;
int oldThr = threshold;
int newCap, newThr = 0;
//判断当前数组是否有容量，且不超过最大容量1<<30
if (oldCap > 0) {
    if (oldCap >= MAXIMUM_CAPACITY) {
        threshold = Integer.MAX_VALUE;
        return oldTab;
    }
    //若有容量，并且新扩容的容量值没有超过最大容量值，则将阈值和容量扩大二倍，也就是容量总是2的幂次方
    else if ((newCap = oldCap << 1) < MAXIMUM_CAPACITY &&
             oldCap >= DEFAULT_INITIAL_CAPACITY)
        newThr = oldThr << 1; // double threshold
}
else if (oldThr > 0) // initial capacity was placed in threshold
    newCap = oldThr;
else {               // zero initial threshold signifies using defaults
    //如果阈值为0则使用默认值
    newCap = DEFAULT_INITIAL_CAPACITY;
    newThr = (int)(DEFAULT_LOAD_FACTOR * DEFAULT_INITIAL_CAPACITY);
}
if (newThr == 0) {
    float ft = (float)newCap * loadFactor;
    newThr = (newCap < MAXIMUM_CAPACITY && ft < (float)MAXIMUM_CAPACITY ?
              (int)ft : Integer.MAX_VALUE);
}
threshold = newThr;
```

2. 根据新阈值创建新数组

```java
//根据新容量参数，创建一个新数组
Node<K,V>[] newTab = (Node<K,V>[])new Node[newCap];
//Node数组引用指向新数组
table = newTab;
if (oldTab != null) {
    for (int j = 0; j < oldCap; ++j) {
        Node<K,V> e;
        if ((e = oldTab[j]) != null) {
            oldTab[j] = null;
            if (e.next == null)// 表示j下标处只有一个结点
                //根据新数组的容量值，取模计算在新数组中的位置
                newTab[e.hash & (newCap - 1)] = e;
            else if (e instanceof TreeNode)
                // 将红黑树分解为两个双向链表，如果双向链表长度大于6，则分解出来的双向链表转换为红黑树。
                // 然后将双向链表或红黑树放入新table的相应下标处
                ((TreeNode<K,V>)e).split(this, newTab, j, oldCap);
            else { // preserve order
                //将原链表拆分为两个（至少一个）链表，并且维持元素在原链表中的相对顺序
                Node<K,V> loHead = null, loTail = null;
                Node<K,V> hiHead = null, hiTail = null;
                Node<K,V> next;
                do {
                    next = e.next;
                    if ((e.hash & oldCap) == 0) {
                        if (loTail == null)
                            loHead = e;
                        else
                            loTail.next = e;
                        loTail = e;
                    }
                    else {
                        if (hiTail == null)
                            hiHead = e;
                        else
                            hiTail.next = e;
                        hiTail = e;
                    }
                } while ((e = next) != null);
                if (loTail != null) {
                    loTail.next = null;
                    // 将新的链表放入新table的相应下标处
                    newTab[j] = loHead;
                }
                if (hiTail != null) {
                    hiTail.next = null;
                    newTab[j + oldCap] = hiHead;
                }
            }
        }
    }
}
return newTab;
```

---------------

#### get获取Value对象（用友Java）

==返回key关联的value值，如果key不存在，返回null==。

==计算key的hash值，根据hash值计算key在table数组中的位置==

- 如果该位置不为null，则比较key和其hash值是否相等；
- 如果相等，则返回该结点；
- 否则
  - 如果结点是红黑树，则从红黑树中查找该key对应的结点
  - 否则，就是从链表中查找该key对应的结点
  - 否则，返回null

1. 根据1获取结点的value值，或者返回null

```java
    public V get(Object key) {
        Node<K,V> e;
        return (e = getNode(hash(key), key)) == null ? null : e.value;
    }

    /**
     * 实现了Map接口的get方法
     */
    final Node<K,V> getNode(int hash, Object key) {
        Node<K,V>[] tab; Node<K,V> first, e; int n; K k;
        if ((tab = table) != null && (n = tab.length) > 0 &&
            //哈希值取模后在数组中存在至少一个节点，在该index位置有一个Node存在
            (first = tab[(n - 1) & hash]) != null) {
            if (first.hash == hash && // always check first node
                ((k = first.key) == key || (key != null && key.equals(k))))
                return first;
            if ((e = first.next) != null) {
                //如果链表的头结点不是目标元素，则判断是不是树形化的节点
                if (first instanceof TreeNode)
                    return ((TreeNode<K,V>)first).getTreeNode(hash, key);
                do {
                    //遍历这个链表，一直到找到key和hash值都相同的节点
                    if (e.hash == hash &&
                        ((k = e.key) == key || (key != null && key.equals(k))))
                        return e;
                } while ((e = e.next) != null);
            }
        }
        return null;
    }
```

#### remove删除key对象

删除key，返回key关联的value；如果key不存在，返回null

1. 查找key对应的结点
2. 从链表或者红黑树删除该结点

```java
    public V remove(Object key) {
        Node<K,V> e;
        return (e = removeNode(hash(key), key, null, false, true)) == null ?
            null : e.value;
    }

    /**
     * 实现了Map接口中remove方法
     */
    final Node<K,V> removeNode(int hash, Object key, Object value,
                               boolean matchValue, boolean movable) {
        Node<K,V>[] tab; Node<K,V> p; int n, index;
        if ((tab = table) != null && (n = tab.length) > 0 &&
            (p = tab[index = (n - 1) & hash]) != null) {
            Node<K,V> node = null, e; K k; V v;
            if (p.hash == hash &&
                ((k = p.key) == key || (key != null && key.equals(k))))
                node = p;
            else if ((e = p.next) != null) {
                if (p instanceof TreeNode)
                    node = ((TreeNode<K,V>)p).getTreeNode(hash, key);
                else {
                    do {
                        if (e.hash == hash &&
                            ((k = e.key) == key ||
                             (key != null && key.equals(k)))) {
                            node = e;
                            break;
                        }
                        p = e;
                    } while ((e = e.next) != null);
                }
            }
            if (node != null && (!matchValue || (v = node.value) == value ||
                                 (value != null && value.equals(v)))) {
                if (node instanceof TreeNode)
                    ((TreeNode<K,V>)node).removeTreeNode(this, tab, movable);
                else if (node == p)
                    tab[index] = node.next;
                else
                    p.next = node.next;
                ++modCount;
                --size;
                afterNodeRemoval(node);
                return node;
            }
        }
        return null;
    }
```

### Java中switch()括号中不能放什么类型？

结论：java中switch()括号中不能放“long”，“float”，“double”，“boolean”类型的数据，可以使用`“byte”，“short”，“char”，“int”，“枚举类型”，“String”`类型的数据。

1. 在JDK1.5之前，switch只支持byte、short、char、int类型。

2. 在JDK1.5中，增加了枚举类与byte、short、char、int的包装类，对四个包装类的支持是因为java编译器在底层手动进行拆箱，而对枚举类的支持是因为枚举类有一个ordinal方法，该方法实际上是一个int类型的数值。

3. 在JDK1.7中，支持String类型，但实际上String类型有一个hashCode算法，结果也是int类型。而byte、short、char类型可以在不损失精度的情况下向上转型成int类型。所以总的来说，可以认为switch中只支持int。

所以支持的有：char、byte、short、int、Character、Byte、Short、Integer、枚举和String。

在switch语句中，表达式的值不能是null，否则会在运行时抛出NullPointerException。在case子句中也不能使用null，否则会出现编译错误。



### Linkedlist 是单向的还是双向的？ArrayList为什么线程不安全？

**双向链表**

```java
//ArrayList
public boolean add(E e) {
    ensureCapacityInternal(size + 1);  // Increments modCount!!
    //ensureCapacityInternal()这个方法的作用就是判断如果将当前的新元素加到列表后面，列表的elementData数组的大小是否满足，如果size + 1的这个需求长度大于了elementData这个数组的长度，那么就要对这个数组进行扩容
    elementData[size++] = e;
    return true;
}
//Vector
public synchronized void addElement(E obj) {
    modCount++;
    ensureCapacityHelper(elementCount + 1);
    elementData[elementCount++] = obj;
}
```

**如何解决ArrayList线程不安全？**

1. 使用Vector代替ArrayList（不推荐）
2. 使用Collections.synchronizedList(new ArrayList<>())来保证list是同步线程安全(不建议)
3. <font color='red'>使用基于写时复制的CopyOnWriteArrayList</font>，CopyOnWriteArrayList 底层实现添加的原理是<font color='blue'>先copy出一个容器(可以简称副本)，再往新的容器里添加这个新的数据，最后把新的容器的引用地址赋值给了之前那个旧的的容器地址，但是在添加这个数据的期间，其他线程如果要去读取数据，仍然是读取到旧的容器里的数据</font>。

### Java序列化和反序列化

**把对象转换为字节序列的过程称为对象的序列化**。

**把字节序列恢复为对象的过程称为对象的反序列化**。

对象的序列化主要有两种用途：

1） 把对象的字节序列永久地保存到硬盘上，通常存放在一个文件中；

2） 在网络上传送对象的字节序列。

**应用场景：**

在很多应用中，需要对某些对象进行序列化，让它们离开内存空间，入住物理硬盘，以便长期保存。比如最常见的是Web服务器中的Session对象，当有 10万用户并发访问，就有可能出现10万个Session对象，内存可能吃不消，于是Web容器就会把一些session先序列化到硬盘中，等要用了，再把保存在硬盘中的对象还原到内存中。

当两个进程在进行远程通信时，彼此可以发送各种类型的数据。无论是何种类型的数据，都会以二进制序列的形式在网络上传送。发送方需要把这个Java对象转换为字节序列，才能在网络上传送；接收方则需要把字节序列再恢复为Java对象。

### Java 反射class.forName()加载类和使用classLoader 加载类的区别？

Class.forName 加载类是将类进行了初始化，而ClassLoader 的loadClass 并没有对类进行初始化，只是把类加载到了虚拟机中

### 为什么HashMap中链表长度超过8会转换成红黑树？

红黑树插入为O(lgn),查询为O(lgn)，链表插入为O(1)，查询为O(n)。个数少时，插入删除成本高，用链表；个数多时，查询成本高，用红黑树。需要定一个值，比这个值大就转红黑树，比这个值小就转链表，而且要避免频繁的转换。<font color='blue'>根据泊松分布，在负载因子0.75（HashMap默认）的情况下，单个hash槽内元素个数为8的概率小于百万分之一，将7作为一个分水岭，等于7时不做转换，大于等于8才转红黑树，小于等于6才转链表</font>。

中间有个差值7可以防止链表和树之间频繁的转换。假设一下，如果设计成链表个数超过8则链表转换成树结构，链表个数小于8则树结构转换成链表，如果一个HashMap不停的插入、删除元素，链表个数在8左右徘徊，就会频繁的发生树转链表、链表转树，效率会很低。

### 准备用HashMap存1w条数据，构造时传10000会触发扩容吗？

HashMap 并不是直接使用外部传递进来的 `initialCapacity`，而是经过了 `tableSizeFor()` 方法的处理，再赋值到 `threshole` 上

```java
static final int tableSizeFor(int cap) {
  int n = cap - 1;
  n |= n >>> 1;
  n |= n >>> 2;
  n |= n >>> 4;
  n |= n >>> 8;
  n |= n >>> 16;
  return (n < 0) ? 1 : (n >= MAXIMUM_CAPACITY) ? MAXIMUM_CAPACITY : n + 1;
}
```

在 `tableSizeFor()` 方法中，通过逐步位运算，就可以让返回值，保持在 2 的 N 次幂。以方便在扩容的时候，快速计算数据在扩容后的新表中的位置。当我们从外部传递进来 1w 时，实际上经过 `tableSizeFor()` 方法处理之后，就会变成 2 的 14 次幂 16384，再算上负载因子 0.75f，实际在不触发扩容的前提下，可存储的数据容量是 12288（16384 * 0.75f）。

----

当我们把初始容量，调整到 1000 时，虽然 HashMap 初始容量指定为 1000，会被调整为 1024，但是它只是表示 table 数组为 1024，扩容的重要依据扩容阈值会在 `resize()` 中调整为 768（1024 * 0.75），它是不足以承载 1000 条数据的，最终在存够 1k 条数据之前，还会触发一次动态扩容。

### 如何遍历HashMap？（用友Java）

1. **使用Iterator遍历HashMap EntrySet**

```java
public class IterateHashMapExample {  
    public static void main(String[] args) {  
        // 1. 使用 Iterator 遍历 HashMap EntrySet  
        Map < Integer, String > coursesMap = new HashMap <>();  
        coursesMap.put(1, "C");  
        coursesMap.put(2, "C++");  
        coursesMap.put(3, "Java");  
        coursesMap.put(4, "Spring Framework");  
        coursesMap.put(5, "Hibernate ORM framework");  
        Iterator < Entry < Integer, String >> iterator = 	
            					coursesMap.entrySet().iterator();  
        while (iterator.hasNext()) {  
            Entry < Integer, String > entry = iterator.next();  
            System.out.println(entry.getKey());  
            System.out.println(entry.getValue());  
        }  
    }  
}
```

2. **使用Iterator遍历HashMap KeySet**

```java
public class IterateHashMapExample {  
    public static void main(String[] args) {  
        Map < Integer, String > coursesMap = new HashMap < Integer, String > ();  
        coursesMap.put(1, "C");  
        coursesMap.put(2, "C++");  
        coursesMap.put(3, "Java");  
        coursesMap.put(4, "Spring Framework");  
        coursesMap.put(5, "Hibernate ORM framework");  
        // 2. 使用 Iterator 遍历 HashMap KeySet  
        Iterator < Integer > iterator = coursesMap.keySet().iterator();  
        while (iterator.hasNext()) {  
            Integer key = iterator.next();  
            System.out.println(key);  
            System.out.println(coursesMap.get(key));  
        }  
    }  
}
```

3. **for-each循环遍历HashMap**

```java
public class IterateHashMapExample {  
    public static void main(String[] args) {  
        Map < Integer, String > coursesMap = new HashMap < Integer, String > ();  
        coursesMap.put(1, "C");  
        coursesMap.put(2, "C++");  
        coursesMap.put(3, "Java");  
        coursesMap.put(4, "Spring Framework");  
        coursesMap.put(5, "Hibernate ORM framework");  
        // 3. 使用 For-each 循环遍历 HashMap  
        for (Map.Entry < Integer, String > entry: coursesMap.entrySet()) {  
            System.out.println(entry.getKey());  
            System.out.println(entry.getValue());  
        }  
    }  
}
```

4. **Lambda表达式遍历HashMap**

```java
public class IterateHashMapExample {  
    public static void main(String[] args) {  
        Map < Integer, String > coursesMap = new HashMap < Integer, String > ();  
        coursesMap.put(1, "C");  
        coursesMap.put(2, "C++");  
        coursesMap.put(3, "Java");  
        coursesMap.put(4, "Spring Framework");  
        coursesMap.put(5, "Hibernate ORM framework");  
        // 4. 使用 Lambda 表达式遍历 HashMap  
        coursesMap.forEach((key, value) -> {  
            System.out.println(key);  
            System.out.println(value);  
        });  
    }  
}
```

5. **Stream API遍历HashMap**

```java
public class IterateHashMapExample {  
    public static void main(String[] args) {  
        Map < Integer, String > coursesMap = new HashMap < Integer, String > ();  
        coursesMap.put(1, "C");  
        coursesMap.put(2, "C++");  
        coursesMap.put(3, "Java");  
        coursesMap.put(4, "Spring Framework");  
        coursesMap.put(5, "Hibernate ORM framework");  
        // 5. 使用 Stream API 遍历 HashMap  
        coursesMap.entrySet().stream().forEach((entry) - > {  
            System.out.println(entry.getKey());  
            System.out.println(entry.getValue());  
        });  
    }  
}
```

### ConcurentHashMap详解（用友Java）？

JDK1.7中的ConcurrentHashMap 是由 `Segment 数组结构`和` HashEntry 数组结构`组成，即
ConcurrentHashMap 把哈希桶切分成小数组（Segment ），每个小数组有 n 个 HashEntry 组成。其中，`Segment `继承了` ReentrantLock`，所以 Segment 是一种可重入锁，扮演锁的角色；`HashEntry用于存储键值对数据`。首先将数据分为一段一段的存储，然后给每一段数据配一把锁，当一个线程占用锁访问其中一个段数据时，其他段的数据也能被其他线程访问，能够实现真正的并发访问。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1.7concurrenthashmap.png">

JDK1.8在数据结构上，JDK1.8中的ConcurrentHashMap选择了与 HashMap 相同的`数组+链表+红黑树`结构；在锁的实现上，抛弃了原有Segment 分段锁，采用`CAS + synchronized`实现更加低粒度的锁。将锁的级别控制在了更细粒度的哈希桶元素级别，也就是说只需要`锁住这个链表头结点（红黑树的根节点）`，就不会影响其他的哈希桶元素的读写，大大提高了并发度。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1.8concurrenthashmap.png">

#### concurrenthashmap的put过程？

<font color='blue'>先来看JDK1.7，首先，会尝试获取锁，如果获取失败，利用自旋获取锁；如果自旋重试的次数超过64 次，则改为阻塞获取锁。</font>

**获取到锁后：**

1. 将当前 Segment 中的 table 通过 key 的 hashcode 定位到 HashEntry
2. 遍历该 HashEntry，如果不为空则判断传入的 key 和当前遍历的 key
value。
3. 不为空则需要新建一个 HashEntry 并加入到 Segment 中，同时会先判断是否需要扩容
4. 释放 Segment 的锁。

<font color='blue'>再来看JDK1.8，大致可以分为以下步骤：</font>

1. 根据 key 计算出 hash值。
2. 判断是否需要进行初始化。
3. 定位到 Node，拿到首节点 f，判断首节点 f：
    - 如果为  null  ，则通过cas的方式尝试添加。
    - 如果为` f.hash = MOVED = -1 `，说明其他线程在扩容，参与一起扩容
    - 如果都不满足 ，synchronized 锁住 f 节点，判断是链表还是红黑树
4. 当在链表长度达到8的时候，数组扩容或者将链表转换为红黑树。

#### concurrenthashmap的get方法是否需要加锁？

get 方法不需要加锁。因为 Node 的元素 val 和指针 next 是用 volatile 修饰的，在多线程环境下线程A
修改结点的val或者新增节点的时候是对线程B可见的。

```java
static class Node<K,V> implements Map.Entry<K,V> {
    final int hash;
    final K key;
    //可以看到这些都用了volatile修饰
    volatile V val;
    volatile Node<K,V> next;
}
```

### String str = new String(“Hello“)；创建了几个对象？分别存在哪儿？

<font color='blue'>这里主要分两种情况：</font>

- **如果String的字符串常量池中有Hello这个对象，那么就只创建了一个对象**——>原因：因为字符串常量池中有Hello，`字符串会用已有的Hello对象，所有不会再创建Hello这个对象了`，只会创建一个new String对象
- **如果String的字符串常量池中没有Hello这个对象，那么就创建了两个对象**——>原因：只要是`new了就一定会创建一个新对象`，`而字符串常量池中没有Hello，所以会在字符串常量池中创建一个Hello对象`

如果是String str = new String(“java“)；就只会创建一个对象

### 哈希冲突解决方法？

#### 开放地址法

1. **线性探测：**按顺序决定值时，如果某数据的值已经存在，则在原来值的基础上往后加一个单位，直至不发生哈希冲突。　
2. **再平方法：**按顺序决定值时，如果某数据的值已经存在，则在原来值的基础上先加1的平方个单位，若仍然存在则减1的平方个单位。随之是2的平方，3的平方等等。直至不发生哈希冲突。
3. **伪随机探测：**按顺序决定值时，如果某数据已经存在，通过随机函数随机生成一个数，在原来值的基础上加上随机数，直至不发生哈希冲突。

#### 链式地址法（HashMap的哈希冲突解决方法）

　对于相同的值，使用链表进行连接。使用数组存储每一个链表。

　　**优点：**

- 拉链法处理冲突简单，且无堆积现象，即非同义词决不会发生冲突，因此平均查找长度较短；
- 由于拉链法中各链表上的结点空间是动态申请的，故它更适合于造表前无法确定表长的情况；
- 开放定址法为减少冲突，要求装填因子α较小，故当结点规模较大时会浪费很多空间。而拉链法中可取α≥1，且结点较大时，拉链法中增加的指针域可忽略不计，因此节省空间；
- 在用拉链法构造的散列表中，删除结点的操作易于实现。只要简单地删去链表上相应的结点即可。
  **缺点：**
- 指针占用较大空间时，会造成空间浪费，若空间用于增大散列表规模进而提高开放地址法的效率。

#### 建立公共溢出区

建立公共溢出区存储所有哈希冲突的数据。

#### 再哈希法

对于冲突的哈希值再次进行哈希处理，直至没有哈希冲突。

### HashMap的长度为什么要是2的n次方？

HashMap为了存取高效，要尽量较少碰撞，就是要尽量把数据分配均匀，每个链表长度大致相同。

`hash % length == hash & (length - 1)`，前提是length是2的n次方

为什么这样能均匀分布减少碰撞呢？2的n次方实际就是1后面n个0，2的n次方-1 实际就是n个1。

例如长度为9时候，3&(9-1)=0 2&(9-1)=0 ，都在0上，碰撞了；

例如长度为8时候，3&(8-1)=3 2&(8-1)=2 ，不同位置上，不碰撞；其实就是按位“与”的时候，每一位都能 &1 ，也就是和1111……1111111进行与运算

### HashMap的put过程（用友Java）？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/20191214222552803.png">

当我们put的时候，首先计算 `key`的`hash`值，这里调用了 `hash`方法，`hash`方法实际是让`key.hashCode()`与`key.hashCode()>>>16`进行异或操作，高16bit补0，一个数和0异或不变，所以 hash 函数大概的作用就是：高16bit不变，低16bit和高16bit做了一个异或，目的是减少碰撞。按照函数注释，因为bucket数组大小是2的幂，计算下标`index = (table.length - 1) & hash`，如果不做 hash 处理，相当于散列生效的只有几个低 bit 位，为了减少散列的碰撞，设计者综合考虑了速度、作用、质量之后，使用高16bit和低16bit异或来简单处理减少碰撞，而且JDK8中用了复杂度 O（logn）的树结构来提升碰撞下的性能。

以JDK1.8为例，简要流程如下：
1. 首先根据 key 的值计算 hash 值，找到该元素在数组中存储的下标；
2. 如果数组是空的，则调用 resize 进行初始化；
3. 如果没有哈希冲突直接放在对应的数组下标里；
4. 如果冲突了，且 key 已经存在，就覆盖掉 value；
5. 如果冲突后，发现该节点是红黑树，就将这个节点挂在树上；
6. 如果冲突后是链表，判断该链表是否大于 8 ，如果大于 8 并且数组容量小于 64，就进行扩容；如
果链表节点大于 8 并且数组的容量大于 64，则将这个结构转换为红黑树；否则，链表插入键值
对，若 key 存在，就覆盖掉 value

### HashMap和Hashtable的区别？（用友Java）

1. **线程是否安全：** `HashMap 是⾮线程安全的， HashTable 是线程安全的`，因为 HashTable 内部的⽅法基本都经过 `synchronized `修饰。（如果你要保证线程安全的话就使⽤ ConcurrentHashMap 吧！）
2. **效率：**因为线程安全的问题， HashMap 要⽐ HashTable 效率⾼⼀点。另外， HashTable 基本被淘汰，不要在代码中使⽤它
3. **对Null Key和Null Value的支持：**`HashMap 可以存储 null 的 key 和 value，但 null 作为键只能有⼀个`，null 作为值可以有多个；`HashTable 不允许有 null 键和 null 值`，否则会抛出 NullPointerException 
4. **初始容量大小和每次扩容大小不同：**① 创建时如果不指定容量初始值， Hashtable 默认的初始⼤⼩为 `11`，之后每次扩充，容量变为原来的 `2n+1`。 HashMap 默认的初始化⼤⼩为` 16`。之后每次扩充，容量变为原来的` 2 倍`。② 创建时如果给定了容量初始值，那么 Hashtable 会直接使⽤你给定的⼤⼩，⽽ HashMap 会将其扩充为` 2 的幂次⽅⼤⼩`（ HashMap 中的 tableSizeFor() ⽅法保证）。也就是说 HashMap 总是使⽤ 2 的幂作为哈希表的⼤⼩
5. **底层数据结构：**JDK1.8 以后的 HashMap 在解决哈希冲突时有了较⼤的变化，当链表⻓度⼤于阈值（默认为 8）（`将链表转换成红⿊树`前会判断，如果当前数组的⻓度⼩于 64，那么会选择先进⾏`数组扩容`，⽽不是转换为红⿊树）时，将链表转化为红⿊树，以减少搜索时间。Hashtable 没有这样的机制

### 抽象类和接口区别？分别用于哪些场景？（用友Java）

#### 区别

1. 接⼝的⽅法默认是 `public `，所有⽅法在接⼝中不能有实现(Java 8 开始接⼝⽅法可以有默认
实现`default`关键字），⽽抽象类可以有⾮抽象的⽅法。
2. 接⼝中除了 `static` 、 `final `变量，不能有其他变量，⽽抽象类中则不⼀定。
3. ⼀个类可以实现多个接⼝，但只能实现⼀个抽象类。接⼝⾃⼰本身可以通过 `extends `关键
字扩展多个接⼝。
4. 接⼝⽅法默认修饰符是 `public` ，抽象⽅法可以有` public `、 `protected` 和` default `这些修饰
符（==抽象⽅法就是为了被重写所以不能使⽤ private 关键字修饰！==）。
5. 从设计层⾯来说，抽象是对类的抽象，是⼀种模板设计，⽽接⼝是对⾏为的抽象，是⼀种⾏
为的规范。

> 1. 在 JDK8 中，接⼝也可以定义静态⽅法，可以直接⽤接⼝名调⽤。实现类和实现是不
> 可以调⽤的。如果同时实现两个接⼝，接⼝中定义了⼀样的默认⽅法，则必须重写，不
> 然会报错。
> 2. jdk9 的接⼝被允许定义私有⽅法 。

#### 使用场景

1. **抽象类的使用场景**

> 既想约束子类具有共同的行为，又想拥有缺省方法，又能拥有实例变量
>
> 如，模板设计模式，使得子类在不改变算法结构的情况下，重新定义算法中某些步骤的具体实现

2. **接口的使用场景**

> 约束多个实现类具有统一的行为，但是不在乎每个实现类如何具体实现
>
> 如果想实现多重继承，那么必须使用接口。由于Java不支持多继承，即一个类只能有一个超类。但是，可以实现多个接口，因此可以使用接口来解决它。

### 访问修饰符public、private、protected以及不写的区别（用友Java）？

- <font color='red'>default (即默认，什么也不写）</font>: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变
  量、方法
- <font color='red'>private </font>: 在同一类内可见。使用对象：变量、方法。注意：不能修饰类（外部类）
- <font color='red'>public </font>: 对所有类可见。使用对象：类、接口、变量、方法
- <font color='red'>protected</font> : 对同一包内的类和所有子类可见。使用对象：变量、方法。注意：不能修饰类（外
  部类）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/xiushifu.png">

### throw和throws区别？

**throw：用于在方法内部抛出异常对象**

1. `throw` 用在方法体内，表示抛出异常，由方法体内的语句处理； 
2. `throw` 是具体向外抛出异常的动作，所以抛出的是一个异常实例，执行 `throw` 一定是抛出了某种异常；

**throws：用于在方法签名上声明该方法所要抛出的异常**

1. `throws` 语句使用在方法声明后，表示若抛出异常，则由该方法的调用者来进行异常的处理； 
2. `throws` 主要是声明这个方法抛出某种类型的异常，让它的使用者要知道需要捕获的异常的类型； 
3. `throws` 表示出现异常的一种可能性，并非一定发生该种异常；

### final、finally、finalize 的区别（用友Java）？

`final` 用于修饰类、方法、变量，修饰类时表示类不能被继承；修饰方法时表示方法不能别重写，但是能够被重载；修饰变量时表示该变量是一个常量无法被重写赋值；

`finally` 一般作用于 `try...catch` 代码块，处理异常时，通常将必须要执行的代码放在 `finally` 代码块中，表示无论是否出现异常，此代码块均执行，一般用来存放一些关闭资源的代码；

`finalize` 是一个方法，属于 `Object` 类，Java 允许用 `finalize()` 方法在垃圾回收器将对象从内存中清除前做一些必要的清理工作；

### 什么是深拷贝和浅拷贝？

**浅拷贝**是按位拷贝对象，它会创建一个新对象，这个对象有着原始对象属性值的一份精确拷贝。如果属性是基本类型，拷贝的就是基本类型的值；如果属性是内存地址（引用类型），拷贝的就是内存地址 ，因此如果其中一个对象改变了这个地址，就会影响到另一个对象。即默认拷贝构造函数只是对对象进行浅拷贝复制(逐个成员依次拷贝)，即只复制对象空间而不复制资源。

**深拷贝**，在拷贝引用类型成员变量时，为引用类型的数据成员另辟了一个独立的内存空间，实现真正内容上的拷贝。

> <font color='red'>浅拷贝：</font>
>
> - 对于基本数据类型的成员对象，因为基础数据类型是值传递的，所以是直接将属性值赋值给新的对象。基础类型的拷贝，其中一个对象修改该值，不会影响另外一个。
> - 对于引用类型，比如数组或者类对象，因为引用类型是引用传递，所以浅拷贝只是把内存地址赋值给了成员变量，它们指向了同一内存空间。改变其中一个，会对另外一个也产生影响。
>
> ```java
> /**
> *实现对象拷贝的类，需要实现Cloneable接口并重写clone()方法
> */
> @Override
> public Object clone() {
>     //浅拷贝
>     try {
>         // 直接调用父类的clone()方法
>         return super.clone();
>     } catch (CloneNotSupportedException e) {
>         return null;
>     }
> }
> ```

> <font color='red'>深拷贝：</font>
>
> - 对于基本数据类型的成员对象，因为基础数据类型是值传递的，所以是直接将属性值赋值给新的对象。基础类型的拷贝，其中一个对象修改该值，不会影响另外一个（和浅拷贝一样）
> - 对于引用类型，比如数组或者类对象，深拷贝会新建一个对象空间，然后拷贝里面的内容，所以它们指向了不同的内存空间。改变其中一个，不会对另外一个也产生影响
> - **对于有多层对象的，每个对象都需要实现 `Cloneable` 并重写 `clone()` 方法，进而实现了对象的串行层层拷贝**
> - 深拷贝相比于浅拷贝速度较慢并且花销较大
>
> ```java
> /**
> *Subject类需要实现Cloneable接口并重写clone()方法
> */
> @Override
> protected Object clone() throws CloneNotSupportedException {
>     //Subject 如果也有引用类型的成员属性，也应该和 Student 类一样实现
>     return super.clone();
> }
> 
> /**
> *Student()类实现Cloneable接口并重写clone()方法
> */
> @Override
> public Object clone() {
>     //深拷贝
>     try {
>         // 直接调用父类的clone()方法
>         Student student = (Student) super.clone();
>         student.subject = (Subject) subject.clone();
>         return student;
>     } catch (CloneNotSupportedException e) {
>         return null;
>     }
> }
> ```

### static可以修饰的类有哪些？

`Java中static方法不能被覆盖，因为方法覆盖是基于运行时动态绑定的，而static方法是编译时静态绑定
的。`static方法跟类的任何实例都不相关，所以概念上不适用。

- static静态方法不能引用非静态资源

- static静态方法里面能引用静态资源

- 非静态方法里面能引用静态资源

> **什么时候用到静态变量？**
>
> - 当数据是共享的，对象不需要修改，只需要使用，不用存储在对象中，就可以定义为静态的
> - 静态成员属于类，被这个类的所有实例所共享
> - 如果类对象中有需要共享的成员变量，则可以定义为静态变量
>
> **什么时候用到静态内部类？**
>
> - 只有内部类才可以被static修饰的内部类可以直接作为一个普通类来使用，而不需实例一个外部类
>
> **什么时候用到静态方法？**
>
> - 无须每次都要new实例化，因为在编译后就已经分配好了内存，通过类名.方法来调用
> - 如果方法内部没有访问到实例数据，则可以定义为静态方法
>
> **什么时候用到静态代码块？**
>
> - 当jvm加载类时，静态代码块的内容会先于其他代码块执行，且只会被执行一次
> - 可用于给类初始化

static修饰的类只能为<font color='red'>内部类</font>，普通类无法用static关键字修饰。static修饰的内部类相当于一个普通的类，访问方式为（new 外部类名.内部类的方法() ）

```java
public class OuterClass {
    public static class InnerClass{
        InnerClass(){
            System.out.println("===== 我是一个内部类'InnerClass'=====");
        }
    }
}
public class TestStaticClass {
    public static void main(String[] args) {
        // 不需要new一个InnerClass
        new OuterClass.InnerClass();
    }
}
//通内部类的访问方式为 （外部类对象.new 内部类方法()）
```

**static关键字加载顺序**

```java
public class Father {
    static int i = 10;//先加载
    static {
        System.out.println("初始化父类的静态块...");
    }//后加载
    public Father() {
        System.out.println("初始化父类的构造方法...");
    }
    public static  void  speak(){
        System.out.println("静态方法...");
    }
    public void speak1(){
        System.out.println("普通方法...");
    }
}

public class A extends  Father {
    static {
        System.out.println("初始化子类静态块...");
    }
    public A(){
        System.out.println("初始化子类构造方法...");
    }
    public static void main(String[] args) {
        System.out.println(Father.i);
        Father a = new A();
        a.speak1();
    }
}
//输出
初始化父类的静态块...
初始化子类静态块...
10
初始化父类的构造方法...
初始化子类构造方法...
普通方法...
```

### Java中的参数传递，到底是值传递还是引用传递？（用友Java）

<font color='red'>结论：Java只有值传递，没有引用传递！</font>

- 值传递：将参数复制一份，修改形参不会对实参造成影响
- 引用传递：将实参的地址传递给形参，修改形参也就是在修改实参

值传递和引用传递的区别并不是传递的内容，而是**实参到底有没有被复制一份给形参**。

基本类型作为参数被传递时肯定是值传递；引用类型作为参数被传递时也是值传递，只不过“值”为对应
的引用。

### 为什么有了字节流还需要字符流?

<font color='red'>Java中一切都是字节流，没有字符流</font>，字符只是根据编码对字节流进行翻译的结果。

Java I/O有两个：

- 面向字节流的**InputStream和OutputStream**
- 面向字符流的**Reader和Writer**

Java中InputStreamReader和InputStreamWriter是字节流向字符流解码的桥梁

<font color='blue'>字符流是由Java虚拟机将字节转换得到的</font>

- 音频、视频等媒体文件用字节流比较好
- 涉及到字符的话使用字符流比较好

### 栈和队列的区别？（百度测开）

1. 栈的插⼊和删除操作都是在⼀端进⾏的，⽽队列的操作却是在两端进⾏的。
2. 栈是先进后出，队列是先进先出。
3. 栈只允许在表尾⼀端进⾏插⼊和删除，队列只允许在表尾⼀端进⾏插⼊，在表头⼀端进⾏删除。
4. 遍历数据速度不同。栈只能从头部取数据，也就最先放⼊的需要遍历整个栈最后才能取出来，⽽且在遍历数据的时候还得为数据开辟临时空间，保持数据在遍历前的⼀致性。队列则不同，它基于地址指针进⾏遍历，⽽且可以从头或尾部开始遍历，但不能同时遍历，⽆需开辟临时空间，因为在遍历的过程中不影像数据结构，速度要快的多。

### AVL树和红黑树区别？（用友Java）

AVL树是带有平衡条件的二叉查找树，一般是用平衡因子差值判断是否平衡并通过旋转来实现平衡，左右子树高度差不超过1，和红黑树相比，AVL树是**严格的平衡二叉树**，平衡条件必须满足(**所有结点的左右子树高度差不超过1**)。不管我们是执行插入还是删除操作，只要不满足上面的条件，就要通过旋转来保存平衡，而因为旋转非常**耗时**，由此我们可以知道**AVL树适合用于插入与删除次数比较少，但查找多的情况**。

由于维护这种高度平衡所付出的代价比从中获得的效率收益还大，故而实际的应用不多，更多的地方是用追求局部而不是非常严格整体平衡的红黑树。当然，**如果应用场景中对插入删除不频繁，只是对查找要求较高，那么AVL还是较优于红黑树。**

-----------

红黑树是一种二叉查找树，但在每个节点增加一个存储位表示结点的颜色，可以是红或黑(非红即黑)。通过对任何一条从根到叶子的路径上各个节点着色的方式的限制，**红黑树确保没有一条路径会比其他路径长出两倍**，因此，红黑树是一中**弱平衡二叉树**(由于是弱平衡，可以看到，在相同的节点情况下，**AVL树的高度低于红黑树**)，相对于要求严格的AVL树来说，它的旋转次数少，`插入最多两次旋转`，`删除最多三次旋转`，所以对于搜索，插入，删除操作较多的情况下，我们就用红黑树。

<font color='red'>红黑树性质：</font>

**(1)结点非红即黑**

**(2)根结点是黑色的**

**(3)每个叶子节点(NULL节点)是黑色的**

**(4)每个红色节点的两个子节点都是黑色的。(不能有两连续的红色节点)**

**(5)从任一节点到其每个叶子的所有路径都包含相同数目的黑色节点。**

**注意：性质(5)保证红黑树的最长路径不超过最短路径的两倍。**

### try和finally中都有return语句，执行哪一个return？

<font color='blue'>try 中的 return 语句调用的函数先于 finally 中调用的函数执行</font>，也就是说 <font color='blue'>try 中的 return 语句先执行，finally 语句后执行</font>，但try中的 return 并不是让函数马上返回结果，而是 return 语句执行后，将把返回结果放置进<font color='red'>函数栈</font>中，此时函数并不是马上返回，它要执行 finally 语句后才真正开始返回。

但此时会出现两种情况：

- ① 如果finally中也有return，则会直接返回finally中的return结果，并终止程序，函数栈中的return不会被完成
- ② 如果finally中没有return，则在执行完finally中的代码之后，会将函数栈中保存的try return的内容返回并终止程序

> 1. 不管有没有出现异常，finally块中代码都会执行
> 2. 当try和catch中有return时，finally仍然会执行
> 3. finally是在try中return后面的表达式运算后执行的（此时并没有返回运算后的值，而是先把要返回的值保存起来，管finally中的代码怎么样，返回的值都不会改变，仍然是之前保存的值），所以函数返回值是在finally执行前确定的
> 4. finally中最好不要包含return，否则程序会提前退出，返回值不是try或catch中保存的返回值

### 知道泛型吗？知道什么讲什么

**泛型**：将类型由原来的具体的类型参数化，类似于方法中的变量参数，此时类型也定义成参数形式（可以称之为类型形参），然后在使用/调用时传入具体的类型，其`本质是为了参数化类型`。

**类型擦除**：泛型是通过类型擦除来实现的，编译器在编译时擦除了所有类型相关的信息，所以在运行时不存在任何类型相关的信息。

**泛型中的限定通配符和非限定通配符**：

有两种限定通配符，一种是`<? extends T>`它通过确保类型必须是T的子类来设定类型的上界，另一种是`<? super T>`它通过确保类型必须是T的父类来设定类型的下界。泛型类型必须用限定内的类型来进行初始化，否则会导致编译错误。另一方面`<?>表示了非限定通配符`，因为`<?>`可以用任意类型来替代。

**Array数组中可以用泛型吗?** 不能，简单的来讲是因为如果可以创建泛型数组，泛型擦除会导致编译能通过，但是运行时会出现异常。所以如果禁止创建泛型数组，就可以避免此类问题。

**如何阻止Java中的类型未检查的警告?**使用`@SuppressWarnings(“unchecked”)`注解来屏蔽

### int和Integer的自动拆箱/装箱相关问题

java中为每一种基本类型都提供相应的包装类型。

`byte（1）,short（2）,char（2）,int（4）,long（8）,float（4）,double（8）和boolean（1）`

`Byte,Short,Character,Integer,Long,Float,Double,Boolean`

自动装箱就是Java自动将基本类型值转换成包装类型，比如将int的变量转换成Integer对象，这个过程叫做装箱，反之将Integer对象转换成int类型值，这个过程叫做拆箱。

**补充：基本数据类型和包装类的区别？**

1. 基本数据类型是值传递，包装类是引用传递
2. 基本数据类型是存放在栈中的，而包装类是存放于堆中的
3. 基本数据类型初始值如：int=0，而包装类Integer=null
4. 集合中添加的元素一定是包装类引用数据类型
5. 声明基本数据类型不需要实例化可直接赋值，而包装类必须申请一个存储空间实例化才可赋值

### 布隆过滤器

bloom算法类似一个hash set，用来判断某个元素（key）是否在某个集合中。和一般的hash set不同的是，这个算法无需存储key的值，<font color='blue'>对于每个key，只需要k个比特位，每个存储一个标志，用来判断key是否在集合中。</font>

**算法：**

1. 首先需要k个hash函数，每个函数可以把key散列成为1个整数
2. 初始化时，需要一个长度为n比特的数组，每个比特位初始化为0
3. 某个key加入集合时，用k个hash函数计算出k个散列值，并把数组中对应的比特位置为1
4. 判断某个key是否在集合时，用k个hash函数计算出k个散列值，并查询数组中对应的比特位，如果所有的比特位都是1，认为在集合中。

**优点：**不需要存储key，节省空间

**缺点：**

1. 算法判断key在集合中时，有`一定的概率`key其实不在集合中
2. 无法删除

### Java反射有没有了解过？应用场景有哪些？（百度测开）

反射就是指程序在运行的时候可以知道一个类的自身信息。对于任何一个类：可以知道这个类的属性和方法。对于任何一个对象：可以调用这个对象的任何一个方法和属性。反射就是把java类中的各种成分映射成一个个的Java对象。

**静态编译：**在编译时确定类型，绑定对象。**动态编译：**在运行时确定类型，绑定对象。

- 反射机制的优缺点：
  - 优点：运行期类型的判断，动态加载类，提高代码灵活度。
  - 缺点：性能瓶颈：反射相当于一系列解释操作，通知 JVM 要做的事情，性能比直接的java代码要慢很多。

**应用场景：**

1. 在使用JDBC连接数据库时使用Class.forName()通过反射加载数据库的驱动程序
2. Spring框架也用到很多反射机制，最经典的就是xml的配置模式。Spring 通过 XML 配置模式装载 Bean 的过程：
   1. 将程序内所有 XML 或 Properties 配置文件加载入内存中
   2. Java类里面解析xml或properties里面的内容，得到对应实体类的字节码字符串以及相关的属性信息
   3. 使用反射机制，根据这个字符串获得某个类的Class实例
   4. 动态配置实例的属性

### 重写和重载区别？（用友Java）

#### 重写

1. 方法名必须相同，参数列表必须相同，返回值类型必须和父类相同或者是父类的子类
2. 运行时多态
3. 访问权限不能比父类中被重写的方法的访问权限更低
4. 不能比父类被重写方法声明更多的异常

#### 重载

1. 编译时多态
2. 方法的参数列表不一定相同，访问修饰符和返回值类型可以相同也可以不同

### Try-catch-finally中，可单独与finally一起使用的是?

finally不管是否有异常都会执行，而且，try可以和catch和finally中的一个搭配使用，但是catch和finally不能单独使用。

### TreeMap介绍下？

TreeMap是一个能比较元素大小的Map集合，`会对传入的key进行了大小排序`。其中，可以使用元素的自然顺序，也可以使用集合中自定义的比较器来进行排序；不同于HashMap的哈希映射，TreeMap实现了<font color='red'>红黑树</font>的结构，形成了一颗二叉树。

TreeMap继承于**AbstractMap**，实现了Map, Cloneable, NavigableMap, Serializable接口。

- TreeMap 继承于AbstractMap，而AbstractMap实现了Map接口，并实现了Map接口中定义的方法，减少了其子类继承的复杂度；
- TreeMap 实现了Map接口，成为Map框架中的一员，可以包含着key-value形式的元素；
- TreeMap 实现了NavigableMap接口，意味着拥有了更强的元素搜索能力；
- TreeMap 实现了Cloneable接口，实现了clone()方法，可以被克隆；
- TreeMap 实现了Java.io.Serializable接口，支持序列化操作；

TreeMap特点：

- **不允许出现重复的key；**
- **可以插入null键，null值；**
- **可以对元素进行排序；**
- **无序集合（插入和遍历顺序不一致）；**

### Array.sort的底层中，为何一部分用快排而不用堆排序？

- 在数组的数量`小于47`的情况下使用`插入排序`

- 在`大于或等于47或少于286`会进入`快速排序`（双轴快排）

- `大于286`采用`归并排序`

### map.put(100,20)再map.get(new Long(100))结果是多少？

```java
public class Test {
    public static void main(String[] args) {
        Map<Integer,Integer> map = new HashMap<>();
        map.put(100,20);
        System.out.println(map.get(new Long(100)));
    }
}
-----------------
null
```

### 为什么要重写hashcode和equals方法？

两个都属于`Object类`的方法

`equals()`方法是用来判断其他的对象是否和该对象相等；`hashCode()`方法给对象返回一个hashcode值

`equals`引用类型是内容的比较，而已经不再是地址的比较，而基本类型是进行值的比较

- 判断对象是否相同，先根据hashcode进行的判断，相同的情况下再根据equals()方法进行判断。如果只重写了equals方法，而不重写hashcode的方法，会造成hashcode的值不同，而equals()方法判断出来的结果
  为true。
- 在Java中的一些容器中，不允许有两个完全相同的对象，插入的时候，如果判断相同则会进行覆盖。这
  时候如果只重写了equals（）的方法，而不重写hashcode的方法，Object中hashcode是根据对象的存储地址转换而形成的一个哈希值。这时候就有可能因为没有重写hashcode方法，造成相同的对象散列到
  不同的位置而造成对象的不能覆盖的问题。

### HashMap为什么无符号移动16位以及为什么要异或运算？

```java
static final int hash(Object key) {
        int h;
        return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
    }
```

`如果key==null那么就将键值对存入索引为0的桶内，如果不为空则计算key的hashcode值，将h右移16位进行异或运算得到hash值`。右移16位其实是为了`减少碰撞，进一步降低hash冲突的几率`。int类型的数值是4个字节的，右移16位异或可以同时保留高16位与低16位的特征。

--------------

> if ((p = tab[i = (n - 1) & hash]) == null)	tab[i] = newNode(hash, key, value, null);

首先将高16位无符号右移16位与低十六位做异或运算。如果不这样做，而是直接做&运算那么高十六位所代表的部分特征就可能被丢失将高十六位无符号右移之后与低十六位做异或运算，使得高十六位的特征与低十六位的特征进行了混合得到的新的数值中就高位与低位的信息都被保留了 ，而在这里采用异或运算而不采用`&` ，`|` 运算的原因是异或运算能更好的保留各部分的特征，`如果采用&运算计算出来的值会向0靠拢`，`采用|运算计算出来的值会向1靠拢`。

**<u><font color='red'>总结：最终目的还是为了让哈希后的结果更均匀的分布，减少哈希碰撞，提升hashmap的运行效率</font></u>**

### 为什么jdk1.8的hashmap先插入再扩容？

可能原因是JDK1.7采用头插法，扩容后，计算hash，只需要插入链表头部就行。而JDK1.8采用尾插法，如果先扩容，扩容后需要遍历一遍，再找到尾部进行插入

```java
if(++size > threshold){
    resize();
}
afterNodeInsertion(evict);
return null;
```

### 编译时异常和运行时异常区别+Error和Exception区别？（用友Java）

> 在 Java 中，所有的异常都有一个共同的祖先 `Throwable`（可抛出）。`Throwable` 指定代码中可用异常传播机制通过 Java 应用程序传输的任何问题的共性。
> `Throwable`： 有两个重要的子类：`Exception`（异常）和 `Error`（错误），二者都是 Java 异常处理的重要子类，各自都包含大量子类。

- ***运行时异常***：都是`RuntimeException`类及其子类异常，表示 JVM 在运行期间可能出现的异常，如`NullPointerException`(空指针异常)、`IndexOutOfBoundsException`(下标越界异常)等，这些异常是***不检查异常***，程序中可以选择捕获处理，也可以不处理。这些异常一般是***由程序逻辑错误引起***的，程序应该从逻辑角度尽可能避免这类异常的发生。
  运行时异常的特点是Java编译器不会检查它，也就是说，当程序中可能出现这类异常，即使没有用`try-catch`语句捕获它，也没有用`throws`子句声明抛出它，也会编译通过。
- ***非运行时异常 （编译异常）***：是`RuntimeException`以外的异常，类型上都属于`Exception`类及其子类。从程序语法角度讲是必须进行处理的异常，如果***不处理，程序就不能编译通过***。如`IOException`、`SQLException`等以及用户自定义的Exception异常，一般情况下不自定义检查异常。

<font color='red'>非受检查异常和受检查异常之间的区别：</font>是否强制要求调用者必须处理此异常，如果强制要求调用者
必须进行处理，那么就使用受检查异常，否则就选择非受检查异常。

----------------------

- **Exception：**程序本身可以处理的异常，可以通过 catch 来进行捕获，通常遇到这种错误，应对其进行处理，使应用程序可以继续正常运行。Exception 又可以分为`运行时异常`(RuntimeException, 又叫非受检查异常)和`非运行时异常`(又叫受检查异常) 。
- **Error：**属于程序无法处理的错误 ，我们没办法通过 catch 来进行捕获 。例如，系统崩溃，内存不足，堆栈溢出等，编译器不会对这类错误进行检测，一旦这类错误发生，通常应用程序会被终止，仅靠应用程序本身无法恢复。

### NoClassDefFoundError 和ClassNotFoundException 区别？

`NoClassDefFoundError` 是一个 Error 类型的异常，是由 JVM 引起的，不应该尝试捕获这个异常。引起
该异常的原因是` JVM 或 ClassLoader 尝试加载某类时在内存中找不到该类的定义，该动作发生在运行期
间，即编译时该类存在，但是在运行时却找不到了，可能是变异后被删除了等原因导致`。

`ClassNotFoundException `是一个受检查异常，需要显式地使用 try-catch 对其进行捕获和处理，或在方
法签名中用 throws 关键字进行声明。当使用 Class.forName, ClassLoader.loadClass 或 
ClassLoader.findSystemClass 动态加载类到内存的时候，通过传入的类路径参数没有找到该类，就会
抛出该异常；另一种抛出该异常的可能原因是某个类已经由一个类加载器加载至内存中，另一个加载器
又尝试去加载它。

### HashMap中key为null时存到哪儿？

```java
if (key == null)  
    return putForNullKey(value);  
//那就看看这个putForNullKey是怎么处理的吧。  
private V putForNullKey(V value) {  
    for (Entry<K,V> e = table[0]; e != null; e = e.next) {  
        if (e.key == null) {  
            V oldValue = e.value;  
            e.value = value;  
            e.recordAccess(this);  
            return oldValue;  
        }  
    }  
    modCount++;  
    addEntry(0, null, value, 0);  
    return null;  
}
```

`存到索引为0的位置`

### Java8新特性知道那些？（用友Java）

1. Lambda表达式
2. 语法<font color='green'>(parameters) -> expression或(parameters) ->{statements; }</font>
3. 变量作用域，lambda 表达式只能引用标记了 final 的外层局部变量，这就是说不能在lambda内部修改定义在域外的局部变量，否则会编译错误
4. 函数式接口，即一个有且仅有一个抽象方法，但是可以有多个非抽象方法的接口
5. Java Stream，以声明的方式处理数据
6. Java 8通过发布新的java.time.Local（本地）/Zoned（时区）进一步加强对日期与时间的处理
7. Java8中，Base64编码已经成为Java类库的标准；Java 8 内置了 Base64 编码的编码器和解码器

### 讲下LinkedHashMap（用友Java）？

LinkedHashMap 继承自 HashMap，在 HashMap 基础上，通过<font color='red'>维护一条**双向链表**，解决了 HashMap 不能随时保持遍历顺序和插入顺序一致的问题</font>。在实现上，LinkedHashMap 很多方法直接继承自 HashMap，仅为维护双向链表覆写了部分方法。

LinkedHashMap底层仍然是基于拉链式散列结构，该结构由数组和链表或红黑树组成。LinkedHashMap 在上面结构的基础上，增加了一条双向链表，使得上面的结构可以保持键值对的插入顺序。同时通过对链表进行相应的操作，实现了访问顺序相关逻辑。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/15166338955699.jpg">

> 淡蓝色的箭头表示前驱引用，红色箭头表示后继引用。每当有新键值对节点插入，新节点最终会接在 tail 引用指向的节点后面。而 tail 引用则会移动到新的节点上，这样一个双向链表就建立起来了。

### 直接new对象不行吗？为啥用反射（五种创建对象的方式）？

`复习一下创建对象的方式`

- 使用new关键字

```java
Person person = new Person();
Person zhangSan = new Person("张三");
Person lisi = new Person("李四", 28);
```

- 使用Class类的newInstance方法（`仅能调用无参构造函数，并且还需要抛出异常`）

```java
try {
    Person person1 = (Person) Class.forName("com.wx.learn.control.Person").newInstance();
    Person person2 = Person.class.newInstance();
} catch (InstantiationException e) {
    e.printStackTrace();
} catch (IllegalAccessException e) {
    e.printStackTrace();
} catch (ClassNotFoundException e) {
    e.printStackTrace();
}
```

- 使用Constructor类的newInstance方法（`可以根据传入的初始化数据来选择对应的构造函数，也需要异常抛出`）

```java
try {
    Constructor constructor = Person.class.getConstructor();
    constructor.newInstance();
} catch (NoSuchMethodException e) {
    e.printStackTrace();
} catch (IllegalAccessException e) {
    e.printStackTrace();
} catch (InstantiationException e) {
    e.printStackTrace();
} catch (InvocationTargetException e) {
    e.printStackTrace();
}
//-----------有参-------------------------
Constructor cons = MyTestEntity.class.getDeclaredConstructor(String.class, int.class);
MyTestEntity emily = cons.newInstance("Emily", 10);
```

- 使用clone方法（`用clone()方法，需要现在对象中重写clone方法，然后才能让对象调用，并且有一个CloneNotSupportedException异常抛出，而且不会调用构造函数`）

```java
Person person = new Person();
try {
    Person personClone = (Person) person.clone();
} catch (CloneNotSupportedException e) {
    e.printStackTrace();
}
```

- 使用反序列化（`使用反序列化无可避免的就是要从字符串变为对象。而且读取数据转换成对象时，会抛出异常`）

```java
try {
    ObjectInputStream in = new ObjectInputStream(new FileInputStream("data.obj"));
    Person emp5 = (Person) in.readObject();
} catch (IOException e) {
    e.printStackTrace();
} catch (ClassNotFoundException e) {
    e.printStackTrace();
}
```

**总结：**

- 通过构造器创建对象可以调用自定义的有参构造函数，`Class对象方式创建只能调用默认的无参构造函数创建对象`
- 通过构造器创建对象可以调用非public类型方法，通过修改访问权限的方式可以获取private类型的构造器去创建对象
- Spring等框架都用的构造器的方式创建对象，更加灵活方便

### 各种排序算法比较+二叉树？（用友Java）

二叉搜索树，平均时间复杂度O(logn)，最坏情况下O(n)

<img src="https://images2015.cnblogs.com/blog/975503/201702/975503-20170214211234550-1109833343.png">

### 删除List中指定的元素，用什么方法？（用友Java）

利用for遍历删除，删除某个元素之后，list的大小发生变化，索引也发生变化，`不应该使用for循环遍历再list.remove()的方式进行删除`。(报异常java.util.ConcurrentModificationException)，应该使用迭代器的方式进行元素的删除。

```java
List<String> list = new ArrayList<>(Arrays.asList("a","b","c","f","b","e","d"));
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    String next = iterator.next();
    System.out.println("------"+next+"------");
    if ("b".equals(next)) {
        iterator.remove();
    }
}
System.out.println(list.toString());
```

### Array和ArrayList的区别？（百度测开）

- <font color='blue'>长度区别</font>

> Array是数组，声明好之后，其长度就已经固定
>
> ArrayList底层是用数组实现的，但是ArrayList的长度是可变的，在每次添加时，如果发现空间不足的话，会创建一个长度大概是原来1.5倍的新数组（java8源码），然后把原来的数组元素复制过去。

- <font color='blue'>存放数据区别</font>

> Array可以除了可以存放对象类型的数据之外，还可以存放基本数据类型的数据
>
> ArrayList只能存放对象数据类型的数据，因为它的类在定义时已经是针对Object的子类做了泛型的约束。
>
> ArrayList如果确实要存放基本数据类型的数据，那只能存放基本数据类型对应的包装类的数据。在数据的存取时可能会涉及到java基本数据类型的自动装箱、自动拆箱。

- <font color='blue'>使用方法区别</font>

> Array数组只能通过数组下标来对指定位置的元素进行变更
>
> ArrayList在Array的基础上增加了很多的方法。比如add，addAll，remove，removeAll，contains，以及iterator等等多种丰富的功能方法

- <font color='blue'>效率上的区别</font>

> ArrayList是在Array的基础上做了各种丰富多样的功能增强，所以ArrayList效率上自然是不如Array效率高了

- <font color='blue'>使用场景的区别</font>

> 如果是在整个过程中长度不会变化的话，可是使用Array数组
>
> 如果在使用过程中，大小不固定，可能需要动态增长的话，就需要使用ArrayList了

### 了解Java动态加载吗？（用友Java）

<font color='green'>ClassLoader.getSystemClassLoader().loadClass()或者Class.forName()</font>方法使用的类加载器是AppClassLoader，一般也称作系统加载器。它在加载类之前首先会检查类是否已被加载，如果是，它就不会重新加载一次，因此修改的结果不会生效。

```java
/**
*自定义类加载器，主要实现findClass()方法和defineClass()方法
*/
public class MyClassLoader extends ClassLoader {
	@Override
	public Class<?> findClass(String name) throws ClassNotFoundException {
		try {
			byte[] classDate = getDate(name);
			if (classDate == null) {
			}else {
				// defineClass方法将字节码转化为类
				return defineClass(null, classDate, 0, classDate.length);
			}
		} catch (IOException e) {
			e.printStackTrace();
		}
		return super.findClass(name);
	}
 
	// 返回类的字节码
	private byte[] getDate(String className) throws IOException {
		InputStream in = null;
		ByteArrayOutputStream out = null;
		try {
			in = new FileInputStream(className);
			out = new ByteArrayOutputStream();
			byte[] buffer = new byte[2048];
			int len = 0;
			while ((len = in.read(buffer)) != -1) {
				out.write(buffer, 0, len);
			}
			return out.toByteArray();
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} finally {
			in.close();
			out.close();
		}
		return null;
	}
}
```

### 十进制转八进制？转二进制？（百度测开）

#### 十进制转八进制

```java
//除8取余法
public static void main(String[] args) {
    int num = 115;
    StringBuilder sb = new StringBuilder();
    while(num >= 1){
        sb.append(num % 8);
        num /= 8;
    }
    System.out.println(sb.reverse().toString());
}
```

#### 十进制转二进制

```java
public static void main(String[] args) {
    int num = 115;
    StringBuilder sb = new StringBuilder();
    while(num >= 1){
        sb.append(num % 2);
        num /= 2;
    }
    System.out.println(sb.reverse().toString());
}
```

## JVM

### 类加载过程？（用友Java）

JVM将类描述数据从.class文件中加载到内存，并对数据进行解析和初始化，最终形成被JVM直接使用的Java类型。 类从被加载到JVM中开始，到卸载为止，整个生命周期包括：<u>**加载、链接（包含三部分——验证、准备、解析）、初始化、使用和卸载**</u>七个阶段。

- `加载`：通过类的全限定名获取定义此类的二进制字节流，并放到方法区中，然后在内存中生成一个代表这个类的Class对象，作为方法区中这个类的访问入口 
- `链接`：链接阶段分为3个部分：验证、准备、解析 
- `验证`：确保上面的class文件二进制字节流中包含的信息符合当前虚拟机要求，保证类加载的正确性 
- `准备`：为类变量分配内存，并且设置该类变量的默认初始值（如int型默认设为0，boolean型默认设为false） 
- `解析`：将方法区的运行时常量池中的符号引用转换为直接引用。所谓的符号引用就是使用一组符号来表示引用的目标，因为在编译阶段，编译成的.class文件并不知道实际引用类的内存地址，所以只能用符号引用来代替。比如说People类中引用了Tool类，在编译时，People类并不知道Tool类的实际内存地址，因此只能使用一组符号表示Tool类的地址。而直接引用是直接指向目标的指针。 
- `初始化`：执行类构造器方法`<clinit>()`，此方法自动收集所有类变量的赋值动作（内存已经在准备阶段分配完毕）和静态代码块中的语句合并而来并执行 

### 如何判断一个对象是否存活？（用友Java）

#### 引用计数法

给每一个对象设置一个引用计数器，当有一个地方引用该对象的时候，引用计数器就+1，引用失效时，
引用计数器就-1；当引用计数器为0的时候，就说明这个对象没有被引用，也就是垃圾对象，等待回收；

<font color='red'>缺点：</font>无法解决`循环引用`的问题，当A引用B，B也引用A的时候，此时AB对象的引用都不为0，此时也就
无法垃圾回收，所以一般主流虚拟机都不采用这个方法。

#### 可达性分析

从一个被称为`GC Roots`的对象向下搜索，如果一个对象到GC Roots没有任何引用链相连接时，说明此对
象不可用。

#### GC Roots有哪些？ 

- 虚拟机栈的栈帧的局部变量表中的引用 
- 本地方法栈的JNI引用对象 
- 方法区中类的静态属性 
- 方法区中的常量 
- 被同步锁synchronized持有的对象 
- 对于分区的G1，可能会存在将另一个区域的对象也临时作为GC Roots

### 堆和栈的区别？（百度测开）

1. 从存储⻆度来看，栈内存存储的是局部变量和对象引⽤，⽽堆内存存储的是实体；
2. 从存取速度来看，栈存取速度快，堆区存取⽐较慢，因为要在运⾏时动态分配内存，存取速度较慢；
3. 从线程访问的⻆度，每个线程都有⼀个栈，所有线程共享⼀个堆；
4. 栈没有GC，所以栈内存存放的变量⽣命周期⼀旦结束就会被释放，堆有GC，堆内存存放的实体会被垃圾回收机制不定时的回收

### 你知道哪几种垃圾回收器，各自的优缺点，重点讲一下CMS和G1和各自的特点?

- Serial/Serial Old，串行回收，简单高效，只适合单CPU 
- ParNew/CMS，新生代并行回收，效率提升，老年代并发回收，STW时间急剧降低。ParNew仍然会STW，CMS会产生内存碎片，无法处理并发清除阶段产生的垃圾，吞吐量不高 
- Parallel/Parallel Old，并行回收，吞吐量优先，可以控制吞吐量以及自适应调节策略。但暂停时间会变高，响应慢 
- CMS是并发标记清除的GC，使用的是标记清除算法，能够与用户线程并发执行，两次STW，能达到低延迟的目标 
- G1，基于分区算法，同样是分代收集，无内存碎片，`可预测的停顿时间模型`，同时实现并行与并发。但在堆内存过小时表现不良好，只有在大堆环境下优势俞明显，且内存占用较高

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/GC.png">

### 讲下CMS和G1区别？

#### CMS

CMS（Concurrent Mark Sweep）收集器是以获取最短回收停顿时间为目标的收集器（追求低停顿），CMS是基于“标记-清除”算法实现的，它在垃圾收集时使得用户线程和 GC 线程并发执行，因此在垃圾收集过程中用户也不会感到明显的卡顿，<font color='blue'>仅作用于老年代收集</font>。它的步骤如下：

1. <font color='green'>初始标记（CMS initial mark）</font>：独占CPU，<font color='red'>stop-the-world</font>, <font color='blue'>仅标记GCroots能直接关联的对象</font>,速度比较快；
2. <font color='green'>并发标记（CMS concurrent mark）:</font>可以和用户线程并发执行，<font color='blue'>通过GCRoots Tracing 标记所有可达对象</font>，`GC Roots范围有虚拟机栈中引用的对象、方法区中类静态属性引用的对象、方法区中常量引用的对象、本地方法栈中JNI引用的对象`；
3. <font color='green'>重新标记（CMS remark）：</font><font color="red">stop-the-world</font>, 对并发标记阶段用户线程运行产生的垃圾对象进行标记**修正**,以及更新逃逸对象；**为啥还要再标记一次？因为第 2 步并没有阻塞其它工作线程，其它线程在标识过程中，很有可能会产生新的垃圾；**
4. <font color='green'>并发清理（CMS concurrent sweep）：</font>清除阶段是清理删除掉标记阶段判断的已经死亡的对象，由于不需要移动存活对象，所以这个阶段也是可以与用户线程同时并发进行的。

**CMS优点：**

- 支持并发收集.
- 低停顿，因为CMS可以控制将耗时的两个stop-the-world操作保持与用户线程恰当的时机并发执行，并且能保证在短时间执行完成，这样就达到了近似并发的目的.

**CMS缺点：**

- CMS收集器对CPU资源非常敏感，在并发阶段虽然不会导致用户线程停顿，但是会因为占用了一部分CPU资源，**如果在CPU资源不足的情况下应用会有明显的卡顿**。

>  CMS默认启动的回收线程数是：`(CPU核数 + 3）/ 4`，当CPU核数不足四个时，CMS对用户程序的影响就可能变得很大。

- `无法处理浮动垃圾`：在执行`并发清理`步骤时，用户线程也会同时产生一部分可回收对象，但是这部分可回收对象只能在下次执行清理是才会被回收。如果在清理过程中预留给用户线程的内存不足就会出现`Concurrent Mode Failure`,一旦出现此错误时便会切换到`SerialOld`回收器。
- **CMS清理后会产生大量的内存碎片**：CMS是一款基于`“标记-清除”`算法实现的回收器，这意味着回收结束时会有内存碎片产生。内存碎片过多时，将会给大对象分配带来麻烦，往往会出现老年代还有很多剩余空间，但就是无法找到足够大的连续空间来分配当前对象，而不得不提前触发一次 Full GC 的情况。

>  为了解决这个问题，CMS收集器提供了一个` -XX:+UseCMSCompactAtFullCollection `开关参数（默认开启），用于在 Full GC 时开启内存碎片的合并整理过程，由于这个内存整理必须移动存活对象，是无法并发的，这样停顿时间就会变长。还有另外一个参数` -XX:CMSFullGCsBeforeCompaction`，这个参数的作用是要求CMS在执行过若干次不整理空间的 Full GC 之后，下一次进入 Full GC 前会先进行碎片整理（默认值为0，表示每次进入 Full GC 时都进行碎片整理）。

---------

#### G1

G1（Garbage First）回收器采用面向局部收集的设计思路和基于Region的内存布局形式，`这样在进行收集时不必在全堆范围内进行`，是一款主要面向服务端应用的垃圾回收器。G1 在JDK9 之后成为服务端模式下的默认垃圾回收器，取代了 Parallel Scavenge 加 Parallel Old 的默认组合，G1从整体来看是基于 `标记-整理 `算法实现的回收器，但从局部（两个Region之间）上看又是基于` 标记-复制` 算法实现的。它主要特点在于`达到可控的停顿时间，用户可以指定收集操作在多长时间内完成`，它的步骤如下：

1. 初始标记（Initial Marking）：仅仅只是标记一下 `GC Roots `能直接关联到的对象，并且修改TAMS指针的值，让下一阶段用户线程并发运行时，能正确地在可用的Region中分配新对象。这个阶段需要停顿线程`（stop the world）`，但耗时很短，而且是借用进行Minor GC的时候同步完成的，所以G1收集器在这个阶段实际并没有额外的停顿。
2. 并发标记（Concurrent Marking）：是从GC Roots开始堆中对象进行可达性分析，找出存活的对象，这阶段耗时较长，但可与用户程序并发执行，该阶段可以被Young GC中断。
3. 最终标记（Final Marking）：是为了修正并发标记期间因用户程序继续运作而导致标记产生变动的那一部分标记记录，虚拟机将这段时间对象变化记录在线程Remembered Set Logs里面，最终标记阶段需要把Remembered Set Logs的数据合并到Remembered Set中，`此阶段是stop-the-world操作`，使用snapshot-at-the-beginning (SATB) 算法。
4. 筛选回收（Live Data Counting and Evacuation）：`更新Region的统计数据，对各个Region的回收价值和成本进行排序，根据用户所期望的停顿时间来制定回收计划`，可以自由选择任意多个Region构成回收集，然后把决定回收的那一部分Region的存活对象复制到空的Region中，再清理掉整个旧Region的全部空间。这里的操作涉及存活对象的移动，必须暂停用户线程`（stop the world）`，由多条回收器线程并行完成的。

### JVM中一次完整的GC是什么样？（用友Java）

在 Java 中，堆被划分成两个不同的区域：新生代 ( Young )、老年代 ( Old )，新生代默认占总空间的 1/3，老年代默认占 2/3。

新生代有 3 个分区：Eden、To Survivor、From Survivor，它们的默认占比是 8:1:1。

新生代的垃圾回收（又称Minor GC）后只有少量对象存活，所以选用复制算法，只需要少量的复制成本就可以完成回收。老年代的垃圾回收（又称Major GC）通常使用“标记-清理”或“标记-整理”算法。

**转化流程：**

- 对象优先在Eden分配。当 eden 区没有足够空间进行分配时，虚拟机将发起一次 Minor GC。
  - 在 Eden 区执行了第一次 GC 之后，存活的对象会被移动到其中一个 Survivor 分区；
  - Eden 区再次 GC，这时会采用复制算法，将 Eden 和 from 区一起清理，存活的对象会被复制
    到 to 区；
  - 移动一次，对象年龄加 1，对象年龄大于一定阀值会直接移动到老年代。GC年龄的阀值可以
    通过参数` -XX:MaxTenuringThreshold `设置，默认为 15；
  - 动态对象年龄判定：Survivor 区相同年龄所有对象大小的总和 > (Survivor 区内存大小 * 这个
    目标使用率)时，大于或等于该年龄的对象直接进入老年代。其中这个使用率通过 `-
    XX:TargetSurvivorRatio `指定，默认为 50%；
  - Survivor 区内存不足会发生担保分配，超过指定大小的对象可以直接进入老年代。
- `大对象直接进入老年代`，大对象就是需要大量连续内存空间的对象（比如：字符串、数组），为了避免为大对象分配内存时由于分配担保机制带来的复制而降低效率。
- 老年代满了而无法容纳更多的对象，Minor GC 之后通常就会进行Full GC，Full GC 清理整个内存堆 – 包括年轻代和老年代。

### 为什么CMS两次标记时要 stop the world?（百度测开）

当虚拟机完成两次标记后，便确认了可以回收的对象。但是，垃圾回收并不会阻塞我们程序的线程，他是与当前程序并发执行的。所以问题就出在这里，当GC线程标记好了一个对象的时候，此时我们程序的线程又将该对象重新加入了“关系网”中，当执行二次标记的时候，该对象也没有重写finalize()方法，因此回收的时候就会回收这个不该回收的对象。 

虚拟机的解决方法就是`在一些特定指令位置设置一些“安全点”`，当程序运行到这些“安全点”的时候就会暂停所有当前运行的线程（Stop The World 所以叫STW），暂停后再找到“GC Roots”进行关系的组建，进而执行标记和清除。

这些特定的指令位置主要在：

​    **1、循环的末尾**

​    **2、方法临返回前 / 调用方法的call指令后**

​    **3、可能抛异常的位置**

### 元空间Metaspace内存溢出OOM原因？

Metaspace元空间主要是存储类的元数据信息，我们的应用里加载的各种类描述信息，比如类名、属性、方法、访问限制等，按照一定的结构存储在Metaspace里。

由此可知`metaspace空间增长是由于反射类加载，动态代理生成的类加载等导致的`，也就是说Metaspace的大小和加载类的数据有关系，加载的类越多metaspace占用的内存也就越大。

**主要原因：**

1. 某个业务场景的访问量暴增，导致Metaspace内存溢出
2. 在JVM正式环境，直接使用JDK自带的参数，一般默认的只有几十MB，针对大型的应用项目，很容易不够，报异常
3. 很多人在写cglib之类的技术动态生成一些类，如果代码没有控制好回收，容易引发MetaSpace溢出

### Java内存模型JMM（用友Java）

在 JDK1.2 之前，Java 的内存模型实现总是从主存（即共享内存）读取变量，是不需要进⾏特别 的注意的。⽽在当前的 Java 内存模型下，线程可以把变量保存本地内存（⽐如机器的寄存器） 中，⽽不是直接在主存中进⾏读写。这就可能造成⼀个线程在主存中修改了⼀个变量的值，⽽另外⼀个线程还继续使⽤它在寄存器中的变量值的拷⻉，造成数据的不⼀致。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/jmm.png">

要解决这个问题，就需要把变量声明为` volatile `，这就指示 JVM，这个变量是共享且不稳定的， 每次使⽤它都到主存中进⾏读取。所以， volatile 关键字除了`防⽌ JVM 的指令重排` ，还有⼀个重要的作⽤就是`保证变量的可⻅性`。

### JVM内存模型1.7和1.8区别？

<img src="https://img2020.cnblogs.com/blog/757939/202009/757939-20200917180800585-2026413046.png">

1.7中有永久代，1.8中取消了永久代，取而代之的是元数据区

### 新建对象内存分配过程？

#### 对象的创建

<img src="https://img-blog.csdnimg.cn/20190421174011622.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L211bGluc2VuNzc=,size_16,color_FFFFFF,t_70">

1. **首先进行类加载的检查：**虚拟机遇到new指令的时候，首先去检查该指令的参数是否能够在常量池中定位到这个类的符号引用，并且检查该符号引用代表的类是否已经被加载过、解析和初始化过。若没有，必须`先执行相应的类加载的过程`。
2. **分配内存：**类加载检查通过之后，虚拟机为对象分配内存。（内存大小在类加载完后就能确定）。分配的方式有`“指针碰撞”`和`“空闲列表”`两种，<font color='green'>若java堆是规整的，采用“指针碰撞”；反之采用空闲列表</font>。（两种内存分配的方式见下文“内存的分配”）
3. **初始化零值：**内存分配完之后，虚拟机将分配到的内存空间初始化为零值。保证了对象的实例字段在java代码中可以不赋初值就直接使用。
4. **设置对象头：**初始化零值之后，虚拟机要对对象进行必要的设置：对象头的设置。（具体包括的内容见下文“对象的内存布局”）
5. **执行init方法：**最后，虚拟机的视角来看，新的对象已经产生了。但是从java程序的视角来看，init方法还没有执行，所有字段还都是零。so，一般来说，执行new指令之后就会接着执行init方法，把对象按照程序员的意愿进行初始化。真正可用的对象就完全产生了。

总结一下，遇到new指令之后先进行类加载的检查，检查就是检查常量池中是否有该new类的符号引用，然后判断该符号引用是否已经被加载、解析、初始化过；然后给该类的对象分配内存；然后赋值为0；然后设置对象头；最后执行init方法。

-----------

#### 内存分配

分配方式有 **“指针碰撞” 和 “空闲列表”** 两种，选择那种分配方式由 Java 堆是否规整决定，而Java堆是否规整又由所采用的垃圾收集器是否带有压缩整理功能决定。GC回收器的算法是“标记清除”（不规整、有内存碎片）还是“”标记整理（规整），复制算法也是规整的。

<img src="https://img-blog.csdnimg.cn/20190421175552853.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L211bGluc2VuNzc=,size_16,color_FFFFFF,t_70">

1. 指针碰撞

<img src="https://img-blog.csdnimg.cn/20191113161112816.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x6aHVpMTk4Nw==,size_16,color_FFFFFF,t_70">

2. 空闲列表

<img src="https://img-blog.csdnimg.cn/20191113161315477.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x6aHVpMTk4Nw==,size_16,color_FFFFFF,t_70">

内存分配时候出现的并发问题：单线程下，**“指针碰撞” 和 “空闲列表”**分配内存不会有线程安全问题**，**实际开发过程中，创建对象是很频繁的事情，而且是多线程环境，作为虚拟机来说，必须要保证线程是安全的，通常来讲，虚拟机采用两种方式来保证线程安全：

1. **CAS+失败重试：** CAS 是乐观锁的一种实现方式。所谓乐观锁就是，每次不加锁而是 设没有冲突而去完成某项操作，如果因为冲突失败就重试，直到成功为止。虚拟机采用 CAS 配上失败重试的方式保证更新操作的原子性。
2. **TLAB**： 为每一个线程预先在Eden区分配一片内存，JVM在给线程中的对象分配内存时，首先在TLAB分配，当对象大于TLAB中的剩余内存或TLAB的内存已用尽时，再采用上述的CAS进行内存分配。

**TLAB**的全称是**Thread Local Allocation Buffer**，即线程本地分配缓存区，这是一个线程专用的内存分配区域，相当于线程的私有对象。

1. 堆是JVM中所有线程共享的，因此在其上进行对象内存的分配均需要进行**加锁**，这也导致了new对象的开销是比较大的。
2. Sun Hotspot JVM为了提升对象内存分配的效率，对于所创建的线程都会分配一块独立的空间TLAB（Thread Local Allocation Buffer），其大小由JVM根据运行的情况计算而得，**在TLAB上分配对象时不需要加锁**，因此JVM在给线程的对象分配内存时会尽量的在TLAB上分配，在这种情况下JVM中分配对象内存的性能和C基本是一样高效的，但如果**对象过大的话则仍然是直接使用堆空**间分配。
3. `TLAB仅作用于新生代的Eden Space`，因此在编写Java程序时，通常**多个小的对象比大的对象分配起来更加高效**。

如果设置了虚拟机参数 -XX:UseTLAB，在线程初始化时，同时也会申请一块指定大小的内存，只给当前线程使用，这样每个线程都单独拥有一个空间，如果需要分配内存，就在自己的空间上分配，这样就不存在竞争的情况，可以大大提升分配效率。

TLAB空间的内存非常小，缺省情况下仅占有整个Eden空间的1%，也可以通过选项`-XX:TLABWasteTargetPercent`设置TLAB空间所占用Eden空间的百分比大小。

----------

#### 栈上分配

如果确定一个对象的作用域不会逃逸出方法之外，那可以将这个对象分配在栈上，如此一来，对象所占用的内存空间就可以随栈帧出栈而销毁。在一般应用中，不会逃逸的局部对象所占的比例很大，如果能使用栈上分配，那大量的对象就会随着方法的结束而自动销毁了，无须通过垃圾收集器回收，可以减小垃圾收集器的负载。

JVM允许将线程私有的对象打散分配在栈上，而不是分配在堆上。分配在栈上的好处是可以在函数调用结束后自行销毁，而不需要垃圾回收器的介入，从而提高系统性能。

- 一是**逃逸分析**：逃逸分析的目的是判断对象的作用域是否有可能逃逸出函数体。
- 二是**标量替换**：允许将对象打散分配在栈上，比如若一个对象拥有两个字段，会将这两个字段视作`局部变量`进行分配。

只能在**server模式下才能启用逃逸分析**，参数-XX:DoEscapeAnalysis启用逃逸分析，参数-XX:+EliminateAllocations开启标量替换（默认打开）。Java SE 6u23版本之后，HotSpot中默认就开启了逃逸分析，可以通过选项-XX:+PrintEscapeAnalysis查看逃逸分析的筛选结果。

#### 对象的内存布局（用友Java）

<img src="https://img-blog.csdn.net/20181001154640197?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2dlbG9pbg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70">

对象在内存中的布局可以分为3块区域：`对象头（Mark Word和类型指针）`、`实例数据`和`对齐填充`。

**<font color='red'>默认情况下，对象头占12字节 = 8个字节的markword + 4个字节的类型指针</font>**

1. Mark Word，用于存储对象自身的自身运行时数据。哈希码、GC分代年龄、锁状态标志等；
2. 类型指针，对象指向他的类元数据的指针、该指针可以让虚拟机判断该对象是哪一个类的实例。
3. 实例数据，对象真正存储的有效信息。也是程序中所定义的各种类型的字段内容。
4. 对齐填充主要是占位，可以没有。因为Hotspot虚拟机的自动内存管理系统要求对象起始地址必须**是8字节的整数倍**，换句话说就是**对象的大小必须是8字节的整数倍**。而**对象头部分正好是8字节的倍数（1倍或2倍、8字节or16字节）**，因此，当对象实例数据部分没有对齐时，就需要通过对齐填充来补全。（64位的系统，刚好是8个字节，保持对象大小是8的倍数，读取是最快的，这就是对齐的原因）

#### 对象的访问

建立对象就是为了使用对象，我们的Java程序通过栈上的 reference （引用）数据来操作堆上的具体对象。对象的访问方式有虚拟机实现而定，目前主流的访问方式有**①使用句柄和②直接指针**两种：

句柄： 如果使用句柄的话，那么Java堆中将会划分出一块内存来作为句柄池，reference 中存储的就是对象的句柄地址，而句柄中包含了对象实例数据与类型数据各自的具体地址信息；

<img src="https://img-blog.csdnimg.cn/20190421182651817.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L211bGluc2VuNzc=,size_16,color_FFFFFF,t_70">

直接指针： 如果使用直接指针访问，那么 Java 堆对象的布局中就必须考虑如何放置访问类型数据的相关信息，而reference 中存储的直接就是对象的地址。

<img src="https://img-blog.csdnimg.cn/20190421182738462.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L211bGluc2VuNzc=,size_16,color_FFFFFF,t_70">

这两种对象访问方式各有优势。使用句柄来访问的最大好处是 reference 中存储的是稳定的句柄地址，在对象被移动时只会改变句柄中的实例数据指针，而 reference 本身不需要修改。使用直接指针访问方式最大的好处就是速度快，它节省了一次指针定位的时间开销。

### JVM内存布局？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/dd614bf56417939aa0e0694fedf2caa9.png">

**线程独享（生命周期与 Thread 相同，即：线程创建时，相应的区域分配内存，线程销毁时，释放相应内存）：**

1. PC Register：程序计数器， 记录每个线程当前执行的指令信息。eg：当前执行到哪一条指令，下一条该取哪条指令。
2. JVM Stack：也称为虚拟机栈，记录每个栈帧（Frame）中的局部变量、方法返回地址等。线程中每次有方法调用时，会创建Frame，方法调用结束时Frame 销毁。
3. Native Method Stack：本地 (原生) 方法栈，顾名思义就是调用操作系统原生本地方法时，所需要的内存区域。

**线程共享（虚拟机启动时创建，虚拟机退出时释放）：**

1. Heap，堆内存区，也是 GC 垃圾回收的主站场，用于存放类的实例对象及 Arrays 实例等。
2. Method Area：方法区，主要存放类结构、类成员定义，static 静态成员等。
3. Runtime Constant Pool：运行时常量池，比如：字符串，int -128~127 范围的值等，它是 Method Area 中的一部分。

#### 说一下 jvm 的主要组成部分？及其作用？

- ①类加载子系统：负责加载class文件，只负责加载，不负责能否运行，能否运行是执行引擎决定的 

- ②运行时数据区：是java内存中区域最大的一块 
  - 包括虚拟机栈、本地方法栈、堆内存、方法区、程序计数器，其中堆内存和方法区是线程共享的，而其他三个是线程私有的 
  - 堆内存：主要存放的是new出来的对象或数组，而且堆内存是多线程共享的。堆的大小可以用-Xms -Xmx来设置，其中主要分为新生代和老年代，比例默认是2:1，新生代中又分为Eden区和Survivor0、1区，比例是8:1:1 
  - 方法区：主要用于存放已被虚拟机加载的类型信息、方法信息、常量等资源。==方法区中存在一个运行时常量池，用于存放编译期间生成的符号引用或类加载后的直接引用==。`jdk1.7及以后将字符串常量池从原来的方法区移动到了堆内存中`，`并且jdk1.8及以后不再使用永久代来实现方法区，而是使用元空间（本地内存）来实现方法区`。 
  - 虚拟机栈：也就是我们通常说的栈内存，每个线程都含有自己的虚拟机栈。它以栈帧为单位存放数据，并且每执行一个方法生成一个栈帧，其中包含`局部变量表`（用于临时保存变量）、`操作数栈`（用于保存临时的中间变量信息）、`方法返回地址`（用于指定方法执行完毕后返回的地址）、`动态链接`（指向运行时常量池的方法引用，可以将符号引用转换为直接引用） 
  - 本地方法栈：为虚拟机提供Native方法服务 
  - 程序计数器：PC寄存器用于存放下一条指令的地址，也就是即将要执行的代码，由执行引擎来读取这里面的指令。 

- ③执行引擎：将字节码指令解释/编译（此编译并非是字节码文件的编译）为对应平台上的本地机器指令，然后交给操作系统去执行 

- ④本地方法接口：提供本地方法 

### 什么情况下会发生堆内存溢出，栈内存溢出？

#### 栈溢出（用友Java）

栈是线程私有的，他的生命周期与线程相同，每个方法在执行的时候都会创建一个栈帧，用来存储局部变量表，操作数栈，动态链接，方法返回地址信息。局部变量表又包含基本数据类型，对象引用类型（局部变量表编译器完成，运行期间不会变化），所以我们可以理解为`栈溢出就是方法执行是创建的栈帧请求的深度超过了栈能给予的最大深度`。

可能情况：**方法递归调用产生这种结果**

解决方法：**使用参数 -Xss 去调整JVM栈的大小**

#### 堆溢出

可能情况：**堆中主要存储的是对象。如果不断的new对象则会导致堆中的空间溢出**

解决方法：**可以通过 -Xmx4096M 调整堆的总大小**

 ### Java 中都有哪些引用类型（用友Java）？

从级别高到低说是：`强引用、软引用、弱引用、虚引用`

- ①强引用：我们日常创建的对象(new方式)就是强引用类型的，只要强引用的对象是可触及的（即可达），则垃圾收集器永远不会执行回收 

- ②软引用：内存充足时候不会回收，只有在内存溢出前才进行回收，可以用来实现缓存，将临时的数据存储下来，也不占据过多的内存空间，即使没有内存了，垃圾收集器也能将其进行二次回收。java提供了SoftReference来实现软引用，在回收软引用时，可以将引用放到这个ReferenceQueue引用队列中，可以获取到对象的信息，进行额外的处理

- ③弱引用：只要发生了GC，那么软引用直接被回收。也能实现`缓存功能`，因为一旦GC就会回收，不会占用太大内存。java提供了WeakReference来实现弱引用（`ThreadLocalMap中的key使用的是弱引用`），与软引用一样，在回收时可以将弱引用放进一个引用队列，可以获取到对象的信息，跟踪回收情况 

- ④虚引用：用于对象回收跟踪，是引用类型中最弱的一个。虚引用不能像强软弱一样单独使用，要配合引用队列进行使用，也无法通过虚引用来获取被引用的对象，当使用get()方法时，总会返回null。`虚引用的作用就是能在这个对象被垃圾回收器回收时收到一个系统通知，并且能跟踪对象的回收时间`。java提供了PhantomReference来实现虚引用，不过在创建引用时，需要指定引用队列ReferenceQueue 

### 什么是内存泄漏？哪些情况容易发生？（百度测开）

内存泄漏就是【占着茅坑不拉shi】，用动态存储分配函数动态开辟的空间，在使用完毕后未释放，结果导致一直占据该内存单元，直到程序结束。

**常见原因：**

1. 循环过多或死循环，产生大量对象；

2. `静态集合类引起内存泄漏`，因为静态集合的生命周期和 JVM 一致，所以静态集合引用的对象不能被释放
3. 全局性的集合，例如：类中的静态属性，全局性的map中有静态引用或final指向它，对此没有相应的删除机制，导致内存无法及时回收。
4. `不正当的单例使用也会导致内存泄漏`，单例对象初始化后在JVM中（以静态的方式存在），该单例对象对外部对象的引用，使得JVM无法对外部对象进行回收，导致内存泄露。
5. 类的装载器，因为类的装载器具有负载的结构，类的装载器不仅仅与常规的对象引用有关，而且与一
   些静态对象以及对象内部的引用有关，这也导致了JVM无法正常回收内存。
6. 变量的不合理作用域，如果变量定义的范围大于其使用的范围，将会导致内存泄露。
7. 监听器，在Java语言中往往会有很多地方使用到监听器，在释放对象时可能忽略关闭监听器导致内存泄漏。

**如何避免：**

1. static的合理使用，一般用来修饰基本数据类型或者轻量级对象，尽量避免修复集合或者大对象，常用作修饰全局配置项、工具类方法、内部类。
2. 在使用静态类/匿名类的时候，尽量避免使用非静态类/匿名类，因为非静态类/匿名类含有隐式对外部类的引用。而静态内部类/匿名类不会隐式的持有外部类引用，外部类会以正常的方式回收，如果你想在静态内部类/匿名类中使用外部类的属性或方法时，可以显示的持有一个弱引用。
3. 各种资源连接的使用结束之后，及时的将其关闭。

### 哪些区域会出现OutOfMemory，如何排查？（用友Java）

`除了程序计数器，其他内存区域都有 OOM 的风险。`

- 栈一般经常会发生 StackOverflowError，比如 32 位的 windows 系统单进程限制 2G 内存，无限创建线程就会发生栈的 OOM
- Java 8 常量池移到堆中，溢出会出 java.lang.OutOfMemoryError: Java heap space，设置最大元空间大小参数无效；
- 堆内存溢出，报错同上，这种比较好理解，GC 之后无法在堆中申请内存创建对象就会报错；
- `方法区 OOM`，经常会遇到的是动态生成大量的类、jsp 等；

- `直接内存 OOM`，涉及到 -XX:MaxDirectMemorySize 参数和 Unsafe 对象对内存的申请。

排查 OOM 的方法：

- 增加两个参数 ==-XX:+HeapDumpOnOutOfMemoryError 和-
  XX:HeapDumpPath=/tmp/heapdump.hprof==，当 OOM 发生时自动 dump 堆内存信息到指定目录；
- 同时 `jstat` 查看监控 JVM 的内存和 GC 情况，先观察问题大概出在什么区域；
- 使用 MAT 工具载入到 dump 文件，分析大对象的占用情况，比如 HashMap 做缓存未清理，时间长了就会内存溢出，可以把改为弱引用 。

### 谈谈JVM中的常量池？

JVM常量池主要分为**Class文件常量池**、**运行时常量池**，**全局字符串常量池**，以及**基本类型包装类对象常量池**。

- <font color='red'>Class文件常量池</font>：class文件是一组以字节为单位的二进制数据流，在java代码的编译期间，我们编写的java文件就被编译为.class文件格式的二进制数据存放在磁盘中，其中就包括class文件常量池。
- <font color='red'>运行时常量池</font>：运行时常量池相对于class常量池一大特征就是具有动态性，java规范并不要求常量只能在运行时才产生，也就是说运行时常量池的内容并不全部来自class常量池，在运行时可以通过代码生成常量并将其放入运行时常量池中，这种特性被用的最多的就是`String.intern()`。
- <font color='red'>全局字符串常量池</font>：字符串常量池是JVM所维护的一个字符串实例的引用表，在HotSpot VM中，它是一个叫做`StringTable的全局表`。在字符串常量池中维护的是字符串实例的引用，底层C++实现就是一个Hashtable。这些被维护的引用所指的字符串实例，被称作”被驻留的字符串”或”interned string”或通常所说的”进入了字符串常量池的字符串”。 
- <font color='red'>基本类型包装类对象常量池</font>：java中基本类型的包装类的大部分都实现了常量池技术，这些类是Byte, Short, Integer,Long,Character,Boolean,另外两种浮点数类型的包装类则没有实现。另外上面这5种整型的包装类也只是在对应值小于等于127时才可使用对象池，也即对象不负责创建和管理大于127的这些类的对象。

### 分析进程CPU占用飙升的原因？

1. **使用top命令查看CPU占用高的进程号**

<img src="https://img-blog.csdnimg.cn/20201202160733340.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpbmdqaWFubWlu,size_16,color_FFFFFF,t_70#pic_center">

2. **根据进程号找到CPU占用高的线程**

如：使用命令top -H -p (其中要换成第一步找到的进程号)

<img src="https://img-blog.csdnimg.cn/20201202160807191.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpbmdqaWFubWlu,size_16,color_FFFFFF,t_70#pic_center">

3. **导出java进程执行堆栈，并找到对应的线程**
   1. 使用jstack > jstack_xxx.txt (其中要换成第一步找到的进程号)
   2. 从第二步中的PID中找出一个CPU占用高的线程号，把它转成16进制，比如3261转成CBD
   3. 从导出的堆栈信息里找到nid为cbd的线程堆栈

<img src="https://img-blog.csdnimg.cn/20201202160852745.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpbmdqaWFubWlu,size_16,color_FFFFFF,t_70#pic_center">

4. **从堆栈里找到对应的代码执行类和方法**

若代码为业务代码，则需要具体分析代码，找出代码中死循环或接近死循环的地方，并修正；定位结束；若堆栈信息为gc线程（类似下图），则需要进行下一步

<img src="https://img-blog.csdnimg.cn/20201202160930591.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpbmdqaWFubWlu,size_16,color_FFFFFF,t_70#pic_center">

5. **dump出java进程的堆对象使用情况**

使用jmap -histo > jmap_xxx.txt

<img src="https://img-blog.csdnimg.cn/20201202161013738.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RpbmdqaWFubWlu,size_16,color_FFFFFF,t_70#pic_center">

找出量比较大的、且跟业务有关的对象，找到这些对象创建的地方进行分析；一般需要持续创建大量的对象，使得内存不够用时，才会频繁触发gc进行回收，gc回收时jvm有停顿，CPU也占用很高。

线程之间的切换，是很耗费性能的，所以带来CPU飙升.新生代设置过小，也会频繁触发gc。有大对象始终根节点路径可达，无法释放,jvm在疯狂的Full GC。

### 跨代引用怎么解决？

**解释**：**老年代有些引用着年轻代的某些对象** （也就是老年代的对象里面有个成员变量是在年轻代中）

遍历整个老年代的GC Roots 然后再逐个扫描新生代中的对象，因为太耗费时间和性能了，显示是不可能的。

在新生代引入记录集（Remember Set）的数据结构，避免整个老年代都加入GC Roots的扫描范围。

hotSpot使用的一种叫做`卡表（cardTable）`的方式实现记录集，也是目前最常用的一种方式，它就是Remember Set的一种实现。

`卡表类似于一个数组，每个元素都会存放卡页的地址，在老年代会开辟一个一个的空间来存放卡页。`

每个卡页都会存放一个或多个对象 ，`只要有一个对象存在跨代引用 ，那么卡页标示就为1`，表示卡页里面有对象引用了年轻代。

在年轻代GC时，会去查询数组如果有标示1的元素那么就会查询到卡页，然后全部做为GC Roots的对象。

卡表的维护：卡页会变脏，那么这个维护的关系是什么时候进行的？**在引用的字段赋值时，HotSpot使用写屏障来维护卡表的状态**。

### 调用System.gc()是否会立即回收？

我们调用System.gc()的时候，其实并不会马上进行垃圾回收，甚至不一定会执行垃圾回收，查看系统源码可以看到

```java
/**
     * Indicates to the VM that it would be a good time to run the
     * garbage collector. Note that this is a hint only. There is no guarantee
     * that the garbage collector will actually be run.
     */
public static void gc() {
    boolean shouldRunGC;
    synchronized(lock) {
        shouldRunGC = justRanFinalization;
        if (shouldRunGC) {
            justRanFinalization = false;
        } else {
            runGC = true;
        }
    }
    if (shouldRunGC) {
        Runtime.getRuntime().gc();
    }
}
```

也就是`justRanFinalization=true`的时候才会执行，查找发现当调用runFinalization()的时候`justRanFinalization`变为`true`，下面为`runFinalization()`源码

```java
/**
* Provides a hint to the VM that it would be useful to attempt
* to perform any outstanding object finalization.
*/
public static void runFinalization() {
        boolean shouldRunGC;
        synchronized(lock) {
            shouldRunGC = runGC;
            runGC = false;
        }
        if (shouldRunGC) {
            Runtime.getRuntime().gc();
        }
        Runtime.getRuntime().runFinalization();
        synchronized(lock) {
            justRanFinalization = true;
        }
}
```

当我们直接调用`System.gc()`只会把这次gc请求记录下来，等到`runFinalization=true`的时候才会先去执行GC，`runFinalization=true`之后会在允许一次system.gc()，之后在call System.gc()还会重复上面的行为，
所以System.gc()要跟System.runFinalization()一起搭配使用才好。

> ```java
> // 强制调用gc释放内存
> System.gc();
> System.runFinalization();
> ```

### 老年代空间担保规则？

当新生代被分配了大对象(该对象大小可以通过参数设置)，或者经过Minor GC后，存活下来的对象，Survivor区放不下，那么这些对象都会被分配到老年代。

老年代空间也是有限的，既然不是无限大，那么老年代在担保前也得自己掂量下，自己是不是吃的下那些要分配给自己的对象。

需要遵守的规则：

- 在执行任何一次Minor GC前，JVM都会检查一下老年代的的可用内存空间，然后和新生代中的所有对象的大小总和做个比较，如果大于新生代中的所有对象的大小总和，那么就可以保证Minor GC后，即使新生代中所有的对象都存活下来，Survivor区放不下，老年代也是能够完全分配下这些对象的。如果老年代的的可用内存空间是小于新生代中的所有对象的大小总和的，那么就要继续走第二步的判断。
- 第二步判断，要看看是否设置了`“-XX:-HandlePromotionFailure”`参数，该参数的作用在于会多加一步判断规则：**判断老年代的的可用内存空间是否大于之前每一次Minor GC后进入老年代的对象的平均大小**。如果不加这个参数或者这个参数判断失败，同时老年代的的可用内存空间小于新生代中的所有对象的大小总和，就会直接进行Full GC，尽量先腾出一些老年代空间来，然后再触发Minor GC，尽最大努力防止出现OOM。如果“-XX:-HandlePromotionFailure”参数判断是成功的，那么就走第三步。
- 第三步就可以试着进行Minor GC了，毕竟该做的判断做了和该满足的条件都有了，此时Minor GC后，如果存活的对象大小小于Survivor区的大小，那么存活的对象直接进入Survivor区。如果存活的对象大小大于Survivor区的大小，却小于老年代大小，那么存活的对象直接进入老年代。最极端的情况就是存活的对象大小大于Survivor区的大小，同时也大于老年代大小，那么此时机会触发一次Full GC，对老年代和新生代统一做一次垃圾回收，腾出空间，方便让Minor GC后存活的对象可以进入老年代。最差的情况就是即使经过了Full GC，老年代空间也还是不够，那么就会爆出OOM了。

### 类加载器的分类？

1. **启动类加载器：**这个类加载器负责放在<font color='red'><JAVA_HOME>\lib</font>目录中的，或者被-Xbootclasspath参数所指定的路径中的，并且是虚拟机识别的类库，用户无法直接使用。
2. **扩展类加载器：**这个类加载器由sun.misc.Launcher$AppClassLoader实现。它负责<font color='red'><JAVA_HOME>\lib\ext</font>目录中的，或者被java.ext.dirs系统变量所指定的路径中的所有类库，用户可以直接使用。
3. **应用程序类加载器：**这个类由sun.misc.Launcher$AppClassLoader实现，是ClassLoader中getSystemClassLoader()方法的返回值，它负责<font color='red'>用户路径（ClassPath）所指定的类库</font>，用户可以直接使用。如果用户没有自己定义类加载器，默认使用这个。

### 什么是双亲委派模型？如何打破？

当一个类加载器收到一个类加载的请求，他首先不会尝试自己去加载，而是将这个请求委派给父类加载器去加载，只有父类加载器在自己的搜索范围类查找不到给类时，子加载器才会尝试自己去加载该类；

为了防止内存中出现多个相同的字节码；因为如果没有双亲委派的话，用户就可以自己定义一个
java.lang.String类，那么就无法保证类的唯一性。

> **如何打破双亲委派模型？**
>
> <font color='red'>自定义类加载器，继承ClassLoader类，重写loadClass方法和findClass方法</font>
>
> **列举一些你知道的打破双亲委派模型的例子？**
>
> - Tomcat，应用的类加载器优先自行加载应用目录下的 class，并不是先委派给父加载器，加载不了才委派给父加载器
>   - 对于各个 webapp中的 class和 lib，需要相互隔离，不能出现一个应用中加载的类库会影响另一个应用的情况，而对于许多应用，需要有共享的lib以便不浪费资源
>   - 与 jvm一样的安全性问题。使用单独的 classloader去装载 tomcat自身的类库，以免其他恶意或无意的破坏
>   - 热部署
> - JDK 9，`Extension ClassLoader 被 Platform ClassLoader 取代`，当平台及应用程序类加载器收到类加载请求，在委派给父加载器加载前，要先判断该类是否能够归属到某一个系统模块中，如果可以找到这样的归属关系，就要优先委派给负责那个模块的加载器完成加载。`打破的原因，是为了添加模块化的特性`。

### JVM调优的命令讲下？

- **jps：**JVM Process Status Tool,显示指定系统内所有的HotSpot虚拟机进程。
- **jstat：**jstat(JVM statistics Monitoring)是用于监视虚拟机运行时状态信息的命令，它可以显示出虚拟机进程中的类装载、内存、垃圾收集、JIT编译等运行数据。
- **jmap：**jmap(JVM Memory Map)命令用于生成heap dump文件，如果不使用这个命令，还阔以使用`-XX:+HeapDumpOnOutOfMemoryError`参数来让虚拟机出现OOM的时候·自动生成dump文件。jmap不仅能生成dump文件，还阔以查询finalize执行队列、Java堆和永久代的详细信息，如当前使用率、当前使用的是哪种收集器等。
- **jhat：**jhat(JVM Heap Analysis Tool)命令是与jmap搭配使用，用来分析jmap生成的dump，jhat内置了一个微型的HTTP/HTML服务器，生成dump的分析结果后，可以在浏览器中查看。在此要注意，一般不会直接在服务器上进行分析，因为jhat是一个耗时并且耗费硬件资源的过程，一般把服务器生成的dump文件复制到本地或其他机器上进行分析。
- **jstack：**jstack用于生成java虚拟机当前时刻的线程快照。jstack来查看各个线程的调用堆栈，就可以知道没有响应的线程到底在后台做什么事情，或者等待什么资源。 如果java程序崩溃生成core文件，jstack工具可以用来获得core文件的java stack和native stack的信息，从而可以轻松地知道java程序是如何崩溃和在程序何处发生问题。

### 内存模型是怎么解决缓存一致性问题的？

缓存一致性协议（Cache Coherence Protocol），最出名的就是Intel 的MESI协议，MESI协议保证了每个缓存中使用的共享变量的副本是一致的。**MESI协议，可以保证缓存的一致性，但是无法保证实时性。**

MESI的核心的思想是：当CPU写数据时，如果发现操作的变量是共享变量，即在其他CPU中也存在该变量的副本，会发出信号通知其他CPU将该变量的缓存行置为无效状态，因此当其他CPU需要读取这个变量时，发现自己缓存中缓存该变量的缓存行是无效的，那么它就会从内存重新读取。

- **M（Modified）**：修改缓存，当前CPU缓存已经被修改，表示已经和内存中的数据不一致了
- **I（Invalid）**：失效缓存，说明CPU的缓存已经不能使用了
- **E（Exclusive）**：独占缓存，当前cpu的缓存和内存中数据保持一直，而且其他处理器没有缓存该数据
- **S（Shared）**：共享缓存，数据和内存中数据一致，并且该数据存在多个cpu缓存中

<font color='blue'>CPU读取遵循规则：</font>

- 如果缓存的状态是I，那么就从内存中读取，否则直接从缓存读取
- 如果缓存处于M或者E的CPU嗅探到其他CPU有读的操作，就把自己的缓存写入到内存，并把自己的状态设置为S
- 只有缓存状态是M或E的时候，CPU才可以修改缓存中的数据，修改后，缓存状态变为MC

-------

缓存一致性（Cache Coherence），解决是多个缓存副本之间的数据的一致性问题。

内存一致性（Memory Consistency），保证的是多线程程序访问内存时可以读到什么值。

### 说下Happens-Before规则？

<font color='red'>Java 内存模型</font>（下文简称 JMM）就是在底层处理器内存模型的基础上，定义自己的多线程语义。它明
确指定了一组排序规则，来保证线程间的可见性。

这一组规则被称为<font color='red'> Happens-Before</font>, JMM 规定，要想保证 B 操作能够看到 A 操作的结果（无论它们是
否在同一个线程），那么 A 和 B 之间必须满足 Happens-Before 关系。

happens-before 表达的并不是说前面一个操作发生在后面一个操作的前面，尽管从程序员编程角度来看也并不会出错，但它其实表达的是，**前一个操作的结果对后续操作时可见的，目的是为了在不改变程序执行结果的前提下，尽可能地提高程序执行的并行度。**在JMM(JAVA内存模型)中，如果**一个操作执行的结果需要对另一个操作可见**，那么这两个操作之间必须存在happens-before关系。

1. <font color='green'>程序顺序规则</font>，**一个线程中，按照程序顺序，前面的操作 Happens-Before 于后续的任意操作**

2. <font color='green'>监视器锁规则</font>，**对一个锁的解锁，happens-before于随后对这个锁的加锁，这里的锁就是Java中的synchronized**

3. <font color='green'>volatile变量规则</font>，**对一个volatile域的写，happens-before于任意后续对这个volatile域的读**

4. <font color='green'>传递规则</font>，**如果A happens-before B，且B happens-before C，那么A happens-before C**

5. <font color='green'>线程start规则</font>，**这条是关于线程启动的。它是指主线程 A 启动子线程 B 后，子线程 B 能够看到主线程A在启动子线程 B 前的操作**

6. <font color='green'>线程join规则</font>，**如果线程A执行操作ThreadB.join()并成功返回，那么线程B中的任意操作happens-before于线程A从ThreadB.join()操作成功返回**

7. <font color='green'>对象finalize规则</font>，**一个对象的初始化完成先行发生于他的finalize()方法的开始**

8. <font color='green'>线程interrupt规则</font>，**对线程interrupt()方法的调用先行发生于被中断线程的代码检测到中断事件的发生**

<font color='blue'>总结：在 Java 语言里面，Happens-Before 的语义本质上是一种可见性，A Happens-Before B 意味着 A 事件对 B 事件来说是可见的，无论 A 事件和 B 事件是否发生在同一个线程里</font>

## Java并发

### 进程和线程的区别？

**根本区别：**进程是操作系统资源分配的基本单位，而线程是处理器任务调度和执行的基本单位

**资源开销：**每个进程都有独立的代码和数据空间（程序上下文），程序之间的切换会有较大的开销；线
程可以看做轻量级的进程，同一类线程共享代码和数据空间，每个线程都有自己独立的运行栈和程序计数器（PC），线程之间切换的开销小。

**包含关系：**一个进程包含多个多个线程，在同⼀进程中，线程的切换不会引起进程切换，从⼀个进程中的线程切换到另⼀个进程中的线程时，会引起进程切换。

**内存分配：**同一进程的线程共享本进程的地址空间和资源，而进程之间的地址空间和资源是相互独立的

**影响关系：**一个进程崩溃后，在保护模式下不会对其他进程产生影响，但是一个线程崩溃整个进程都死
掉，所以多进程要比多线程健壮。

**执行过程：**每个独立的进程有程序运行的入口、顺序执行序列和程序出口。但是线程不能独立执行，必
须依存在应用程序中，由应用程序提供多个线程执行控制，两者均可并发执行。

**通信方面：**线程间可以通过直接读写同⼀进程中的数据进⾏通信，但是进程通信需要借助 IPC。

### sleep(0)的作用是什么？

**就是线程等待的意思，触发操作系统立刻重新进行一次CPU竞争。**

由于Java采用抢占式的线程调度算法，因此可能会出现某条线程常常获取到CPU控制权的情况，为了让某些优先级比较低的线程也能获取到CPU控制权，可以**使用Thread.sleep(0)手动触发一次操作系统分配时间片的操作**，这也是平衡CPU控制权的一种操作。功能等价于Object类中的wait()方法，导致当前的线程等待，直到其他线程调用此对象的 notify() 方法或 notifyAll() 唤醒方法，但是Thread.sleep(0)不需要被唤醒。

### 浅谈AtomicInteger原理？

```java
public class AtomicInteger extends Number implements java.io.Serializable {
    private static final long serialVersionUID = 6214790243416807050L;
    // setup to use Unsafe.compareAndSwapInt for updates
    private static final Unsafe unsafe = Unsafe.getUnsafe();
    private static final long valueOffset;
    static {
        try {
            valueOffset = unsafe.objectFieldOffset
                (AtomicInteger.class.getDeclaredField("value"));
        } catch (Exception ex) { throw new Error(ex); }
    }
    private volatile int value;
}
```

- 从 AtomicInteger 的内部属性可以看出，它依赖于Unsafe 提供的一些底层能力，进行底层操作；如根据valueOffset代表的该变量值在内存中的偏移地址，从而获取数据的
- 变量value用volatile修饰，保证了多线程之间的内存可见性

```java
public final int getAndIncrement() {
    return unsafe.getAndAddInt(this, valueOffset, 1);
}
//unsafe.getAndAddInt
public final int getAndAddInt(Object var1, long var2, int var4) {
    int var5;
    do {
        var5 = this.getIntVolatile(var1, var2);
    } while(!this.compareAndSwapInt(var1, var2, var5, var5 + var4));

    return var5;
}
```

以`getAndIncrement`为例，说明原子操作的过程

- 假设线程1和线程2通过getIntVolatile拿到value的值都为1，线程1被挂起，线程2继续执行
- 线程2在compareAndSwapInt操作中由于预期值和内存值都为1，因此成功将内存值更新为2
- 线程1继续执行，在compareAndSwapInt操作中，预期值是1，而当前的内存值为2，CAS操作失败，什么都不做，返回false
- 线程1重新通过getIntVolatile拿到最新的value为2，再进行一次compareAndSwapInt操作，这次操作成功，内存值更新为3

### 讲下semaphore,cyclicBarrier,countDownLatch的使用场景与区别?

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/countdownlatch.png">

#### CountDownLatch

CountDownLatch是一个同步工具类，它允许一个或多个线程一直等待，直到其他线程的操作执行完毕再执行。

> 对于线程来说，`CountDownLatch`会阻塞线程的运行，只有当`CountDownLatch`内部记录的值减小为`0`，线程才能继续向前执行。
>
> `CountDownLatch`底层通过`AQS`实现，`AQS`的一般使用方式就是以内部类的形式继承它，`CountDownLatch`就是这么使用它的。在`CountDownLatch`内部有一个内部类`Sync`，继承自`AQS`，并重写了`AQS`加锁解锁的方法，并通过`Sync`的对象，调用`AQS`的方法，阻塞线程的运行。我们知道，创建一个`CountDownLatch`对象时，需要传入一个整数值`count`，只有当`count`被减小为`0`时线程才能通过`await`方法，否则将被`await`阻塞。这里实际上是这样的：**当线程运行到await方法时，需要去获取锁（锁由AQS实现），若count不为0，则线程就会获取锁失败，被阻塞；若count为0，则就能顺利通过**。`CountDownLatch`是一次性的，因为没有方法可以增加`count`的值，也就是说，一旦`count`被减小为`0`，则之后就一直是`0`了，也就再也不能阻塞线程了。
>
> 内部类Sync的实现非常简单，它只实现了`AQS`中的两个方法，即**tryAcquireShared**以及**tryReleaseShared**，这两个方法是`AQS`提供的使用共享锁的接口。这也就表明，`CountDownLatch`实际上是一种共享锁机制，即锁可以同时被多个线程获取，这个不难理解，因为一旦`count`被减小为0，则所有线程通过`await`方法时，都能够顺利通过，不会因为获取不到锁而阻塞。而且从上面的实现中我们可以看到，`Sync`直接将`count`值作为`AQS`的`state`的值，只有`state`的值为0，线程才能获取锁，也就是获得执行权限。

```java
import java.util.concurrent.CountDownLatch;
public class CountDownLatchDemo {
    public static void main(String[] args) throws InterruptedException {
        CountDownLatch countDownLatch = new CountDownLatch(1);
        new Thread(()->{
            System.out.println("----------");
            countDownLatch.countDown();
        }).start();
        countDownLatch.await();
        System.out.println("==========");
    }
}
```

CountDownLatch的构造函数接收一个int类型的参数作为计数器，可以视自己的需求设置一个合法的int数值，执行一次countDown()方法，计数器就会减1，await()方法会阻塞线程，直到线程计数减少为0才会继续运行。如果说为了防止某一个线程卡死导致await()一直阻塞的话，也可以调用await(long timeout, TimeUnit unit)方法设定超时时间，到达超时时间之后，即使计数器不到0，也可以继续执行后面的代码。

#### CyclicBarrier

CyclicBarrier的字面意思是可循环使用（Cyclic）的屏障（Barrier）。它要做的事情是，让一 组线程到达一个屏障（也可以叫同步点）时被阻塞，直到最后一个线程到达屏障时，屏障才会 开门，所有被屏障拦截的线程才会继续运行。CyclicBarrier可以用于多线程计算数据，最后合并计算结果的场景。

```java
import java.util.concurrent.CyclicBarrier;
public class CyclicbarrierDemo {
    static CyclicBarrier cyclicBarrier = new CyclicBarrier(2);
    public static void main(String[] args) {
        new Thread(()-> {
            try {
                cyclicBarrier.await();
            } catch (Exception e) {
                e.printStackTrace();
            }
            System.out.println("我是线程t1");
        },"t1").start();
        new Thread(()-> {
            try {
                cyclicBarrier.await();
            } catch (Exception e) {
                e.printStackTrace();
            }
            System.out.println("我是线程t2");
        },"t2").start();
        System.out.println("主线程==end");
    }
}
//结果
主线程==end
我是线程t1
我是线程t2
//t1和t2的输出结果是随机的
```

1. 对于指定int类型的计数值 ，若由于某种原因，没有足够的线程调用 CyclicBarrier 的await()方法，则所有调用 await 的线程都会被阻塞
2. 若有多余线程执行了await()方法，那么最后一个到达屏障的线程会被阻塞
3. 通过` reset 重置计数`，会使得进入 await 的线程出现BrokenBarrierException；我们可以通过捕获异常重新处理业务逻辑
4. 如果采用是 CyclicBarrier(int parties, Runnable barrierAction) 构造方法，执行 barrierAction 操作的是最后一个到达的线程。

> `CountDownLatch和CyclicBarrier区别`
>
> **CountDownLatch的计数器只能使用一次，而CyclicBarrier的计数器可以使用reset()方法重置。**所以CyclicBarrier能处理更为复杂的业务场景。例如，如果计算发生错误，可以重置计数 器，并让线程重新执行一次

#### Semaphore

Semaphore可以控制同时访问的线程个数，通过 acquire 获取一个许可，如果没有就等待，通过 release 释放一个许可，有点类似`限流`的作用。

```java
import java.util.concurrent.Semaphore;
import java.util.concurrent.TimeUnit;
public class SemaphoreDemo {
    public static void main(String[] args) {
        Semaphore semaphore=new Semaphore(2);
        for(int i=1;i<=5;i++){
            new Car(i,semaphore).start();
        }
    }
}
class Car extends Thread{
    private int num;
    private Semaphore semaphore;
    public Car(int num, Semaphore semaphore) {
        this.num = num;
        this.semaphore = semaphore;
    }
    @Override
    public void run() {
        try {
            semaphore.acquire();//获取一个许可
            System.out.println("第"+num+"辆车进来了");

            TimeUnit.SECONDS.sleep(2);
            System.out.println("第"+num+"辆车出去了");
            semaphore.release();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

总结：`CountDownLatch和CyclicBarrier在一定场景下是可以替换使用的，而Semaphore一般用于限流。`

### 什么是逃逸分析？

<font color='green'>逃逸是指在某个方法之内创建的对象，除了在方法体之内被引用之外，还在方法体之外被其它变量引用到；这样带来的后果是在该方法执行完毕之后，该方法中创建的对象将无法被GC回收，由于其被其它变量引用。正常的方法调用中，方法体中创建的对象将在执行完毕之后，将回收其中创建的对象；故由于无法回收，即成为逃逸。</font>

```java
/**
* 无逃逸
*/
void test01() {
    String test1 = "test1";
}
String test2;
    /**
     * 逃逸
     */
void test02() {
    test2 = "test2";
}
```

在方法内的变量不会逃逸，在方法外声明的对象会发生逃逸，脱离了方法的控制，方法结束时变量没有结束

#### 分类

**方法逃逸：**

- 定义 一个对象在方法中被定义，但却被方法以外的其他代码使用
- 场景 如传参到其他方法中等可能导致此情况发生

**线程逃逸：**

- 定义 一个对象由某个线程在方法中被定义，但却被其他线程访问。
- 场景 如类变量、公用的或有get、set方法的实例变量等

#### 三种状态

**全局逃逸：**一个对象的引用掏出了方法或者线程。例如：一个对象的引用赋值给一个类变量，或者这个对象的利用引用作为方法的返回这返回给了调用方法。

**参数级逃逸：**方法调用过程中，传递对象给另一个方法

**没有逃逸：**一个可以进行标量替换的对象，可以将这个对象不分配在传统的堆上

#### 参数设置

```shell
-XX:+DoEscapeAnalysis   //使用 （JDK8中，逃逸分析默认开启。）
-XX:-DoEscapeAnalysis   //不用
-XX:+PrintEscapeAnalysis //结果展示
```

### 逃逸分析有什么优化技术？

普通对象在堆中分配，各线程共享。但有GC消耗。当确定对象不会发生方法逃逸时，可在线程栈上分配对象。此时对象生命周期和方法相同，随栈帧出栈时即可销毁，不需要GC了。

-----

**同步消除：**线程同步降低了并发性和程序性能。

**锁消除：**当确定对象不会发生线程逃逸时，可消除该对象不必要的同步操作（永不会竞争）。具体来说，JVM在编译器运行时会扫描代码，当检查到那些不可能存在共享区竞争，但却有互斥同步的代码，直接将这样的多此一举的同步消除

**锁粗化：**JVM针对那些反复在一段代码中对同一对象加锁的情况，将同步锁放在最外层包住这里面的多次同步锁，同时取消内部的同步锁

----

**标量替换：**标量是指一个数据无法分解成更小的数据，基础类型的数据都算是标量，对象可以被分解成其他的成员变量，所以说变量不是标量，那么标量替换是指在运行期间，不必要创建对象，而是改成创建对象的成员变量，不仅可以让对象成员在栈上分配和读写之外，还可以为后一步的优化技术创造了条件。

### start()和run()方法区别？

`run方法是Runnable接口中定义的，start方法是Thread类定义的。 `所有实现Runnable的接口的类都需要重写run方法，run方法是线程默认要执行的方法，有底层源码可知是绑定操作系统的，也是线程执行的入口。 

start方法是Thread类的默认执行入口，Thread又是实现Runnable接口的。要使线程Thread启动起来，需要通过start方法，表示线程可执行状态，调用start方法后，则表示Thread开始执行，此时run变成了Thread的默认要执行普通方法。 

`通过start(）方法，直接调用run()方法可以达到多线程的目的`。通常，系统通过调用线程类的start()方法来启动一个线程，此时该线程处于`就绪状态`，而非运行状态，这也就意味着这个线程可以被JVM来调度执行。

在调度过程中，JVM会通过调用线程类的run()方法来完成试机的操作，当run()方法结束之后，此线程就会终止。 如果直接调用线程类的run()方法，它就会被当做一个普通的函数调用，程序中任然只有主线程这一个线程。也就是说，start()方法可以异步地调用run()方法，但是直接调用run()方法确实同步的，因此也就不能达到多线程的目的。 

<font color='blue'>run()和start()的区别可以用一句话概括：单独调用run()方法，是同步执行；通过start()调用run()，是异步执行。</font>

> **Thread类中run()和start()方法的区别如下**：
>
> - run()方法:在本线程内调用该Runnable对象的run()方法，可以重复多次调用；
> - start()方法:启动一个线程，调用该Runnable对象的run()方法，不能多次启动一个线程；
>
> <font color='red'>start方法：</font>
>
> 通过该方法启动线程的同时也创建了一个线程，真正实现了多线程。无需等待run()方法中的代码执行完毕，就可以接着执行下面的代码。此时start()的这个线程处于就绪状态，当得到CPU的时间片后就会执行其中的run()方法。这个run()方法包含了要执行的这个线程的内容，run()方法运行结束，此线程也就终止了。
>
> <font color='red'>run方法：</font>
>
> 通过run方法启动线程其实就是调用一个类中的方法，当作普通的方法的方式调用。并没有创建一个线程，程序中依旧只有一个主线程，必须等到run()方法里面的代码执行完毕，才会继续执行下面的代码，这样就没有达到写线程的目的。

### execute()和submit()？

- execute()方法用于提交不需要返回值的任务，所以无法判断任务是否被线程池执行成功与否；
- submit()方法用于提交需要返回值的任务。线程池会返回一个 Future 类型的对象，通过这个 Future 对象可以判断任务是否执行成功（可以通过 Future 的 get()方法来获取返回值，get()方法会阻塞当前线程直到任务完成，而使用 get（long timeout，TimeUnit unit）方法则会阻塞当前线程一段时间后立即返回，这时候有可能任务没有执行完。）

### CopyOnWriteArrayList介绍下？

在很多应用场景中，读操作可能会远远大于写操作。由于读操作根本不会修改原有的数据，因此如果每次读取都进行加锁操作，其实是一种资源浪费。我们应该允许多个线程同时访问 List 的内部数据，毕竟读操作是线程安全的。

JDK中提供了 `CopyOnWriteArrayList` 类，相比于在读写锁的思想又更进一步。为了将读取的性能发挥到极致，`CopyOnWriteArrayList 读取是完全不用加锁的`，并且更厉害的是：`写入也不会阻塞读取操作`，只有写入和写入之间需要进行同步等待，读操作的性能得到大幅度提升。

`CopyOnWriteArrayList` 类的所有可变操作（add，set等等）都是通过`创建底层数组的新副本来实现的`。当 List 需要被修改的时候，并不直接修改原有数组对象，而是对原有数据进行一次拷贝，将修改的内容写入副本中。写完之后，再将修改完的副本替换成原来的数据，这样就可以保证写操作不会影响读操作了。

从 `CopyOnWriteArrayList` 的名字可以看出，`CopyOnWriteArrayList` 是满足 `CopyOnWrite` 的 ArrayList，所谓 `CopyOnWrite` 的意思：就是对一块内存进行修改时，不直接在原有内存块中进行写操作，而是将内存拷贝一份，在新的内存中进行写操作，写完之后，再将原来指向的内存指针指到新的内存，原来的内存就可以被回收。

1. CopyOnWriteArrayList 读取操作的实现：读取操作没有任何同步控制和锁操作，理由就是内部数组 array 不会发生修改，只会被另外一个 array 替换，因此可以保证数据安全。

```java
/** The array, accessed only via getArray/setArray. */
private transient volatile Object[] array;

public E get(int index) {
    return get(getArray(), index);
}

@SuppressWarnings("unchecked")
private E get(Object[] a, int index) {
    return (E) a[index];
}

final Object[] getArray() {
    return array;
}
```

2. CopyOnWriteArrayList 写入操作的实现：CopyOnWriteArrayList 写入操作 `add()` 方法在添加集合的时候加了锁，保证同步，避免多线程写的时候会 copy 出多个副本。

```java
/**
     * Appends the specified element to the end of this list.
     *
     * @param e element to be appended to this list
     * @return {@code true} (as specified by {@link Collection#add})
     */
public boolean add(E e) {
    final ReentrantLock lock = this.lock;
    lock.lock();  // 加锁
    try {
        Object[] elements = getArray();
        int len = elements.length;
        Object[] newElements = Arrays.copyOf(elements, len + 1);  // 拷贝新数组
        newElements[len] = e;
        setArray(newElements);
        return true;
    } finally {
        lock.unlock();  // 释放锁
    }
}
```

### 进程/线程同步的方法？（用友Java）

1. `临界区`：当多个线程访问一个独占性共享资源时，可以使用临界区对象。拥有临界区的线程可以访问被保护起来的资源或代码段，其他线程若想访问，则被挂起，直到拥有临界区的线程放弃临界区为止以此达到用原子方式操作共享资源的目的。
2. `事件`：事件机制，则允许一个线程在处理完一个任务后，主动唤醒另外一个线程执行任务。
3. `互斥量`：互斥对象和临界区对象非常相似，只是其允许在进程间或者线程间使用，而临界区只限制与同一进程的各个线程之间使用，但是更节省资源，更有效率。
4. `信号量`：当需要一个计数器来限制可以使用某共享资源的线程数目时，可以使用“信号量”对象。

<img src="https://img-blog.csdn.net/20171121130628916">

------------

**区别：**

- 互斥量与临界区的作用非常相似，但互斥量是可以命名的，也就是说`互斥量可以跨越进程使用，但创建互斥量需要的资源更多`，所以如果只为了在进程内部是用的话使用临界区会带来速度上的优势并能够减少资源占用量 。因为互斥量是跨进程的互斥量一旦被创建，就可以通过名字打开它。
- **互斥量，信号量，事件都可以被跨越进程使用来进行同步数据操作**。

### synchronized和volitale区别？（用友Java）

- volatile关键字是线程同步的`轻量级实现`，所以volatile性能肯定比synchronized关键字要好。
- `volatile关键字只能用于变量`，而`synchronized关键字可以修饰方法以及代码块`。实际开发中使用 
  synchronized 关键字的场景还是更多一些。
- 多线程访问volatile关键字不会发生阻塞，而synchronized关键字可能会发生阻塞
- volatile关键字能保证数据的可见性，但`不能保证数据的原子性`；synchronized关键字两者都能保证
- **volatile关键字主要用于解决变量在多个线程之间的可见性，而 synchronized关键字解决的是多个线程之间访问资源的同步性**。 

### volitale的使用及原理大总结？

#### volatile的两层语义

1. volatile保证变量对所有线程的可见性：当volatile变量被修改，新值对所有线程会立即更新，或者理解为多线程环境下使用volatile修饰的变量的值一定是最新的。
   
2. jdk1.5以后volatile完全避免了指令重排优化，实现了有序性（场景：单例模式Double Check定义Singleton对象）。

#### volatile的原理

1. 获取JIT（即时Java编译器，把字节码解释为机器语言发送给处理器）的汇编代码，发现volatile多加了`lock addl`指令，这个操作相当于一个<font color='blue'>内存屏障</font>，使得lock指令后的指令不能重排序到内存屏障前的位置，这也是为什么JDK1.5以后可以使用双锁检测实现单例模式。

2. lock前缀的另一层意义是使得本线程工作内存中的volatile变量值立即写入到主内存中，并且使得其他线程共享的该volatile变量无效化，这样其他线程必须重新从主内存中读取变量值。

#### 如何禁止指令重排？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/20200704151144615.png">

#### volatile如何保证可见性？（用友Java）

被`volatile`关键字修饰的变量，在每个写操作之后，都会加入一条`store`内存屏障命令，此命令强制工作内存将此变量的最新值保存至主内存；在每个读操作之前，都会加入一条`load`内存屏障命令，此命令强制工作内存从主内存中加载此变量的最新值至工作内存。

#### volatile为什么不能保证原子性？

- `读取volatile变量到local`
- `修改变量值`
- `local值写回`
- 插入内存屏障，即lock指令，让其他线程可见

**前三步都是不安全的，取值和写回之间，不能保证没有其他线程修改。原子性需要锁来保证**。

### synchronized底层实现（用友Java）

JVM对于同步方法和同步代码块的处理方式不同，对于同步方法，JVM采用`ACC_SYNCHRONIZED`标记符来实现同步，而对于同步代码块，JVM则采用 `monitorenter`和`monitorexit` 这两个指令实现同步。

- **`ACC_SYNCHRONIZED`标记符**

方法级的同步是隐式的。同步方法的常量池中会有一个ACC_SYNCHRONIZED标志。当某个线程要访问某个方法的时候，会检查是否有ACC_SYNCHRONIZED标志，如果有设置，则需要先获得监视器锁，然后开始执行方法，方法执行之后再释放监视器锁。这时如果其他线程来请求执行方法，会因为无法获得监视器锁而被阻断住。值得注意的是，如果在方法执行过程中，发生了异常，并且方法内部并没有处理该异常，那么在异常被抛到方法外面之前监视器锁会被自动释放。

- **`monitorenter`和`monitorexit` 指令**

可以把执行monitorenter指令理解为加锁，执行monitorexit理解为释放锁。 每个对象维护着一个记录着被锁次数的计数器。未被锁定的对象的该计数器为0，当一个线程获得锁（执行monitorenter）后，该计数器自增变为 1 ，当同一个线程再次获得该对象的锁的时候，计数器再次自增。当同一个线程释放锁（执行monitorexit指令）的时候，计数器再自减。当计数器为0的时候。锁将被释放，其他线程便可以获得锁。

`为什么有两条monitorexit指令？`

编译器需要确保方法中调用过的每条monitorenter指令都要执行对应的monitorexit 指令。为了保证在方法异常时，monitorenter和monitorexit指令也能正常配对执行，编译器会自动产生一个异常处理器，它的目的就是用来执行异常的monitorexit指令。而`字节码中多出的monitorexit指令，就是异常结束时，被执行用来释放monitor的`。

==JVM就是根据该标示符来实现方法的同步的：当方法调用时，调用指令将会检查方法的 ACC_SYNCHRONIZED 访问标志是否被设置，如果设置了，执行线程将先获取monitor，获取成功之后才能执行方法体，方法执行完后再释放monitor==。

<font color='blue'>monitorenter ：</font>

每个对象有一个监视器锁（monitor）。当monitor被占用时就会处于锁定状态，线程执行monitorenter指令时尝试获取monitor的所有权，过程如下：

1. 如果monitor的进入数为0，则该线程进入monitor，然后将进入数设置为1，该线程即为monitor的所有者。
2. 如果线程已经占有该monitor，只是重新进入，则进入monitor的进入数加1.
3. 如果其他线程已经占用了monitor，则该线程进入阻塞状态，直到monitor的进入数为0，再重新尝试获取monitor的所有权。

<font color='blue'>monitorexit：</font>

执行monitorexit的线程必须是object ref所对应的monitor的所有者。

指令执行时，monitor的进入数减1，如果减1后进入数为0，那线程退出monitor，不再是这个monitor的所有者。其他被这个monitor阻塞的线程可以尝试去获取这个 monitor 的所有权。 

> 通过这两段描述，我们应该能很清楚的看出Synchronized的实现原理，`Synchronized的语义底层是通过一个monitor的对象来完成，其实wait/notify等方法也依赖于monitor对象`，这就是为什么只有在同步的块或者方法中才能调用wait/notify等方法，否则会抛出java.lang.IllegalMonitorStateException的异常的原因。

#### synchronized如何保证原子性？

**原子性：** 即一个操作或者多个操作 **要么全部执行并且执行的过程不会被任何因素打断**，要么就都**不执行**。

Java内存模型提供了字节码指令`monitorenter`和`monitorexit`来隐式的使用这两个操作，在synchronized块之间的操作是具备原子性的。

线程1在执行monitorenter指令的时候，会对Monitor进行加锁，加锁后其他线程无法获得锁，除非线程1主动解锁。即使在执行过程中，由于某种原因，比如CPU时间片用完，线程1放弃了CPU，但是它并没有进行解锁。而由于synchronized的锁是可重入的，下一个时间片还是只能被他自己获取到，还是会继续执行代码。直到所有代码执行完，这就保证了原子性。

#### synchronized如何保证有序性？

**有序性：** 程序执行的顺序按照代码的先后顺序执行。

在并发时，程序的执行可能会出现乱序。给人的直观感觉就是：写在前面的代码，会在后面执行。但是synchronized提供了有序性保证，这其实和`as-if-serial语义`有关。

`as-if-serial语义是指不管怎么重排序（编译器和处理器为了提高并行度），单线程程序的执行结果都不能被改变`。<font color='red'>编译器和处理器无论如何优化，都必须遵守as-if-serial语义。只要编译器和处理器都遵守了这个语义，那么就可以认为单线程程序是按照顺序执行的</font>，由于synchronized修饰的代码，同一时间只能被同一线程访问。那么可以认为是单线程执行的。所以可以保证其有序性。

#### synchronized如何保证可见性？

**可见性：** 当多个线程访问同一个变量时，一个线程修改了这个变量的值，其他线程能够立即看得到修改的值。

被`synchronized`修饰的代码，在开始执行时会加锁，执行完成后会进行解锁，但在一个变量解锁之前，必须先把此变量`同步回主存`中，这样解锁后，后续其它线程就可以访问到被修改后的值，从而保证可见性。

#### synchronized锁优化的方法？

1. <font color='red'>⾃适应⾃旋锁：</font>⾃旋的时间不固定，会根据上次⾃旋的时间以及当前持有锁的线程状态来决定；
2. <font color='red'>锁消除：</font>如果JVM明显检测到某段代码是线程安全的（⾔外之意：⽆锁也安全），JVM会安全地将
原有的锁消除掉；
3. <font color='red'>锁粗化：</font>默认情况下，总是推荐将同步块的作⽤范围限制得尽量⼩。但是如果⼀系列的连续操作都
对同⼀个对象反复的加锁和解锁，甚⾄加锁操作是出现在循环体中的，频繁的进⾏互斥同步操作会
导致不必要的性能损耗。JVM会将加锁的范围扩展（粗化），这就叫锁粗化；
4. <font color='red'>轻量级锁：</font>在⽆竞争的情况下使⽤CAS操作去消除同步使⽤的互斥量
5. <font color='red'>偏向锁：</font>在⽆竞争环境下，把整个同步都消除，CAS也不做

### 可重入锁可重入的原理（用友Java）？

**可重入解释：**当线程请求一个由其它线程持有的对象锁时，该线程会阻塞，而当线程请求由自己持有的对象锁时，如果该锁是重入锁，请求就会成功，否则阻塞。

**原理：**每一个锁关联一个线程持有者和计数器，当计数器为 0 时表示该锁没有被任何线程持有，那么任何线程都可能获得该锁而调用相应的方法；当某一线程请求成功后，JVM会记下锁的持有线程，并且将计数器置为 1；此时其它线程请求该锁，则必须等待；而该持有锁的线程如果再次请求这个锁，就可以再次拿到这个锁，同时计数器会递增；当线程退出同步代码块时，计数器会递减，如果计数器为 0，则释放该锁。

### 乐观锁和悲观锁？（用友Java）

**悲观锁：**总是假设最坏的情况，每次去拿数据的时候都认为别⼈会修改，所以每次在拿数据的时候都会上锁，这样别⼈想拿这个数据就会阻塞直到它拿到锁（共享资源每次只给⼀个线程使⽤，其它线程阻塞，⽤完后再把资源转让给其它线程）。传统的关系型数据库⾥边就⽤到了很多这种锁机制，⽐如⾏锁，表锁等，读锁，写锁等，都是在做操作之前先上锁。Java中 synchronized和 ReentrantLock等独占锁就是悲观锁思想的实现。

**乐观锁：**总是假设最好的情况，每次去拿数据的时候都认为别⼈不会修改，所以不会上锁，但是在更新的时候会判断⼀下在此期间别⼈有没有去更新这个数据，可以使⽤`版本号机制`和`CAS算法`实现。乐观锁适⽤于多读的应⽤类型，这样可以提⾼吞吐量，像数据库提供的类似于write_condition机制，其实都是提供的乐观锁。在Java中 java.util.concurrent.atomic包下⾯的原⼦变量类就是使⽤了乐观锁的⼀种实现⽅式CAS实现的。

> **乐观锁常见的两种实现方式：**
>
> 1. **版本号机制：**⼀般是在数据表中加上⼀个数据版本号version字段，表示数据被修改的次数，当数据被修改时，version值会加⼀。当线程A要更新数据值时，在读取数据的同时也会读取version值，在提交更新时，若刚才读取到的version值为当前数据库中的version值相等时才更新，否则重试更新操作，直到更新成功。
> 2. **CAS**
>    1. 需要读写的内存值V
>    2. 进行比较的值A
>    3. 拟写入的新值B

### Thread类中的yield方法有什么用？

**Yield方法可以暂停当前正在执行的线程对象，让其它有相同优先级的线程执行。**它是一个静态方法，而且只保证当前线程放弃CPU占用而不能保证使其它线程一定能占用CPU，执行yield()的线程有可能在进入到暂停状态后马上又被执行。

### Thread类中的join方法有什么用？

一个线程可以在其他线程上调用join(）方法，其效果是等待一段时间直到第二个线程结束才正常执行。如果某个线程在另一个线程t上调用t.join()方法，此线程将被挂起，知道目标线程t结束才回复（可以用t.isAlive()返回为真假判断）。也可以在调用join时带上一个超时参数，来设置到期时间，时间到期，join方法自动返回。

### ThreadLocal是什么？有什么用？（用友Java）

通常情况下，我们创建的变量是可以被任何⼀个线程访问并修改的。如果想实现每⼀个线程都有⾃⼰的专属本地变量该如何解决呢？ JDK 中提供的 ThreadLocal 类正是为了解决这样的问题。 ThreadLocal 类主要解决的就是让每个线程绑定⾃⼰的值。

如果你创建了⼀个 ThreadLocal 变量，那么访问这个变量的每个线程都会有这个变量的本地副本，这也是 ThreadLocal 变量名的由来。他们可以使⽤ get 和 set ⽅法来获取默认值或将其值更改为当前线程所存的副本的值，从⽽避免了线程安全问题。

**原理总结：**

1. 每个Thread维护着⼀个ThreadLocalMap的引⽤
2. ThreadLocalMap是ThreadLocal的==内部类==，⽤Entry来进⾏存储
3. 调⽤ThreadLocal的set()⽅法时，实际上就是往ThreadLocalMap设置值，**key是ThreadLocal对象，值是传递进来的对象**
4. 调⽤ThreadLocal的get()⽅法时，实际上就是往ThreadLocalMap获取值，key是ThreadLocal对象
5. ThreadLocal本身并不存储值，它只是作为⼀个key来让线程从ThreadLocalMap获取value

### 什么是线程安全？

线程安全的定义：当多个线程访问⼀个对象时，如果不⽤考虑这些线程在运⾏时环境下的调度和交替执⾏，也不需要进⾏额外的同步，或者在调⽤⽅进⾏任何其他的协调操作，调⽤这个对象的⾏为都可以获得正确的结果，那这个对象就是线程安全的。

### wait()和sleep()区别？

**sleep方法**：是`Thread类的静态方法`，当前线程将睡眠n毫秒，线程进入阻塞状态。当睡眠时间到了，会解除阻塞，进入可运行状态，等待CPU的到来。睡眠不释放锁（如果有的话）。

**wait方法**：是`Object的方法`，必须与synchronized关键字一起使用，线程进入阻塞状态，当notify或者notifyall被调用后，会解除阻塞。但是，只有重新占用互斥锁之后才会进入可运行状态，睡眠时，会释放互斥锁。

1. sleep() 方法没有释放锁，而 wait() 方法释放了锁 
2. sleep() 通常被用于暂停执行，而wait() 通常被用于线程间交互/通信
3. wait()⽅法被调⽤后，线程不会⾃动苏醒，需要别的线程调⽤同⼀个对象上的notify()或者notifyAll()
   ⽅法。sleep()⽅法执⾏完成后，线程会⾃动苏醒。或者可以使⽤wait(long timeout)超时后线程会
   ⾃动苏醒
4. **相同：**两者都可以暂停线程的执行

### wait()和notify()底层实现？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/20190515142945200.png">

`wait线程首先获得了对象的锁，然后调用对象的wait方法，从而放弃了锁并进入了对象的等待队列WaitQueue，进入等待状态。由于wait线程释放了对象的锁，notify随后获取了对象的锁，并调用对象的notify方法，将等待线程移到SynchronizedQueue队列中，此时wait线程变为阻塞状态。Notify释放了锁之后，wait线程再次获取到锁并从wait（）返回继续执行。`

### 创建线程的方式有哪些？有什么区别？线程通信方式？（用友Java）

#### 创建线程

- <font color='blue'>继承Thread类，重写Thread类的run()方法</font>
- <font color='blue'>实现Runnable接口，作为参数，传递给Thread的构造函数</font>
- <font color='blue'>FutureTask+实现Callable接口</font>

```java
public class ThreadResultDemo {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        // Callable接口任务（前文实现了Callable接口）
        CallableTask task = new CallableTask();
        // 包装成FutureTask类
        FutureTask<Integer> futureTask = new FutureTask<>(task);
        new Thread(futureTask).start();
        // 阻塞的方式获取线程执行结果
        System.out.println(futureTask.get());
    }
}
```

```java
@FunctionalInterface
public interface Callable<V> {
    /**
     * Computes a result, or throws an exception if unable to do so.
     *
     * @return computed result
     * @throws Exception if unable to compute a result
     */
    V call() throws Exception;
}
------------------------------------------------
@FunctionalInterface
public interface Runnable {
    /**
     * When an object implementing interface <code>Runnable</code> is used
     * to create a thread, starting the thread causes the object's
     * <code>run</code> method to be called in that separately executing
     * thread.
     * <p>
     * The general contract of the method <code>run</code> is that it may
     * take any action whatsoever.
     *
     * @see     java.lang.Thread#run()
     */
    public abstract void run();
}
```

1. <font color='green'>callable的核心是call方法，允许返回值</font>，Callable接口支持返回执行结果，此时需要调用FutureTask.get()方法实现，此方法会阻塞线程直到获取“将来”的结果，当不调用此方法时，主线程不会阻塞。<font color='green'>runnable的核心是run方法，没有返回值</font>
2. `call方法可以抛出异常，但是run方法不行`
3. runnable是java1.1就有了，所以他不存在返回值，后期在java1.5进行了优化，就出现了callable，就有了返回值和抛异常
4. callable和runnable都可以应用于executors，**而thread类只支持runnable**
5. `Callable接口实现类中run()方法允许将异常向上抛出`，也可以直接在内部处理(try…catch)；而Runnable接口实现类中run()方法的异常必须在内部处理掉，不能向上抛出

- <font color='blue'>线程池(七个参数)</font>

#### 三种方式对比（除线程池）

- `实现Runnable接口、Callable接口方式`

**优势：**

1. 线程类只是实现了Runnable接口或Callable接口，还可以继承其他类
2. 多个线程可以共享同一个target对象，所以非常适合多个相同线程来处理同一份资源的情况，从而可以将CPU、代码和数据分开，形成清晰的模型，较好地体现了面向对象的思想
3. 线程池只能放入Runnable或Callable接口实现类，不能直接放入继承Thread的类
4. call()方法执行后可以有返回值
5. 实现Callable接口可以拿到一个Future对象，表示异步计算的结果 。通过Future对象可以了解任务执行情况，**可取消任务的执行**，还可获取执行结果

**劣势：**编程稍微复杂，如果要访问当前线程，则必须使用Thread.currentThread()方法

- `继承Thread类的方式`

**优势：**编写简单，如果需要访问当前线程，则无需使用Thread.currentThread()方法，直接使用this即可获得当前线程

**劣势：**线程类已经继承了Thread类，所以不能再继承其他父类

#### 线程通信方式

1. `使用volatile关键字`

> volatile有两⼤特性，⼀是可⻅性，⼆是有序性，禁⽌指令重排序，其中可⻅性就是可以让线程之间
> 进⾏通信。
>
> volatile语义保证线程可⻅性有两个原则保证：
>
> - 所有volatile修饰的变量⼀旦被某个线程更改，必须⽴即刷新到主内存
> - 所有volatile修饰的变量在使⽤之前必须重新读取主内存的值

2. `使用Object()类的wait()和notify()方法`

> 等待通知机制是基于wait和notify⽅法来实现的，在⼀个线程内调⽤该线程锁对象的wait⽅法，线
> 程将进⼊等待队列进⾏等待直到被通知或者被唤醒

3. `join方式`

> 当在⼀个线程调⽤另⼀个线程的join⽅法时，当前线程阻塞等待被调⽤join⽅法的线程执⾏完毕才能继续执⾏，所以join的好处能够保证线程的执⾏顺序

4. `threadLocal方式`

> threadLocal⽅式的线程通信，不像以上三种⽅式是多个线程之间的通信，它更像是⼀个线程内部的通信，将当前线程和⼀个map绑定，在当前线程内可以任意存取数据，减省了⽅法调⽤间参数的传递

### 三个线程交替打印1-100

```java
/**
 * 多线程按序打印1-100
 */
public class TurnPrint {
    private static volatile int flag = 0;
    private static volatile int count = 1;
 
    public static void main(String[] args) {
        new Thread(() -> {
            while(count <= 100){
                if (flag == 0){
                    System.out.println(Thread.currentThread().getName() + " " + 
count);
                    count++;
                    flag = 1;
                }
            }
        }, "线程A").start();
 
        new Thread(() -> {
            while(count <= 100){
                if (flag == 1){
                    System.out.println(Thread.currentThread().getName() + " " + 
count);
                    count++;
                    flag = 2;
                }
            }
        }, "线程B").start();
 
        new Thread(() -> {
            while(count <= 100){
                if (flag == 2){
                    System.out.println(Thread.currentThread().getName() + " " + 
count);
                    count++;
                    flag = 0;
                }
            }
        }, "线程C").start();
    }
}
```

### 如何让线程（线程池）优雅的退出？

1. **interrupt**

interrupt()方法的使用效果并不像for+break语句那样，马上就停止循环。`调用interrupt方法是在当前线程中打了一个停止标志，并不是真的停止线程`。

2. **标志位**

如果代码程序逻辑中是循环执行的业务，可以在程序的执行中线程代码中增加一个标志位，比如下面代码中在 while 循环中去执行这个程序，通过 flag 去控制程序是否继续执行，如果在外部线程将 flag 修改为 false，那么创建的子线程代码中会收到这个数据的变化，通过这个变量的形式，通知到另一个线程，从而达到控制线程中止的效果。

```java
public class FlagThreadDemo{
    public volatile static boolean flag = true;
    public static void main(String[] args) throws InterruptedException{
        new Thread(()->{
            try{
                while(flag){
                    System.out.println("运行中");
                    Thread.sleep(1000L);
                }
            }catch(InterruptedException e){
                e.printStackTrace();
            }
        }).start();
        Thread.sleep(3000L);
        flag = false;
        System.out.println("程序运行结束");
    }
}
```

**<font color='red'>为什么不用stop()?</font>**

<font color='blue'>假设一个线程正在处理一个复杂的业务流程，突然间线程被调用stop而意外终止，stop会释放锁并强制终止线程，造成执行一半的线程终止，会带来数据不一致性的问题。</font>

------

线程池提供了两个关闭方法，`shutdownNow()`和`shutdown()`方法。

shutdownNow方法的解释是：线程池拒接收新提交的任务，同时立马关闭线程池，线程池里的任务不再执行。

> 当我们调用线程池的shutdownNow时，如果线程正在getTask方法中执行，则会通过for循环进入到if语句，于是getTask返回null,从而线程退出。不管线程池里是否有未完成的任务。
>
> 如果线程因为执行提交到线程池里的任务而处于阻塞状态，则会导致报错(如果任务里没有捕获InterruptedException异常)，否则线程会执行完当前任务，然后通过getTask方法返回为null来退出。

shutdown方法的解释是：线程池拒接收新提交的任务，同时等待线程池里的任务执行完毕后关闭线程池。

> 当我们调用线程池的shutdown方法时，如果线程正在执行线程池里的任务，即便任务处于阻塞状态，线程也不会被中断，而是继续执行。
>
> 如果线程池阻塞等待从队列里读取任务，则会被唤醒，但是会继续判断队列是否为空，如果不为空会继续从队列里读取任务，为空则线程退出。

**我们知道，使用shutdownNow方法，可能会引起报错，使用shutdown方法可能会导致线程关闭不了。**

**所以当我们使用shutdownNow方法关闭线程池时，一定要对任务里进行异常捕获。**

**当我们使用shutdown方法关闭线程池时，一定要确保任务里不会有永久阻塞等待的逻辑，否则线程池就关闭不了。**

**最后，一定要记得，shutdownNow和shutdown调用完，线程池并不是立马就关闭了，要想等待线程池关闭，还需调用awaitTermination方法来阻塞等待。**

### synchronized和ReentrantLock的区别是什么（用友Java）？

**两者都是可重入锁**，一个线程在执行一个带锁的方法，该方法中又调用了另一个需要相同锁的方法，则该线程可以直接执行调用的方法，而无需重新获得锁， 两者都是同一个线程每进入一次，锁的计数器都自增1，所以要等到锁的计数器下降为0时才能释放锁。

1. **<font color='red'>锁的实现：</font>**synchronized是关键字属于JVM层⾯，synchronized的语义底层是通过⼀个monitor的对象来完成，而Lock是具体类（java.util.concurrent.Locks.Lock）是API层⾯的锁
2. **<font color='red'>性能：</font>**新版本 Java 对 synchronized 进⾏了很多优化，例如⾃旋锁等，synchronized 与 ReentrantLock ⼤致相同
3. **<font color='red'>等待可中断：</font>**当持有锁的线程⻓期不释放锁的时候，正在等待的线程可以选择放弃等待，改为处理其他事情。`ReentrantLock 可中断，⽽ synchronized 不⾏`。
4. **<font color='red'>公平锁：</font>**==公平锁是指多个线程在等待同⼀个锁时，必须按照申请锁的时间顺序来依次获得锁。==
   `synchronized 中的锁是⾮公平的，ReentrantLock 默认情况下也是⾮公平的，但是也可以是公平的`
5. **<font color='red'>锁绑定多个条件：</font>**⼀个 ReentrantLock 可以同时绑定多个 Condition 对象，⽤来实现分组唤醒需要唤醒的线程，可以`精确唤醒`，⽽不是像synchronized`要么随机唤醒⼀个线程要么唤醒全部线程`
6. **<font color='red'>唤醒：</font>**synchronized不需要⽤户去⼿动释放锁，当synchronized代码执⾏完后系统会⾃动让线程释放对锁的占⽤ReentrantLock则需要⽤户⼿动释放锁，就有可能导致出现死锁现象，需要`lock()和unlock()方法配合try/finally使用`

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/6fa1cdd8fbec0fd0560d6d648f8a8d47-2.png">

### Java中的并行框架？

<font color='red'>Fork/Join</font>框架是JAVA7提供的一个用于并行执行任务的框架，是一个把大任务分割成若干个小任务，最终汇总每个小任务结果后得到大任务结果的框架

> 该框架采用工作窃取算法，比传统的Executor方式更加高效与简单，不需要再单独维护计数器了；工作窃取算法指的是某个线程从其他队列里窃取任务来执行。使用的场景是一个大任务拆分成多个小任务，为了减少线程间的竞争，把这些子任务分别放到不同的队列中，并且每个队列都有单独的线程来执行队列里的任务，线程和队列一一对应。但是会出现这样一种情况：A线程处理完了自己队列的任务，B线程的队列里还有很多任务要处理。A是一个很热情的线程，想过去帮忙，但是如果两个线程访问同一个队列，会产生竞争，所以A想了一个办法，从双端队列的尾部拿任务执行。而B线程永远是从双端队列的头部拿任务执行（任务是一个个独立的小任务），这样感觉A线程像是小偷在窃取B线程的东西一样。

```java
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.RecursiveTask;

public class MyTest extends RecursiveTask<List<Integer>> {
    private int cn = 0;
    public MyTest(int a){
        this.cn = a;
    }
    public static void main(String[] args) {
        long time1 = System.currentTimeMillis();
        MyTest t1 = new MyTest(3);    // 任务1耗时600ms
        MyTest t2 = new MyTest(5);   // 任务2耗时1s
        t1.fork();
        t2.fork();
        List<Integer> l1 = t1.join();
        List<Integer> l2 = t2.join();
        l1.addAll(l2);
        System.out.println(l1+": "+(System.currentTimeMillis() - time1)); //如果串行执行，执行时间会大于1600ms
    }
    @Override
    protected List<Integer> compute() {
        try {
            Thread.sleep(cn*200);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        List<Integer> ls = new ArrayList<>();
        for(int i=0; i<cn; i++){
            ls.add(i);
        }
        return ls;
    }
}
```

### 如何保证i++的原子性？

1. JUC的Lock

```java
private final Lock lock = new ReentrantLock();
public void add() {
    lock.lock();
    try {
        i++;
    } finally {
        lock.unlock();
    }
}
```

2. synchronized关键字

```java
public synchronized void add() {
    i++;
}
```

3. JUC的AtomicInteger

```java
AtomicInteger i = new AtomicInteger(0);
public void add() {
    i.getAndIncrement();
}
```

```java
/*
*AtomicInteger.getAndIncrement()线程安全
*/
public final int getAndIncrement(){
    //三个参数
    return unsafe.getAndAddInt(this,valueOffset,1);
}
```

1. Unsafe类是CAS的核心类，由于Java方法无法直接访问底层系统，需要通过本地(native) 方法来访问，Unsafe相当于一个后门，基于该类可以直接操作特定内存的数据。**Unsafe类存在于sun.misc包中**，其内部方法操作可以**像C的指针一样直接操作内存**，因为Java中CAS操作的执行依赖于Unsafe类的方法。注意Unsafe类中的所有方法都是native修饰的，也就是说==Unsafe类中的方法都直接调用操作系统底层资源执行相应任务==。
2. **变量valueOffset**, 表示该变量值在内存中的**偏移地址**，因为Unsafe就是根据**内存偏移地址**获取数据的。
3. **变量value用volatile修饰， 保证了多线程之间的内存可见性。**

### 详细讲解下AQS？

AQS，全名**AbstractQueuedSynchronizer**，是一个抽象类的队列式同步器，它的内部通过维护一个状态volatile int state(共享资源)，一个FIFO线程等待队列来实现同步功能。

state用关键字**volatile**修饰，代表着该共享资源的状态一更改就能被所有线程可见，而AQS的加锁方式本质上就是多个线程在竞争state，<font color='blue'>当state为0时代表线程可以竞争锁，不为0时代表当前对象锁已经被占有</font>，其他线程来加锁时则会失败，<font color='blue'>加锁失败的线程会被放入一个FIFO的等待队列中</font>，这些线程会被**UNSAFE.park()**操作挂起，等待其他获取锁的线程释放锁才能够被唤醒。

`AQS支持两种资源分享的方式：Exclusive（独占，只有一个线程能执行，如ReentrantLock）和Share（共享，多个线程可同时执行，如Semaphore/CountDownLatch）`

AQS代码内部提供了一系列操作锁和线程队列的方法，主要操作锁的方法包含以下几个：

- compareAndSetState()：利用CAS的操作来设置state的值
- tryAcquire(int)：独占方式获取锁。成功则返回true，失败则返回false。
- tryRelease(int)：独占方式释放锁。成功则返回true，失败则返回false。<font color='red'>ReentrantLock就是实现了自定义的tryAcquire-tryRelease</font>
- tryAcquireShared(int)：共享方式释放锁。负数表示失败；0表示成功，但没有剩余可用资源；正数表示成功，且有剩余资源。
- tryReleaseShared(int)：共享方式释放锁。如果释放后允许唤醒后续等待结点返回true，否则返回false。

<font color='blue'>AQS内部还定义了一个静态类Node，表示CLH队列的每一个结点</font>，该结点的作用是对每一个等待获取资源做了封装，包含了需要同步的线程本身、线程等待状态.....

### ThreadLocalMap的enrty的key为什么要设置成弱引用？

ThreadLocalMap的内部类Entry被设计为实现了WeakReference，Entry用来存放数据。在构造Entry对象时，将传进来的ThreadLocal对象包装成了真正的弱引用对象，而Entry对象和内部的value对象本身是强引用的。

ThreadLocalMap是用来存放对象的，在一次线程的执行栈中，存放数据后方便我们在任意的地方取得我们想要的值而不被其他线程干扰。ThreadLocalMap本身并没有为外界提供取出和存放数据的API，我们所能获得数据的方式只有通过ThreadLocal类提供的API来间接的从ThreadLocalMap取出数据，所以，当我们用不了key（ThreadLocal对象）的API也就无法从ThreadLocalMap里取出指定的数据。**让key（threadLocal对象）为弱引用，自动被垃圾回收，key就变为null了，就可以通过Entry不为null，而key为null来判断该Entry对象该被清理掉了**

`Entry的key被设计为弱引用就是为了让程序自动的对访问不到的数据进行回收提醒，所以，在访问不到的数据被回收之前，内存泄漏确实是存在的，但是我们不用担心，就算我们不调用remove，ThreadLocalMap在内部的set，get和扩容时都会清理掉泄漏的Entry，内存泄漏完全没必要过于担心。`

### 关于锁的四种状态与锁升级过程 （用友Java）？

**无锁、偏向锁、轻量级锁、重量级锁**四种，锁状态只能升级，不能降级，但是`偏向锁可以被重置为无锁状态`。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/20200603161323889.png">

|  锁状态  |                       存储内容                        | 标志位 |
| :------: | :---------------------------------------------------: | :----: |
|   无锁   |     对象的hashCode、对象分代年龄、是否是偏向锁(0)     |   01   |
|  偏向锁  | 偏向线程ID、偏向时间戳、对象分代年龄、是否是偏向锁(1) |   01   |
| 轻量级锁 |                 指向栈中锁记录的指针                  |   00   |
| 重量级锁 |                   指向互斥量的指针                    |   11   |

|    锁    |                             优点                             | 缺点                                           | 适用场景                           |
| :------: | :----------------------------------------------------------: | :--------------------------------------------- | :--------------------------------- |
|  偏向锁  | 加锁和解锁不需要额外的消耗，和执行非同步方法相比仅存在纳秒级的差距 | 如果线程间存在锁竞争，会带来额外的锁撤销的消耗 | 适用于只有一个线程访问同步块场景   |
| 轻量级锁 |           竞争的线程不会阻塞，提高了程序的响应速度           | 如果始终得不到索竞争的线程，使用自旋会消耗CPU  | 追求响应速度，同步块执行速度非常快 |
| 重量级锁 |               线程竞争不使用自旋，不会消耗CPU                | 线程阻塞，响应时间缓慢                         | 追求吞吐量，同步块执行速度较慢     |

#### 偏向锁

线程1获取锁对象时，会在java对象头和栈帧中记录偏向的锁的threadID

线程1获取该锁时，比较threadID是否一致：（1） 一致 -> 直接进入而无需使用CAS来加锁、解锁；线程2获取该锁时，比较threadID是否一致 ；（2）不一致 -> 检查对象的threadID线程是否还存活

存活：代表该对象被多个线程竞争，于是升级成轻量级锁

不存活：将锁重置为无锁状态，锁头重新标记线程2为新的threadID

（如果线程1和线程2的执行时间刚好错开，那么锁只会在偏向锁之间切换而不会升级为轻量级锁，在使用synchronized的情况下避开了获取锁的成本，所以效率和无锁状态非常接近）

#### 轻量级锁

**对象被多个线程竞争时，锁由偏向锁升级为轻量级锁，轻量级锁采用自旋+CAS的方式不断获取锁。**

线程1获取轻量级锁时会先把锁对象的对象头MarkWord复制⼀份到线程1的栈帧中创建的⽤于存储锁记录的空间（称为DisplacedMarkWord），然后使⽤CAS把对象头中的内容替换为线程1存储的锁记录（DisplacedMarkWord）的地址。

如果在线程1复制对象头的同时（在线程1CAS之前），线程2也准备获取锁，复制了对象头到线程2的锁记录空间中，但是在线程2CAS的时候，发现线程1已经把对象头换了，线程2的CAS失败，那么线程2就尝试使⽤⾃旋锁来等待线程1释放锁。 ⾃旋锁简单来说就是让线程2在循环中不断CAS。

#### 重量级锁

**当线程的自旋次数过长依旧没获取到锁，为避免CPU无端耗费，锁由轻量级锁升级为重量级锁。**

获取锁的同时会阻塞其他正在竞争该锁的线程，依赖对象内部的监视器（monitor）实现，monitor又依赖操作系统底层，需要从用户态切换到内核态，成本非常高。

### 有哪几种线程池，七大参数，拒绝策略，如何提交任务？

#### 四种线程池

- `newCachedThreadPool`：创建一个可缓存线程池，如果线程池长度超过处理需要，可灵活回收空闲线程，若无可回收，则新建线程。线程池为无限大，当执行第二个任务时第一个任务已经完成，会复用执行第一个任务的线程，而不用每次新建线程。

- `newFixedThreadPool`：创建一个定长线程池，可控制线程最大并发数，超出的线程会在队列中等待。

- `newScheduledThreadPool`：创建一个定长线程池，支持定时及周期性任务执行。
- `newSingleThreadExecutor`：创建一个单线程化的线程池，它只会用唯一的工作线程来执行任务，保证所有任务按照指定顺序(FIFO, LIFO, 优先级)执行

#### 七大参数（用友Java）

- <font color='red'>corePoolSize：</font>核心线程数，线程数定义了最⼩可以同时运⾏的线程数量
- <font color='red'>maximumPoolSize：</font>当队列中存放的任务达到队列容量的时候，当前可以同时运⾏的线程数量变为最⼤线程数
- <font color='red'>workdQueue：</font>当新任务来的时候会先判断当前运⾏的线程数量是否达到核⼼线程数，如果达到的话，新任务就会被存放在队列中
- <font color='red'>keepAliveTime：</font>当线程池中的线程数量⼤于 corePoolSize 的时候，如果这时没有新的任务提交，核⼼线程外的线程不会⽴即销毁，⽽是会等待，直到等待的时间超过了keepAliveTime 才会被回收销毁
- <font color='red'>Unit：</font>keepAliveTime 参数的时间单位
- <font color='red'>threadFactory：</font>executor 创建新线程的时候会⽤到，用于创建线程
- <font color='red'>Handler：</font>拒绝策略

#### 四种拒绝策略（用友Java）

**AbortPolicy：**直接抛出异常，抛出`RejectedExecutionException的 RuntimeException`

**CallerRunsPolicy：**返回调用者所在线程来运行任务

**DiscardOldestPolicy：**丢弃队列里存活时间最久的任务

**DiscardPolicy：**直接将刚提交的任务丢弃，而且不会给与任何提示通知

当然也可以根据应用场景需要来实现<font color='red'>RejectedExecutionHandler</font>接口自定义策略

#### 提交任务（execute和submit）

1. 可以使用<font color='blue'>execute</font>提交的任务，但是execute方法没有返回值，所以无法判断任务是否被线程池执行成功
2. 也可以使用<font color='blue'>submit </font>方法来提交任务，它会返回一个<font color='blue'>future</font>,可以通过这个future来判断任务是否执行成功，通过future的get方法来获取返回值，get方法会阻塞住直到任务完成，而使用get(long timeout, TimeUnit unit)方法则会阻塞一段时间后立即返回，这时有可能任务没有执行完
3. 通过调用线程池的shutdown或shutdownNow方法来关闭线程池

#### 线程池的好处（用友Java）

- **降低资源消耗**，通过重复利⽤已创建的线程降低线程创建和销毁造成的消耗
- **提高响应速度**，当任务到达时，任务可以不需要的等到线程创建就能⽴即执⾏
- **提高线程的可管理性**，线程是稀缺资源，如果⽆限制的创建，不仅会消耗系统资源，还会降低系统的稳定性，使⽤线程池可以进⾏统⼀的分配，调优和监控

#### 如何合理的配置线程池？

1. <font color='red'>CPU密集型</font>

> CPU 使⽤率较⾼（也就是经常计算⼀些复杂的运算，逻辑处理等情况）⾮常多的情况下，`线程数⼀般只
> 需要设置为CPU核⼼数的线程个数`。 这⼀类型多出现在开发中的⼀些业务复杂计算和逻辑处理过程中。
>
> 注意：但是如果线程远远超出 CPU 核⼼数量，反⽽会使得任务效率下降，因为`频繁的切换线程也是要消耗时间的`。因此对于 CPU 密集型的任务来说，线程数等于 CPU 数是最好的了。

2. <font color='red'>IO密集型</font>

> CPU 使⽤率较低，程序中会存在⼤量的 I/O 操作占⽤时间，导致线程空余时间很多，所以通常就需要开
> `CPU核⼼数两倍的线程`。当线程进⾏ I/O 操作 CPU 空闲时，启⽤其他线程继续使⽤ CPU，以提⾼ CPU 的使⽤率。
>
> 线程等待时间所占⽐例越⾼，需要越多线程，启⽤其他线程继续使⽤CPU，以此提⾼CPU的利⽤率；线
> 程 CPU 时间所占⽐例越⾼，需要越少的线程，这⼀类型在开发中主要出现在⼀些计算业务频繁的逻辑中。

### 如何解决ThreadLocal因线程复用导致失效的问题？

<font color='red'>remove()方</font>法用来清除这个线程本地变量的值, 这个方法很容易被忽视, 其实我们在进行get()和set()操作之后, 需要调用remove方法来清除这个线程本地变量的值, 否则会因线程复用导致ThreadLocal失效

```java
@Component
public class HostHolder {
    private ThreadLocal<User> users = new ThreadLocal<>();
    public void setUsers(User user){
        users.set(user);
    }
    public User getUser(){
        return users.get();
    }

    public void clean(){
        users.remove();
    }
}
```

### 线程死锁案例？

```java
public class Test {
    static Object resource_one = new Object();
    static Object resource_two = new Object();

    public static void main(String[] args) {
        Thread1 thread1 = new Thread1();
        Thread2 thread2 = new Thread2();

        thread1.start();
        thread2.start();
    }

    static class Thread1 extends Thread {
        @Override
        public void run() {
            System.out.println(Thread.currentThread().getName() + "---尝试获得资源1");
            synchronized (resource_one) {
                System.out.println(Thread.currentThread().getName() + "---获得资源1成功");
                try {
                    Thread.sleep(3000);
                } catch (InterruptedException e) {
                    // Do none
                }
                System.out.println(Thread.currentThread().getName() + "---尝试获得资源2");
                synchronized (resource_two) {

                }
            }
        }
    }

    static class Thread2 extends Thread {
        @Override
        public void run() {
            System.out.println(Thread.currentThread().getName() + "---尝试获得资源2");
            synchronized (resource_two) {
                System.out.println(Thread.currentThread().getName() + "---获得资源2成功");
                try {
                    Thread.sleep(3000);
                } catch (InterruptedException e) {
                    // Do none
                }
                System.out.println(Thread.currentThread().getName() + "---尝试获得资源1");
                synchronized (resource_one) {

                }
            }
        }
    }
}
```

### synchronized修饰static方法,具体锁的是什么？普通方法呢？

`当synchronized修饰一个static方法时`，多线程下，获取的是类锁(即Class本身，**注意:不是实例**)，作用范围是整个静态方法，作用的对象是这个类的所有对象。

`当synchronized修饰一个非static方法时`，多线程下，获取的是对象锁(即类的实例对象)，作用范围是整个方法，作用对象是调用该方法的对象

### CAS底层原理和缺点？

#### CAS原理（用友Java）

定义：CAS即`compare and swap`，是一种有名的无锁算法。即不使用锁的情况下实现多线程之间的变量同步，也就是在没有线程被阻塞的情况下实现变量的同步，也叫非阻塞同步。

CAS中涉及三个要素：

- 需要读写的内存值V
- 进行比较的值A
- 拟写入的新值B

<font color='red'>当且仅当预期值A和内存值V相同时，将内存值V修改为B，否则什么都不做。</font>

--------------------

1. 自旋锁
2. 乐观锁
3. Unsafe类，Unsafe是CAS的核心类，由于Java方法无法直接访问底层系统，而是通过本地(native)方法来访问，Unsafe相当于一个后门，基于该类可以操作特定内存的数据。Unsafe类存在于`sun.misc(jre文件夹下rt.jar)包`中，其内部方法操作可以像C的指针一样直接操作内存，因为java中的CAS操作的执行依赖于Unsafe类的方法。**Unsafe类中的所有方法都是native修饰的，也就是说Unsafe类中的所有方法都可以直接调用操作系统。**

#### CAS缺点解决？

1. **ABA问题**

JDK1.5之后的`AtomicStampedReference`类实现，其中的`compareAndSet方法`首先检查当前引用是否等于预期引用，并且当前标志是否等于预期标志，如果全部相等，则以原子的方式将该引用和该标志的值设置为给定的更新值。

> `AtomicStampedReference`是一个带有时间戳的对象引用，能很好的解决CAS机制中的ABA问题。
>
> AtomicStampedReference的`compareAndSet函数`，这里面有四个参数：
>
> （1）第一个参数expectedReference：表示预期值
>
> （2）第二个参数newReference：表示要更新的值
>
> （3）第三个参数expectedStamp：表示预期的时间戳
>
> （4）第四个参数newStamp：表示要更新的时间戳
>
> ***如果当前引用 等于 预期值并且 当前版本戳等于预期版本戳, 将更新新的引用和新的版本戳到内存***

2. **循环资源开销大**

通过自适应自旋锁，`当超过一定时间或者一定次数时`，return退出，自旋的时间不固定，会根据上次自旋的时间以及当前持有锁的线程状态来决定。

3. **只能保证一个共享变量的原子操作**

CAS只对单个共享变量有效，当操作涉及多个共享变量时CAS失效。但从JDK1.5开始，提供了`AtomicReference类`来保证引用对象之间的原子性，你可以把多个变量放在一个对象里进行CAS操作，可以适用`AtomicReference类`或者`锁`把多个共享变量合并成一个共享变量莱来操作。

### Future和FutureTask区别？

1. Future是一个接口，代表可以取消的任务，并可以获得任务的执行结果

2. FutureTask 是基本的实现了Future和runnable接口

- 实现runnable接口，说明可以把FutureTask实例传入到Thread中，在一个新的线程中执行。
- 实现Future接口，说明可以从FutureTask中通过get取到任务的返回结果，也可以取消任务执行（通过interreput中断）

**FutureTask可用于异步获取执行结果或取消执行任务的场景。**通过传入Runnable或者Callable的任务给FutureTask，直接调用其run方法或者放入线程池执行，之后可以在外部通过FutureTask的get方法异步获取执行结果，因此，**FutureTask非常适合用于耗时的计算**，主线程可以在完成自己的任务后，再去获取结果。另外，**FutureTask还可以确保即使调用了多次run方法，它都只会执行一次Runnable或者Callable任务**，或者通过cancel取消FutureTask的执行等。

## MySQL

### 索引是什么以及索引的优缺点？（用友Java）

索引是一种特殊的文件(InnoDB数据表上的索引是表空间的一个组成部分)，它们包含着对数据表里所有
记录的引用指针。

索引是一种数据结构。数据库索引，是数据库管理系统中一个排序的数据结构，以协助快速查询、更新
数据库表中数据。

--------------

**<font color='red'>索引的优点：</font>**

- 可以大大加快数据的检索速度，这也是创建索引的最主要的原因。
- 通过使用索引，可以在查询的过程中，使用优化隐藏器，提高系统的性能。

**<font color='red'>索引的缺点：</font>**

- 时间方面：创建索引和维护索引要耗费时间，具体地，当对表中的数据进行增加、删除和修改的时
  候，索引也要动态的维护，会降低增/改/删的执行效率；
- 空间方面：索引需要占物理空间。

### 索引为什么可以提高查询速度？

索引可以将无序内容转换为有序的一个集合（相对），就如同新华字典，如果没有目录，那么查询一个汉字就需要很长时间了

- 数据页和数据页之间，组成一个双向链表
- 每个数据页中的记录，是一个单向链表
- 每个数据页都根据内部的记录生成一个页目录（Page directory），如果是主键的话，可以在页目录中使用二分法快速定位
- 如果我们根据一个非主键、非索引列进行查询，那么需要遍历双向链表，找到所在的页；再遍历页内的单向链表；如果表内数据很大的话，这样的查询就会很慢

-------

**缺点：**

- B+ Tree 是一颗平衡树，如果对这颗树新增、修改、删除的话，会破坏它的原有结构
- 我们在做数据新增、修改、删除的时候，需要花额外的时间去维护索引
- 正因为这些额外的开销，导致索引会降低新增、修改、删除的速度

### 为什么B+树3层可以容纳2千万数据？

我们假设主键ID为bigint类型，长度为`8字节`，而指针大小在InnoDB源码中设置为`6字节`，这样一共14字节，我们一个页中能存放多少这样的单元，其实就代表有多少指针，即16384/14=1170。那么可以算出一棵高度为2的B+树，能存放 `1170*16=18720`条这样的数据记录。

根据同样的原理我们可以算出一个高度为3的B+树可以存放多少条这样的记录：`1170*16=18720`, `(18720*16384)/14=21907748.6`条这样的记录。

其实也可以这样算：`1170*1170*16=21902400`条这样的记录。所以在InnoDB中B+树高度一般为1-3层，它就能满足千万级的数据存储。在查找数据时一次页的查找代表一次IO，所以通过主键索引查询通常只需要1-3次IO操作即可查找到数据。

### 缓存与数据库双写不一致问题分析和解决？

**策略一：先更新数据库，再更新缓存** 

1.  这种策略会导致线程安全问题 

 例如：线程 1 更新了数据库，线程 2 也更新数据库， 这时候由于某种原因，线程 2 首先更新了缓存，线程 1 后续更新。 这样就导致了脏数据的问题。 因为目前数据库中存储的线程 2 更新后的数据，而缓存存储的是线程 1 更新的老数据。 

2. 更新缓存的复杂度相对较高 

 数据写入数据库之后，一般存入缓存的数据都要经过一系列的加工计算，然后写入缓存。 这时候更新缓存相比较于直接删除缓存要比较复杂。 

 **策略二：先删除缓存，再更新数据库** 

 这种策略可能导致数据不一致的问题。线程 1 写数据删除缓存；这时候有线程 2 查询该缓存，发现不存在，则去访问数据库，得到旧值放入缓存；线程 1 更新数据库。这时候就出现了数据不一致的问题。 如果缓存没有过期时间，这个脏数据一直存在。 

 解决方案：在写数据库成功之后， 再次淘汰缓存一次。 

 **策略三：先更新数据库，再删除缓存** 

 可能会造成比较短暂的数据不一致。在更新完成数据库， 还没有删除缓存的时刻，如果有缓存数据访问， 就会造成数据不一致的情形。 但这种如果数据同步机制比较科学，一般都会比较快， 不一致的影响比较小。

| 方案                   | 问题                                                         | 问题出现的概率                        | 推荐程度                                                     |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------- | ------------------------------------------------------------ |
| 更新缓存 -> 更新数据库 | 为了保证数据准确性，数据必须以数据库更新结果为准，所以该方案绝不可行 | 大                                    | 不推荐                                                       |
| 更新数据库 -> 更新缓存 | 并发更新数据库场景下，会将脏数据刷到缓存                     | 并发写场景，概率一般                  | 写请求较多时会出现不一致问题，不推荐使用                     |
| 删除缓存 -> 更新数据库 | 更新数据库之前，若有查询请求，会将脏数据刷到缓存             | 并发读场景，概率较大                  | 读请求较多时会出现不一致问题，不推荐使用                     |
| 更新数据库 -> 删除缓存 | 在更新数据库之前有查询请求，并且缓存失效了，会查询数据库，然后更新缓存。如果在查询数据库和更新缓存之间进行了数据库更新的操作，那么就会把脏数据刷到缓存 | 并发读场景&读操作慢于写操作，概率最小 | **读操作比写操作更慢的情况较少，相比于其他方式出错的概率小一些，勉强推荐** |

---------------

**推荐方案：延迟双删，确保读请求结束，写请求可以删除读请求造成的缓存脏数据**

- 先删除缓存
- 再写数据库
- 休眠1秒，再次删除缓存

**问题及解法：**

1. 同步删除，吞吐量降低如何处理，将第二次删除作为异步的，提交一个延迟的执行任务
2. 解决删除失败的方式：添加重试机制，例如：将删除失败的key，写入消息队列；但对业务耦合有些严重

**实际场景：**

- 写缓存策略
  - 缓存key设置失效时间
  - 先DB操作，再缓存失效
  - 写操作都标记key（美团中间件）强制走主库
  - 接入美团中间件监听binlog（美团中间件）变化的数据在进行兜底，再删除缓存
- 读缓存策略
  - 先判断是否走主库
  - 如果走主库，则使用标记（美团中间件）查主库
  - 如果不是，则查看缓存中是否有数据
  - 缓存中有数据，则使用缓存数据作为结果
  - 如果没有，则查DB数据，再写数据到缓存

### B+树和B树的对比，好处？（用友Java）

#### 主要区别

B树中的内部节点和叶⼦节点均存放键和值，⽽B+树的内部节点只有键没有值，叶⼦节点存放所有
的键和值；B＋树的叶⼦节点是通过链表相连在⼀起的，⽅便顺序检索

#### B+树好处

- B树适⽤于随机检索，⽽B+树适⽤于随机检索和顺序检索
- B+树⾮叶⼦节点只存储关键字和指向⼦节点的指针，⽽B树还存储了数据，在同样⼤⼩的情况下，B+树的⼀个节点可以存储更多的关键字，从⽽使树的⾼度变低，减少了I/O次数，使得数据检索速度更快
- B+树可以很好的利⽤局部性原理，如果⼀个存储器的某个位置被访问，那么将它附近的位置也会被访问。我们可以利⽤磁盘预读原理提前将这些数据读⼊内存，减少了磁盘 IO 的次数
- B+树叶⼦节点存储了所有关键字和数据，并且多个节点⽤链表连接。可以快速⽀撑范围查找
- B+树性能更加稳定，B+树⾮叶⼦节点不存储数据，所以查询时间复杂度固定为O(logN)，B树查询时间复杂度不固定，最好是O(1)

### Hash索引和B+树索引的区别？

哈希索引⼀般多⽤于精确的等值查找，B+索引则多⽤于除了精确的等值查找外的其他查找。在⼤多数情况下，会选择使⽤B+树索引。

- 哈希索引不⽀持排序，因为哈希表是⽆序的
- 哈希索引不⽀持范围查找
- 哈希索引不⽀持模糊查询及多列索引的最左前缀匹配
- 因为哈希表中会存在哈希冲突，所以哈希索引的性能是不稳定的，⽽B+树索引的性能是相对稳定的，每次查询都是从根节点到叶⼦节点

### 什么情况下考虑分库分表？

#### IO瓶颈

第一种：磁盘读IO瓶颈，热点数据太多，数据库缓存放不下，每次查询会产生大量的IO，降低查询速度->分库和垂直分表

第二种：网络IO瓶颈，请求的数据太多，网络带宽不够 ->分库

#### CPU瓶颈

第一种：SQl问题：如SQL中包含join,group by, order by，非索引字段条件查询等，增加CPU运算的操作->SQL优化，建立合适的索引，在业务Service层进行业务计算。

第二种：单表数据量太大，查询时扫描的行太多，SQl效率低，增加CPU运算的操作——>水平分表

- **水平分库**
  - 概念：以字段为依据，按照一定策略（hash、range等），将一个库中的数据拆分到多个库中
  - 每个库的结构都一样；每个库中的数据不一样，没有交集；所有库的数据并集是全量数据
- **水平分表**
  - 概念：以字段为依据，按照一定策略（hash、range等），讲一个表中的数据拆分到多个表中
  - 每个表的结构都一样；每个表的数据不一样，没有交集，所有表的并集是全量数据
- **垂直分库**
  - 概念：以表为依据，按照业务归属不同，将不同的表拆分到不同的库中
  - 每个库的结构都不一样；每个库的数据也不一样，没有交集；所有库的并集是全量数据
- **垂直分表**
  - 概念：以字段为依据，按照字段的活跃性，将表中字段拆到不同的表中（主表和扩展表）
  - 每个表的结构不一样；每个表的数据也不一样，一般来说，每个表的字段至少有一列交集，一般是主键，用于关联数据；所有表的并集是全量数据

### 索引的成本有哪些？

1. 创建索引和维护索引都是需要消耗一定的时间，这种时间会随着数据量的增加而增加；
2. 索引需要占一定的物理空间，除了数据表存储数据占用空间，每一条索引都会占用一定的空间，所以索引创建的越多空间占用的就会越大;
3. 当表中的数据增加、修改、删除时都需要对索引进行维护，这就降低了数据的维护速度

### MySQL什么时候用行锁，什么时候用表锁？（用友Java）

对于InnoDB表，在绝大部分情况下都应该使用<font color='blue'>行级锁</font>，因为事务和行锁往往是我们之所以选择InnoDB的理由。

在特殊事务中，可以考虑使用表锁

- 事务需要更新大部分或全部数据，表又比较大，如果使用默认的行锁，不仅这个事务执行效率低，而且可能造成其他事务长时间锁等待和锁冲突，这种情况下可以考虑使用表锁来提高该事务的执行速度
- 事务涉及多个表，比较复杂，很可能引起死锁，造成大量事务回滚。这种情况也可以考虑一次性锁定事务涉及的表，从而避免死锁、减少数据库因事务回滚带来的开销

### 说明主键索引、联合索引和没有索引情况下select的过程？

- 无索引情况下，Mysql会以主键当成索引来按主键从小到大输出结果

- 有索引情况下，按照索引列有序

  - > 首先系统会查询索引表，假如该索引表的主键是索引列type（通常为了保证主键唯一性，type后面会添加一个id后缀），通过索引列查到Id，然后拿着这些Id去select的表中查询最终结果。为了最高效，扫描索引表的时候会顺着type主键往下扫，然后拿扫描得到的id去“逐个”请求select的表，于是自然就出现了按照索引列有序的结果。当type列的值一致的时候，插入到索引列的数据可以根据Id顺序插入到索引表中，保证了当Type一致的时候，会按照Id排序

### MySQL查看数据库编码？

```shell
show variable like 'charactere%';
```

### 数据库是否会出现死锁？

- MyISAM中不会出现，只用到表锁，不支持事务，每次的读写都会隐形的加上读写锁

- InnoDB会出现死锁
  - 系统资源不足，进程运行推进的顺序不合适，资源分配不当等
  - 事务一:两个操作update A;update B;事务二:两个操作update B;update A;线程一执行事务一到一半的时候，锁了A想要获得B的锁，与此同时事务二执行到了锁B，想要获得锁A的时候，因为互相都想要对方拥有的锁，而导致死锁！
  - A线程先查询了一条记录（使用了共享锁），与此同时B线程正要修改这条记录（使用了独占锁），然后A线程突然想修改这条记录了，怎么办呢？升级锁。。而B线程想要降级为共享锁，必须要等到A线程释放掉共享锁，这样就形成了死锁！
- 使用MVCC（多版本并发控制）解决死锁

<font color='blue'>悲观锁：</font>

- 查询时直接锁住记录使得其他事务不能查询，更不能更新
- 语法：select ... for update（排他锁）|| select ... lock in share mode（共享锁）
- 适用于并发量大的情况
- 类比Java，synchronized关键字

<font color='blue'>乐观锁：</font>

- 提交更新时检查版本或者时间戳是否符合
- 语法：使用version或者timestamp进行比较
- 设永远并发量小的情况
- 类比Java，CAS

### 主键索引和唯一索引的区别？

主键创建后一定包含一个唯一性索引，唯一性索引并不一定就是主键。

唯一性索引列<font color='blue'>允许空值</font>，而<font color='blue'>主键列不允许为空值</font>。

主键可以被其他表引用为外键，而唯一索引不能。

一个表最多只能创建一个主键，但可以创建多个唯一索引。

### 什么是MySQL主从复制？

<font color='green'>MySQL主从复制是指数据可以从一个MySQL数据库服务器主节点复制到一个或多个从节点。MySQL 默认采用异步复制方式，这样从节点不用一直访问主服务器来更新自己的数据，数据的更新可以在远程连接上进行，从节点可以复制主数据库中的所有数据库或者特定的数据库，或者特定的表。</font>

<font color='blue'>好处：</font>

1. 主从复制，即主库负责写，从库负责读，这样即使主库出现了锁表的情景，通过读取从库也可以保证业务的正常运行
2. 做数据的热备份
3. 架构的扩展。业务量越来越大，I/O访问频率过高，单机无法满足，此时做多库的存储，降低磁盘I/O访问的频率，提高单个机器的I/O性能

<font color='blue'>原理：</font>

（1）master服务器将数据的改变记录二进制<font color='red'>binlog</font>日志，当master上的数据发生改变时，则将其改变写入二进制日志中；

（2）slave服务器会在一定时间间隔内对master二进制日志进行探测其是否发生改变，如果发生改变，则开始一个<font color='red'>I/OThread</font>请求master二进制事件

（3）同时主节点为每个I/O线程启动一个<font color='red'>dump</font>线程，用于向其发送二进制事件，并保存至从节点本地的中继日志中，从节点将启动`SQL线程`从中继日志中读取二进制日志，在本地重放，使得其数据和主节点的保持一致，最后I/OThread和SQLThread将进入睡眠状态，等待下一次被唤醒。

<font color='blue'>也就是说：</font>

- 从库会生成两个线程,一个I/O线程,一个SQL线程;
- I/O线程会去请求主库的binlog,并将得到的binlog写到本地的<font color='red'>relay-log(中继日志)</font>文件中;
- 主库会生成一个<font color='red'>log dump线程</font>,用来给从库I/O线程传binlog;
- <font color='red'>SQL线程,会读取relay log文件中的日志,并解析成sql语句逐一执行</font>

### MySQL有那些隔离级别？（用友Java）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/gelijibie.png">

#### 脏读

有两个事务A和B，A读取已经被B修改但未提交的字段，此时B回滚，那么A读取的字段就是临时且⽆效的。可以提⾼隔离级别，改成读已提交

#### 不可重复读

有两个事务A和B，A读取了⼀个字段值，然后B更新并且提交事务，A再重新读取这个字段，就和之前不相等了。可以提⾼隔离级别，改成可重复读

#### 幻读

有两个事务A和B，A读取某个范围内的记录时，B⼜在该范围内插⼊了新的记录并提交，当事务A再次读取该范围的记录时，会产⽣幻⾏。可以升级隔离级别到串⾏化，或者使用`MVCC+next-key-lock（间隙锁）`实现

### MySQL的最左前缀原则？

最左前缀原则就是最左优先，在创建多列索引时，要根据业务需求，where子句中使用最频繁的一列放在最左边。

mysql会一直向右匹配直到遇到范围查询(>、<、between、like)就停止匹配，比如a = 1 and b = 2 and c > 3 and d = 4 如果建立(a,b,c,d)顺序的索引，d是用不到索引的，如果建立(a,b,d,c)的索引则都可以用到，a,b,d的顺序可以任意调整。

=和in可以乱序，比如a = 1 and b = 2 and c = 3 建立(a,b,c)索引可以任意顺序，mysql的查询优化器会帮你优化成索引可以识别的形式。

### MySQL如何保证ACID？

**redo log**是重做日志，提供前滚操作，**undo log**是回滚日志，提供回滚操作。

**redo log通常是物理日志，记录的是数据页的物理修改，而不是某一行或某几行修改成怎样怎样，它用来恢复提交后的物理数据页(恢复数据页，且只能恢复到最后一次提交的位置)**

**undo用来回滚行记录到某个版本。undo log一般是逻辑日志，根据每行记录进行记录**

原子性：通过undo log，undo log记录了这些回滚需要的信息，当事务执行失败或调用了rollback，导致事务需要回滚，便可以利用undo log中的信息将数据回滚到修改之前的样子。

一致性：通过其他三种来保证

隔离性：通过给操作的对象加悲观锁或者乐观锁，MVCC(undo log)来保证，RC不满足隔离性，RR满足隔离性

持久性：通过redo log来保证的

> 讨论下何时写入undo log和redo log和bin log?
>
> 假设有A、B两个数据，值分别为1,2.
>
> A.事务开始
>
> B.记录A=1到undo log
>
> C.修改A=3.
>
> D.记录A=3到redo log
>
> E.记录B=2到undo log
>
> F.修改B=4
>
> G.记录B=4到redo log
>
> H.将redo log写入磁盘
>
> I.事务提交完成
>
> > `两阶段提交：为了保证 redo log 和 binlog 的逻辑一致性`
> >
> > `写入：redo log（prepare）|| 写入：binlog  ||  写入：redo log（commit）`
> >
> > 先写redo log再写binlog，会出现redo log写入到磁盘，但binlog还没写入磁盘，断电都主库应用redo log恢复数据，从库无法同步这些数据，主库比从库“新”。
> >
> > 先写binlog再写redo log会造成从库比主库“新”

### 为什么MySQL选择可重复读作为默认隔离级别？

binlog有三种格式：

- <font color='green'>statement</font>：记录的是修改SQL语句
- <font color='green'>row</font>：记录的是每行实际数据的变更
- <font color='green'>mixed</font>：statement和row的混合

Mysql在5.0这个版本以前，binlog只支持`STATEMENT`这种格式！而这种格式在读已提交(Read Commited)这个隔离级别下主从复制是有bug的，因此Mysql将可重复读(Repeatable Read)作为默认的隔离级别！

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/725429-20190311134942591-1582271936.jpg">

在master上执行的顺序为先删后插！而此时binlog为STATEMENT格式，它记录的顺序为先插后删！从(slave)同步的是binglog，因此从机执行的顺序和主机不一致！就会出现主从不一致！

解决方案有两种：
(1)隔离级别设为**可重复读(Repeatable Read)**,在该隔离级别下引入间隙锁。当`Session 1`执行delete语句时，会锁住间隙。那么，`Ssession 2`执行插入语句就会阻塞住！
(2)将binglog的格式修改为row格式，此时是基于行的复制，自然就不会出现sql执行顺序不一样的问题！奈何这个格式在mysql5.1版本开始才引入。因此由于历史原因，mysql将默认的隔离级别设为**可重复读(Repeatable Read)**，保证主从复制不出问题！

### 聚簇索引和非聚簇索引？（百度测开）

**<font color='red'>聚簇索引和⾮聚簇索引最主要的区别是数据和索引是否分开存储。⼀张表只存在⼀个聚簇索引，但可以有多个⾮聚簇索引。</font>**

1. 聚集索引即索引结构和数据⼀起存放的索引。主键索引属于聚集索引

> **优点：**聚集索引的查询速度⾮常的快，因为整个B+树本身就是⼀颗多叉平衡树，叶⼦节点也都是有序的，定位到索引的节点，就相当于定位到了数据。
>
> **缺点：**
>
> 1. 依赖于有序的数据，不是有序的数据的话，插⼊或查找的速度肯定⽐较慢。
>
> 2. 更新代价⼤。

2. ⾮聚集索引即索引结构和数据分开存放的索引。叶⼦节点存的是键值和数据所在物理地址

> **优点：**更新代价⽐聚集索引要⼩ 。
>
> **缺点：**
>
> 1. 依赖于有序的数据，不是有序的数据的话，插⼊或查找的速度肯定⽐较慢。
>
> 2. 可能会⼆次查询(回表)，当查到索引对应的指针或主键后，可能还需要根据指针或主键再到数据⽂件或表中查询

### InnoDB和MyISAM的比较？（用友Java）

- 事务：InnoDB 是`事务型`的，可以使⽤ Commit 和 Rollback 语句。
- 并发：MyISAM 只⽀持`表级锁`，⽽ InnoDB 还⽀持`⾏级锁`。
- 外键：InnoDB ⽀持`外键`。
- 备份：InnoDB ⽀持在线热备份。
- 崩溃恢复：MyISAM 崩溃后发⽣损坏的概率⽐ InnoDB ⾼很多，⽽且恢复的速度也更慢。
- 其它特性：MyISAM ⽀持压缩表和空间数据索引。
- Innodb 主键索引的叶⼦节点是数据⽂件，辅助索引的叶⼦节点是主键的值。MyISAM 的主键索引
  和辅助索引，叶⼦节点都是数据⽂件的指针
- Innodb 不保存表的⾏数，执⾏ select count(*) from tb需要全表扫描，而MyISAM ⽤⼀个变量保存
  了整个表的⾏数，执⾏上述语句只需要读取该变量，速度很快
- Innodb 所有的表在磁盘上保存在⼀个⽂件中，而MyISAM 存储成三个⽂件。

### 哪些字段适合建立索引，哪些情况不适合？

#### 适合建立索引

1. 频繁作为where条件语句查询的字段
2. 关联字段需要建⽴索引，例如外键字段，student表中的classid, classes表中的schoolid 等
3. 排序字段可以建⽴索引
4. 分组字段可以建⽴索引，因为分组的前提是排序
5. 统计字段可以建⽴索引，例如count(),max()

#### 不适合建立索引

1. 频繁更新的字段不适合建⽴索引
2. where条件中⽤不到的字段不适合建⽴索引
3. 表数据可以确定⽐较少的不需要建索引
4. 数据重复且发布⽐较均匀的的字段不适合建索引（唯⼀性太差的字段不适合建⽴索引），例如性别，真假值

5. 参与列计算的列不适合建索引

### 索引失效的情况（用友Java）？

1. 使用`!=` 或者`<>`导致索引失效
2. `OR`引起索引的失效，OR导致索引是在特定情况下的，并不是所有的OR都是使索引失效，`如果OR连接的是同一个字段，那么索引不会失效，反之索引失效`
3. 模糊查询导致索引失效，当`%`放在第一个位置是不走索引的
4. 运算符导致的索引失效，如果你对列进行了`（+，-，*，/，!）`, 那么都将不会走索引
5. 函数导致的索引失效，如果使用函数在索引列，这是不走索引的
6. `NOT IN`、`NOT EXISTS`导致索引失效

### 一条SQL语句在执行时，其底层经历了哪些过程？

<font color='blue'>连接器、查询缓存、分析器、优化器、执行器</font>

- 一条SQL语句从客户端传过来首先会创建一个连接，用username和password认证身份
- 建立连接后先去查询缓存<font color='blue'>（MySQL8.0已删去）</font>
- 经过缓存器后来到分析器，先做词法分析分析出sql语句中的关键字，然后做语法分析判断是否有语法错误
- 经过分析后MySQL知道你要做什么了，但是在实际执行之前还得经过优化器优化一下，在表中有多个索引的时候，由优化器来决定使用哪个索引或者有多表关联（join）的时候决定连接顺序选择效率高的方案
- 执行器开始执行之前会验证是否有读/写权限没有则返回权限错误，有的话就打开表调用指定的存储引擎接口获取执行结果集返回给客户端

### char和varchar区别？

1. <font color='blue'>char的长度是不可变的，而varchar的长度是可变的</font>，也就是说，定义一个char[10]和varchar[10],如果存进去的是‘csdn’,那么char所占的长度依然为10，除了字符‘csdn’外，后面跟六个空格，而varchar就立马把长度变为4了，取数据的时候，char类型的要用trim()去掉多余的空格，而varchar是不需要的。
2. <font color='blue'>char的存取速度还是要比varchar要快得多</font>，因为其长度固定，方便程序的存储与查找；但是char也为此付出的是空间的代价，因为其长度固定，所以难免会有多余的空格占位符占据空间，可谓是以空间换取时间效率，而varchar是以空间效率为首位的。
3. <font color='blue'>char的存储方式是，对英文字符（ASCII）占用1个字节，对一个汉字占用2个字节；而varchar的存储方式是，对每个英文字符占用2个字节，汉字也占用2个字节</font>。

### drop，truncate，delete的区别？

1. **drop（删除表）：**删除内容和定义，释放空间。简单来说就是把整个表去掉；
2. **truncate（清空表中的数据）：**删除内容，释放空间但不删除定义（保留表的数据结构）。与drop不同的是，只是清空数据⽽已。注意：truncate不能删除⾏数据，要删就要把表清空；
3. **delete（删除表中的数据）：**delete语句⽤于删除表中的⾏。delete语句执⾏删除的过程就是每次从表中删除⼀⾏，并且同时将该⾏的删除操作作为事务记录在⽇志中保存以便进⾏回滚操作；
4. **执⾏速度**，⼀般来说: drop> truncate > delete。
5. delete语句是数据库操作语⾔(dml)，这个操作会放到 rollback segement 中，事务提交之后才⽣效；如果有相应的 trigger，执⾏的时候将被触发。 truncate、drop 是数据库定义语⾔(ddl)，操作⽴即⽣效，原数据不放到 rollback segment 中，不能回滚，操作不触发 trigger。 

### MySQL中int(5) 中的5代表什么意思？

对于int型，MySQL支持指定<font color='red'>显示宽度</font>，表示如果数值宽度小于5位，则填满宽度，保证总宽度为5位。

### SQL字段执行顺序？（用友Java）

from，join，on，where，group by，avg（sum...），having，select，distinct，order by，limit

### explain记得哪些字段？解释一下（用友Java）

Explain可以模拟优化器执行SQL查询语句，从而知道MySQL是如何处理你的SQL语句的，分析所查询的语句或者表结构的性能瓶颈。

````shell
mysql> explain select * from staff;
+----+-------------+-------+------+---------------+------+---------+------+------+-------+
| id | select_type | table | type | possible_keys | key  | key_len | ref  | rows | Extra |
+----+-------------+-------+------+---------------+------+---------+------+------+-------+
|  1 | SIMPLE      | staff | ALL  | NULL          | NULL | NULL    | NULL |    2 | NULL  |
+----+-------------+-------+------+---------------+------+---------+------+------+-------+
1 row in set
````

1. <font color='blue'>id</font>：SQL查询中的序列号，id列数字越大越先执行，id相同自上而下
2. <font color='blue'>select_type</font>：查询类型
   - SIMPLE：简单selcet
   - PRIMARY：最外层的select
   - UNION：UNION中第二个或之后的select语句
   - SUBQUERY：子查询中的第一个select
3. <font color='blue'>table</font>：查询的表名，不一定是实际存在的表名
4. <font color='red'>type（重要）</font>：最重要的字段之一，显示查询使用了哪种类型
   - 最好到最差：**system（表中只有一行数据或者是空表，且只能用于myisam和memory表），const（最多只有一行记录匹配），eq_ref（多表join时，对于来自前面表的每一行，在当前表中只能找到一行），ref（对于来自前面表的每一行，在此表的索引中可以匹配到多行），fulltext，ref_or_null（跟ref类型类似，只是增加了null值的比较），index_merge（表示查询使用了两个以上的索引，最后取交集或者并集），unique_subquery（用于where中的in形式子查询，子查询返回不重复值唯一值，可以完全替换子查询，效率更高），index_subquery（适用于非唯一索引，可以返回重复值），range（索引范围查询），index（索引全表扫描，把索引从头到尾扫一遍），ALL（全表扫描）**
5. <font color='blue'>partitions</font>：显示分区表命中的分区情况
6. <font color='blue'>possible_keys</font>：查询可能使用到的索引
7. <font color='blue'>key</font>：查询真正使用到的索引
8. <font color='blue'>key_len</font>：查询用到的索引长度（字节数）
9. <font color='blue'>ref</font>：如果是使用的常数等值查询，这里会显示const，如果是连接查询，被驱动表的执行计划这里会显示驱动表的关联字段，如果是条件使用了表达式或者函数，或者条件列发生了内部隐式转换，这里可能显示为func
10. <font color='red'>rows（重要）</font>：mysql估算的需要扫描的行数（不是精确值），这个值非常直观显示 SQL 的效率好坏, 原则上 rows 越少越好
11. <font color='blue'>filtered</font>：这个字段表示存储引擎返回的数据在server层过滤后，剩下多少满足查询的记录数量的比例，注意是百分比，不是具体记录数
12. <font color='red'>extra（重要）</font>：EXplain 中的很多额外的信息会在 Extra 字段显示
    - **distinct**：在select部分使用了distinc关键字
    - **Using filesort**：当 Extra 中有 Using filesort 时, 表示 MySQL 需额外的排序操作, 不能通过索引顺序达到排序效果. 一般有 Using filesort, 都建议优化去掉, 因为这样的查询 CPU 资源消耗大.
    - **Using index**
      "覆盖索引扫描", 表示查询在索引树中就可查找所需数据, 不用扫描表数据文件, 往往说明**性能不错**
    - **Using temporary**
      查询有使用临时表, 一般出现于排序, 分组和多表 join 的情况, 查询效率不高, 建议优化.

### 听说过buffer pool和double write buffer吗？

MySQL采用buffer机制，避免每次读写进行磁盘IO，提升效率

<font color='blue'>缓冲池（buffer pool）、写缓冲（change buffer）、日志缓冲（log buffer）</font>

MySQL的buffer一页的大小是16K，文件系统一页的大小是4K，也就是说，MySQL将buffer中一页数据刷入磁盘，要写4个文件系统里的页。如果执行到一半断电，会造成所谓的“页数据损坏”，同时redo log无法修复这类“页数据损坏”的异常，修复的前提是“页数据正确”并且redo log日志正常。

<font color='red'>double write buffer是mysql 系统表空间的一块存储区域</font>，分为内存和磁盘的两层架构。传统的buffer，大部分是内存存储，而doublewrite buffer里的数据是需要落磁盘的。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/aHR0cHM6Ly9tbWJpei5xcGljLmNuL3N6X21tYml6X3BuZy9ZcmV6eGNraFlPeGlicmlhY0lpY1hoaGZ6MW1vQ0Q3SFlUckVPVnJNdGljSmc3UVFkRDFlT1Jvb2ZBdTNBUUJHeFVoOHQ4MkRqRVZmQXZkaFRIZ1UwVDE0N0EvNjQw.png">

如上图所示，当有页数据要刷盘时：

**第一步**：页数据先memcopy到DWB的内存里；

**第二步**：DWB的内存里，会先刷到DWB的磁盘上；

**第三步**：DWB的内存里，再刷到数据磁盘存储上；

**<u>画外音：DWB由128个页构成，容量只有2M，步骤2和步骤3要写2次磁盘，这就是“Double Write”的由来。</u>**

#### DWB为什么能解决“页数据损坏”问题呢？

假设步骤2掉电，磁盘里依然是1+2+3+4的完整数据。<font color='red'>画外音：只要有页数据完整，就能通过redo还原数据。</font>

假如步骤3掉电，DWB里存储着完整的数据。<font color='red'>所以，一定不会出现“页数据损坏”问题。</font>

MySQL有很强的**数据安全性机制**：

（1）在异常崩溃时，如果不出现“页数据损坏”，能够通过redo恢复数据；

（2）在出现“页数据损坏”时，能够通过double write buffer恢复页数据；

### Mysql慢查询如何优化？（用友Java）

MySQL的慢查询，全名是**慢查询日志**，是MySQL提供的一种日志记录，用来记录在MySQL中**响应时间超过阀值**的语句。具体环境中，运行时间超过`long_query_time（默认10s）`值的SQL语句，则会被记录到慢查询日志中。

- <font color='red'>索引没有起到作用</font>
  - 使用到`like模糊查询`时，匹配字符串第一个位置不能为`%`，否则不会起作用
  - 使用多列索引查询时，只有查询条件使用了这些字段中的第一个字段时，索引才会被使用
- <font color='red'>优化数据库结构</font>
  - **将字段很多的表分解成多个表。**对于字段比较多的表，如果有些字段的使用频率很低，可以将这些字段分离出来形成新表。因为当一个表的数据量很大时，会由于使用频率低的字段的存在而变慢。
  - **增加中间表。**对于需要经常联合查询的表，可以建立中间表以提高查询效率。通过建立中间表，把需要经常联合查询的数据插入到中间表中，然后将原来的联合查询改为对中间表的查询，以此来提高查询效率。
- <font color='red'>分解关联查询</font>：将一个大的查询分解为多个小查询是很有必要的
- <font color='red'>优化LIMIT分页</font>：尽可能的使用索引覆盖扫描，而不是查询所有的列

### left join 为什么需要小表驱动大表，原理是什么?

MySQL的join实现原理是，<font color='red'>以驱动表的数据为基础，“嵌套循环”去被驱动表匹配记录</font>

```powershell
select * from a join b on a.bid = b.id;
```

假设a表中有10000条数据，b表中有20条数据

这里有2个过程，b表数据最少，查询引擎优化选择b为驱动表

- 循环b表的20条数据
- 去a表的10000条数据中匹配，这个匹配过程是B+树的查找过程，比循环取数要快的多

1. 小表驱动的方式

```powershell
for 20条数据
	匹配10000条数据（根据on a.id = b.id的连接条件，进行B+查找）
------------------------
查找次数（20+log10000）
```

2. 大表驱动的方式

```powershell
for 10000条数据
	匹配20条数据（根据on a.id = b.id的连接条件，进行B+查找）
------------------------
查找次数（10000+log20）
```

### left join和inner join的含义？（用友Java）（携程测开）

1. `inner join`，内连接,显示两个表中有联系的所有数据;
2. `left join`，左链接,以左表为参照,显示所有数据,右表中没有则以null显示
3. `right join`，右链接,以右表为参照显示数据，左表中没有则以null显示

#### 笛卡尔连接

> MySQL cross join是mysql中的一种连接方式，区别于内连接和外连接，对于cross join连接来说，其实使用的就是笛卡尔连接。**在MySQL中，当CROSS JOIN不使用WHERE子句时，CROSS JOIN产生了一个结果集，该结果集是两个关联表的行的乘积**。通常，如果每个表分别具有n和m行，则结果集将具有n*m行
>
> **<font color='red'>cross join的时候是不需要on或者using关键字的，这个是区别于inner join和join的</font>**

<img src="https://img-blog.csdnimg.cn/20191031192720529.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9zbWlsZW5pY2t5LmJsb2cuY3Nkbi5uZXQ=,size_16,color_FFFFFF,t_70">

### MySQL中IN和EXISTS有什么不同？

`exists`关键字后面的参数是一个任意的子查询，系统对子查询进行运算以判断它是否返回行，如果至少返回一行，那么`exists`的结果为`true` ,此时外层的查询语句将进行查询；如果子查询没有返回任何行，那么`exists`的结果为`false`,此时外层语句将不进行查询。

`in`关键字进行子查询时，内层查询语句仅仅返回一个数据列，这个数据列的值将提供给外层查询语句进行比较操作。

- IN查询在内部表和外部表上都可以使用到索引；
- Exists查询仅在内部表上可以使用到索引；
- 当**子查询结果集**很大，而外部表较小的时候，Exists的Block Nested Loop(Block 嵌套循环)的作用开始显现，并弥补外部表无法用到索引的缺陷，查询效率会优于IN。
- 当**子查询结果集**较小，而外部表很大的时候，Exists的Block嵌套循环优化效果不明显，IN 的外表索引优势占主要作用，此时IN的查询效率会优于Exists。
- 网上的说法不准确。其实“表的规模”不是看内部表和外部表，而是外部表和子查询结果集。

<font color='red'>外层查询表小于子查询表，则用exists，外层查询表大于子查询表，则用in，如果外层和子查询表差不多，则爱用哪个用哪个</font>

### MySQL中count(字段),count(id),count(1)和count(*)区别？

count() 是一个聚合函数，对于返回的结果集，一行行地判断，如果 count 函数的参数不是 NULL，累计值就加 1，否则不加。最后返回累计值。

count(*)、count(1)和count(id) 都表示返回满足条件的结果集的总行数；而 count(字段)，则表示返回满足条件的数据行里面，参数“字段”不为 NULL 的总个数。

- count(可空字段)：扫描全表，读到server层，判断字段可空，拿出该字段所有值，判断每一个值是否为空，不为空则累加
- count(非空字段)和count(id)：扫描全表，读到server层，判断字段不可空，按行累加
- count(1)：扫描全表，但不取值，server层收到的每一行都是1，判断不可能是null，按值累加
- `count(*)：MySQL 执行count(*)在优化器做了专门优化`。因为count(*)返回的行一定不是空。扫描全表，但是不取值，按行累加

### 数据库三大范式？（用友Java）

#### 第一范式

第一范式是最基本的范式。如果`数据库表中的所有字段值都是不可分解的原子值`，就说明该数据库表满足了第一范式。

#### 第二范式

第二范式在第一范式的基础之上更进一层。`第二范式需要确保数据库表中的每一列都和主键相关，而不能只与主键的某一部分相关`（主要针对联合主键而言）。也就是说在一个数据库表中，一个表中只能保存一种数据，不可以把多种数据保存在同一张数据库表中。

#### 第三范式

`第三范式需要确保数据表中的每一列数据都和主键直接相关，而不能间接相关`。

比如在设计一个订单数据表的时候，可以将客户编号作为一个外键和订单表建立相应的关系。而不可以在订单表中添加关于客户其它信息（比如姓名、所属公司等）的字段。如下面这两个表所示的设计就是一个满足第三范式的数据库表。

### MySQL中日期用那个 timestamp 和 datetime 区别？

|   类型    | 占据子节 |                           表示范围                           |  默认值  |
| :-------: | :------: | :----------------------------------------------------------: | :------: |
| datetime  |  8子节   | '1000-01-01' 00:00:00.000000 to '9999-12-31 23:59:59.999999' |   null   |
| timestamp |  4子节   | '1970-01-01' 00:00:01.000000 to '2038-01-19 03:14:07.999999' | 当前时间 |

### 关系型数据库和非关系型数据库区别？

1. 数据存储方式不同（表结构）
2. 扩展方式不同（纵向扩展/分布式）
3. 对事务性的支持不同（回滚）

### 各种SQL语句加的什么锁？

在4个事务隔离级别中，除了在串行化(Serializable)时会加共享锁，其他的都不加锁，即`快照读`。

#### 加了锁的查询

加锁select主要指：

- select ...` for update`
- select ... `lock in share mode`

1. 当使用唯一索引来搜索唯一行的语句时，使用记录锁(record lock)。如：

```powershell
select * from t where id = 10  for update; # id是唯一索引列
```

2. 其他情况，包括id列没有索引或者是非唯一索引又或者是搜索条件里有多个查询条件(使每个列都有唯一索引)，则使用间隙锁与临键锁。

#### update和delete

1. 当使用唯一索引列确定的唯一数据行上进行的update/delete，也使用记录锁：

```powershell
update t set number=10 where id=1;
```

2. 其他情况，包括id列没有索引或者是非唯一索引又或者是搜索条件里有多个查询条件(使每个列都有唯一索引)，**则**加排他临界锁(exclusive next-key lock)。

#### insert

insert会用排它锁封锁被插入的索引记录，然后在插入区间加插入意向锁(insert intention lock)。

### 索引底层是B+树，为什么不是红黑树？

**为什么不用哈希？**哈希只适合等值查询，不适合范围查询，存在哈希冲突问题

**为什么不用二叉树？**树的高度不均匀，不能自平衡，查找效率和数据有关（树的高度），且IO代价高

**为什么不用红黑树？**是一种特化的平衡二叉树，树的高度随着数据量增加而增加，IO代价高

**为什么不用B树？**叶子节点和非叶子节点都保存数据，相同的数据量，B+树更矮壮，IO读写次数更少

## Redis

### Redis是什么？优缺点？

定义：Redis本质上是一个Key-Value类型的内存数据库，很像Memcached，整个数据库加载在内存当中操作，定期通过异步操作把数据库中的数据flush到硬盘上进行保存。

<font color='red'>优点：</font>

- **读写性能极高**， Redis能读的速度是110000次/s，写的速度是81000次/s。
- **支持数据持久化**，支持AOF和RDB两种持久化方式。
- **支持事务**， Redis的所有操作都是原子性的，意思就是要么成功执行要么失败完全不执行。单个操作是原子性的。`多个操作也支持事务，即原子性，通过MULTI和EXEC指令包起来`。
- **数据结构丰富**，除了支持string类型的value外，还支持hash、set、zset、list等数据结构。
- **支持主从复制**，主机会自动将数据同步到从机，可以进行读写分离。
- **丰富的特性** – Redis还支持 publish/subscribe，通知，key 过期等特性。

<font color='red'>缺点：</font>

- 数据库容量受到物理内存的限制，不能用作海量数据的高性能读写，因此Redis适合的场景主要局限在较小数据量的高性能操作和运算上

### Redis各个数据结构的底层结构？（用友Java）

**String：**简单动态字符串（SDS）

**Hash：**压缩列表、哈希表

**List：**压缩列表、双向链表

**Set：**整数数组、哈希表

**Zset：**压缩列表、跳跃表

<img src="https://mmbiz.qpic.cn/mmbiz_png/EoJib2tNvVtcTPsiaXJOBib6514wp74WvjuqiaaaBTiaajCRiaGZgIf9JwIRSIKoa4CTqbk6A5oCv6aibeaNEj9gqCNNg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1">

### Redis为何用跳表而不用红黑树？

1. 在做范围查找的时候，平衡树比skiplist操作要复杂。在平衡树上，我们找到指定范围的小值之后，还需要以中序遍历的顺序继续寻找其它不超过大值的节点。如果不对平衡树进行一定的改造，这里的中序遍历并不容易实现。而在skiplist上进行范围查找就非常简单，只需要在找到小值之后，对第1层链表进行若干步的遍历就可以实现。
2. 平衡树的插入和删除操作可能引发子树的调整，逻辑复杂，而skiplist的插入和删除只需要修改相邻节点的指针，操作简单又快速。
3. 从内存占用上来说，skiplist比平衡树更灵活一些。一般来说，平衡树每个节点包含2个指针（分别指向左右子树），而skiplist每个节点包含的指针数目平均为1/(1-p)，具体取决于参数p的大小。如果像Redis里的实现一样，取p=1/4，那么平均每个节点包含1.33个指针，比平衡树更有优势。
4. 查找单个key，skiplist和平衡树的时间复杂度都为O(logn)，大体相当；而哈希表在保持较低的哈希值冲突概率的前提下，查找时间复杂度接近O(1)，性能更高一些。所以我们平常使用的各种Map或dictionary结构，大都是基于哈希表实现的。
5. 从算法实现难度上来比较，skiplist比平衡树要简单得多。

### Redis的三种高级数据结构？

- **HyperLoglog（统计UV，独立用户）**
  - 采用一种基数算法，用于完成独立总数的统计
  - 占据空间小，无论统计多少个数据，只占12k的内存空间
  - 不精确的统计算法，标准误差0.81%
- **Bitmap（统计DAU，日活跃用户）**
  - 不是一种独立的数据结构，实际上是字符串
  - 支持按位存取数据，可以将其看成是byte数组
  - 适合存储大量的连续的数据的布尔值
- **Geospatial**
  - 主要用于存储地理位置信息，并对存储的信息进行操作，适用场景如朋友的定位、附近的人、打车距离计算等

### Redis加锁的几种方式？

1. <font color='red'>INCR</font>，key不存在，那么key的值会先被初始化为 0 ，然后再执行INCR操作进行加1，然后其它用户在执行INCR操作进行加一时，如果返回的数大于1，说明这个锁正在被使用当中
2. <font color='red'>SETNX</font>，如果 key 不存在，将 key 设置为 value；如果 key 已存在，则 SETNX 不做任何动作
3. <font color='red'>SET</font>，<font color='blue'>上面两种方法都有一个问题，都需要设置 key 过期</font>。A请求服务器设置key的值，如果设置成功就表示加锁成功；B也去请求服务器设置key的值，如果返回失败，那么就代表加锁失败；A执行代码完成，删除锁；B在等待一段时间后在去请求设置key的值，设置成功；B执行代码完成，删除锁

### Redis单线程为何能支撑高并发?

- 纯内存操作
- 核心是基于非阻塞的IO多路复用机制（epoll）
- 单线程避免了多线程的频繁上下文切换问题

### Redis string和zset的实现

`SDS`的结构有点类似于`Java`中的`ArrayList`。`buf[]`表示真正存储的字符串内容，`alloc`表示所分配的数组的长度，`len`表示字符串的实际长度，并且由于`len`这个属性的存在，`Redis`可以在`O(1)`的时间复杂度内获取数组长度。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1593641-20200831194045515-1907392740.png">

zset为有序（有限score排序，score相同则元素字典序），自动去重的集合数据类型，其底层实现为`字典（dict） + 跳表（skiplist）`，当数据比较少的时候用**ziplist**编码结构存储。

同时满足以下两个条件采用ziplist存储：

- 有序集合保存的元素数量小于默认值128个
- 有序集合保存的所有元素的长度小于默认值64字节

当ziplist作为zset的底层存储结构时候，每个集合元素使用两个紧挨在一起的压缩列表节点来保存，第一个节点保存元素的成员，第二个元素保存元素的分值。zset是一个dict结构，主要key是其集合元素，而value就是对应分值，而zkiplist作为跳跃表，按照分值排序，方便定位成员

### 讲下Redis持久化策略和缓存失效策略和淘汰策略？

#### 缓存失效策略

主要有：定时删除策略，惰性删除策略，定期删除策略

**定时删除策略** 

 在设置 key 的过期时间的同时，为该 key 创建一个定时器，让定时器在 key 的过期时间来临时，对 key 进行删除。 

-  优点：保证内存尽快释放。 

-  缺点：若 key 过多，删除这些 key 会占用很多 CPU 时间， 而且每个 key 创建一个定时器，性能影响严重。 

 **惰性删除策略** 

 key 过期的时候不删除，每次从数据库获取 key 的时候去检查是否过期，若过期，则删除，返回 null。

-  优点：CPU 时间占用比较少。 

-  缺点：若 key 很长时间没有被获取， 将不会被删除，可能造成内存泄露。 

 **定期删除策略** 

 每隔一段时间执行一次删除过期 key 操作。 

-  优点：可以控制删除操作的时长和频率，来减少 CPU 时间占用，可以避免惰性删除时候内存泄漏的问题。 

-  缺点：对内存友好方面，不如定时策略；对 CPU 友好方面，不如惰性策略 

 **Redis 一般采用：惰性策略 + 定期策略两个相结合。**

#### 淘汰策略

1. **no-eviction：** 当内存使用达到上限，所有需要申请内存的命令都会异常报错
2. **allkeys-lru：** 先试图移除一部分最近未使用的 key 
3. **volatile-lru：** 从已设置过期时间的数据集中淘汰一部分最近使用较少的 
4. **allkeys-random：** 随机淘汰某一个键
5. **volatile-random：** 淘汰任意键，但只限于有过期设置的驱逐键
6. **volatile-ttl：** 优先移除具有更早失效时间的 key

----------

7. **volatile-lfu：**从已设置过期时间的数据集中挑选最不经常使用的数据淘汰
8. **allkeys-lfu**：挑选最不经常使用的数据淘汰

#### 持久化策略

1. **RDB 持久化：** 将 Reids 在内存中的数据库记录定时 dump 到磁盘上的 RDB 持久化。 
2. **AOF（append only file）持久化：** 将 Redis 的操作日志以追加的方式写入文件。
   1. AOF_FSYNC_**NO** ：不保存
   2. AOF_FSYNC_**EVERYSEC** ：每一秒钟保存一次
   3. AOF_FSYNC_**ALWAYS** ：每执行一个命令保存一次

**区别：**

- RDB 持久化是指在指定的时间间隔内将内存中的数据集快照写入磁盘，实际操作过程是 fork 一个子进程，先将数据集写入临时文件，写入成功后，再替换之前的文件，用二进制压缩存储。

- AOF 持久化以日志的形式记录服务器所处理的每一个写、删除操作，查询操作不会记录，以文本的方式记录，可以打开文件看到详细的操作记录。

**优缺点：**

- **RDB优点**：RDB 是紧凑的二进制文件，比较适合备份，全量复制等场景；RDB 恢复数据远快于AOF
- **RDB缺点**：RDB 无法实现实时或者秒级持久化；新老版本无法兼容 RDB 格式

------------

- **AOF优点**：可以更好地保护数据不丢失；append-only 模式写入性能比较高；适合做灾难性的误删除紧急恢复
- **AOF缺点**：对于同一份文件，AOF 文件要比 RDB 快照大；AOF 开启后，会对写的 QPS 有所影响，相对于 RDB 来说 写 QPS 要下降；数据库恢复比较慢， 不合适做冷备

### Redis事务跟Mysql事务有什么区别?

#### 事务命令

**Mysql**

- `Begin`：显示的开启一个事务
- `Commit`：提交事务，将对数据库进行的所有的修改变成永久性
- `Rollback`：结束用户的事务，并撤销现在正在进行的未提交的修改

**Redis**

- `Multi`：标记事务的开始
- `Exec`：执行事务的commands队列
- `Discard`：结束事务，并清除commands队列

#### 默认状态

mysql会默认开启一个事务，且缺省设置是自动提交，即每成功执行sql，一个事务就会马上commit，所以不能rollback。

redis默认不会开启事务，即command会立即执行，而不会排队，并不支持rollback；**Redis事务不支持Rollback**

#### 使用方式

Mysql：用Begin、Rollback、commit显式开启并控制一个 新的 Transaction；执行命令 set autocommit=0，用来禁止当前会话自动commit，控制 默认开启的事务

Redis：用multi、exec、discard，显式开启并控制一个Transaction

#### 实现原理

- mysql实现事务，是基于**undo/redo日志**；
- `undo`记录**`修改前`**状态，**`rollback`**基于**undo**日志实现；
- `redo`记录**`修改后`**的状态，**`commit`**基于**redo**日志实现；
- 在mysql中无论是否开启事务，**sql都会被立即执行并返回执行结果**，只是**`事务开启`**后`执行后的状态`只是记录在`redo日志`，执行`commit`之后，数据才会被**`写入磁盘；`**

---------

- redis实现事务，是基于`commands队列；`
- 如果**没有开启**事务，command将会被立即执行并返回执行结果，并且**直接写入磁盘**；
- 如果**事务开启**，command不会被立即执行，而是**排入队列**，并返回**`排队状态`**（具体依赖于客户端（例如：spring-data-redis）自身实现），调用**`exec`**才会执行**`commands队列；`**

### Redis6.0支持多线程，单线程做的这么好，为什么还要多线程？

一般来说 Redis 的瓶颈并不在 CPU，而在内存和网络。如果要使用 CPU 多核，可以搭建多个 Redis 实例来解决。

**<font color='blue'>Redis6.0之前为什么一直不使用多线程？</font>**

1. 使用了单线程后，可维护性高。多线程模型虽然在某些方面表现优异，但是它却引入了程序执行顺序的不确定性，带来了并发读写的一系列问题，增加了系统复杂度、同时可能存在线程切换、甚至加锁解锁、死锁造成的性能损耗。
2. Redis 通过 AE 事件模型以及 IO 多路复用等技术，处理性能非常高，因此没有必要使用多线程。
3. 单线程机制使得 Redis 内部实现的复杂度大大降低，Hash 的惰性 Rehash、Lpush 等等 “线程不安全” 的命令都可以无锁进行。

**<font color='blue'>Redis 6.0 为什么要引入多线程呢？</font>**

内存不够的话，可以加内存或者做数据结构优化和其他优化等，但网络的性能优化才是大头，`网络 IO 的读写在 Redis 整个执行期间占用了大部分的 CPU 时间`，如果把网络处理这部分做成多线程处理方式，那对整个 Redis 的性能会有很大的提升。

**主要原因：**

- 可以充分利用服务器 CPU 资源，目前主线程只能利用一个核
- 多线程任务可以分摊 Redis 同步 IO 读写负荷

**<font color='blue'>Redis开启多线程后，是否会存在线程并发安全问题？</font>**

不会，`Redis 的多线程部分只是用来处理网络数据的读写和协议解析，执行命令仍然是单线程顺序执行`。

**<font color='blue'>Redis线程中经常提到IO多路复用，如何理解？</font>**

这是 IO 模型的一种，即经典的 Reactor 设计模式，有时也称为异步阻塞 IO。多路指的是多个 Socket 连接，复用指的是复用一个线程。多路复用主要有三种技术：Select，Poll，Epoll。

Epoll 是最新的也是目前最好的多路复用技术。采用多路 I/O 复用技术可以让单个线程高效的处理多个连接请求（尽量减少网络 IO 的时间消耗），且 Redis 在内存中操作数据的速度非常快（内存内的操作不会成为这里的性能瓶颈），主要以上两点造就了 Redis 具有很高的吞吐量。（具体见操作系统模块）

### RDB快照会影响目前线程执行任务嘛？

Redis提供两个命令生成RDB文件：

- `save`：在主线程中执行，但会导致阻塞；
- `bgsave`：创建一个子进程，专门用于写入RDB文件，避免了主线程的阻塞，<font color='red'>也是Redis RDB文件生成的默认配置</font>。

### Redis做快照时数据还能被增删改吗？

Redis借助操作系统提供的写时复制技术（Copy-On-Write，COW），在执行快照的同时，正常处理写操作。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/4dc5fb99a1c94f70957cce1ffef419cc.jpg">

<font color='blue'>bgsave子进程是由主线程fork生成的，可以共享主线程的所有内存数据</font>。当主线程要修改数据时，通过COW复制一份副本出来给bgsave子进程，这既保证快照的完整性，也允许主线程同时对数据进行修改，避免了对正常业务的影响。

### Redis缓存和本地内存有什么区别？

1. 读写速度，不考虑并发问题，本地缓存自然是最快的。但是如果本地缓存不加锁，那应并发了咋办呢？所以，我们以加锁方式再比较一次
2. 场景使用，同一数据，从数据库取出来，放到redis只要一次，而放到本地缓存，则需要n个集群次
3. 本地缓存无法用于重复点击，重复点击会分发请求到多台服务器，而用本地缓存只能防止本机重复点击，redis则可以防止，但是时间间隔也需要在redis的读写差之外
4. redis内存可能n多扩充，而本地扩大堆内存代价是很大的
5. 本地缓存需要自己实现过期功能，实现不好可能导致极其严重的后果，而redis经过大量的流量验证，安全可靠
6. 本地缓存无法提供丰富的数据结构，redis可以
7. redis可以写磁盘，持久化，本地缓存不可以或者说很麻烦要考虑的东西太多
8. 各位开发同学水平差别大，使用本地缓存极有可能导致严重的线程安全问题，并发考虑严重
9. 加本地缓存后，代码复杂度急剧上升，后面进来的开发很难一下领会原有开发想法，间接提升维护成本

### Redis设置键的生存时间和过期时间有哪些命令？

- EXPIRE 以秒为单位，设置键的生存时间
- PEXPIRE 以毫秒为单位，设置键的生存时间

- EXPIREAT 以秒为单位，设置键的过期 UNIX 时间戳

- PEXPIREAT 以毫秒为单位，设置键的过期 UNIX 时间戳

### Redis命令行常用命令？

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/95EEDDE0535C63CC18F1DF47698EC90B.png">

### Redis 为什么不支持回滚？

1. 只有语法错误，Redis 才会执行失败，例如错误类型的赋值， 这就是说从程序层面完全可以捕获以及解决这些问题。
2. 支持回滚需要增加很多工作，不支持的情况下，Redis 可以保持简单、速度快的特性。

### 一个String类型的值能存储最大容量是多少？

512M

### Redis 各个数据类型最大存储量分别是多少?

1. **Strings 类型：** 一个 String 类型的 value 最大可以存储 512M 
2. **Lists 类型：** list 的元素个数最多为 2^32-1 个，也就是 4294967295 个。 
3. **Sets 类型：** 元素个数最多为 2^32-1 个，也就是 4294967295 个。 
4. **Hashes 类型：** 键值对个数最多为 2^32-1 个，也就是 4294967295 个。 
5. **Sorted sets 类型：** 跟 Sets 类型相似。

### Redis 集群的主从复制模型是怎样的？

Redis 中的主从复制，也就是 Master-Slave 模型，多个 Redis 实例间的数据同步以及 Redis 集群中数据同步会使用主从复制。 

 主从复制主要是数据同步， 数据同步分为**全量同步**和**增量同步**。 

 **全量同步：** 

 全量同步一般发生在 Slave 机器初始化阶段， 这时候 Slave 需要将 Master 上的所有数据都进行同步复制。 

 大概步骤如下所示：

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/FA6030375F978147E6A13D9EDFA797E8.png">

1. 从服务器发送 SYNC 命令，链接主服务器 
2. 主服务器收到 SYNC 命令后，进行存盘的操作，并继续收集后续的写命令，存储缓冲区 
3. 存盘结束后，将对应的数据文件发送到 Slave 中，完成一次全量同步 
4. 主服务数据发送完毕后，将进行增量的缓冲区数据同步 
5. Slave 加载数据文件和缓冲区数据，开始接受命令请求，提供操作

**增量更新：** 

 Slave 节点初始化完成之后，开始正常工作，Master 节点进行的写操作都会同步到 Slave 节点上面。Master 节点每执行一个写命令都会向从服务器发送相同的写命令，从服务器接收到命令，并执行。

### Redis 的主从复制模式有什么优缺点?

- **优点：** 可靠性相对于单个节点部署模式有所提高，实现读写分离提高读写效率

- **缺点：** 写数据依赖于主节点，主节点空间有限，而且主节点存在单点的风险

### Redis sentinel（哨兵）模式优缺点有哪些？

- **优点：** 保证高可用，各个节点自动故障转移

- **缺点：** 主从模式，依旧存在主节点单点风险，主从切换有丢失数据的问题

### 什么是 bigkey？ 有什么影响？

bigkey 是指存储 value 占用内存空间非常大的 key。例如一个 String 类型的 value 占用了 100MB 空间。

**bigkey 的影响主要体现在：** 

1.  **造成内存空间不平衡：** 如果 bigkey 存储量比较大，同一个 key 在同一个节点或者服务器中存储，造成一定的影响 
2.  **超时阻塞：** 由于占用空间比较大，那么操作起来效率肯定比较低，也就表示出现阻塞可能性增加 
3.  **网络阻塞：** 获取 bigkey 的时候，自然传输的数据量比较大，导致宽带的压力。

### Redis缓存雪崩、击穿、穿透？

#### 缓存雪崩

**<font color='red'>缓存雪崩：</font>**缓存雪崩指的是缓存同⼀时间⼤⾯积的失效，紧接着这些请求被全部转发到了数据库，导致数据库压⼒⼤增，严重的会造成数据库宕机，形成⼀系列连锁反应，造成整个系统崩溃。产⽣雪崩的原因主要有两个：

1. 缓存中有⼤量的数据同时过期，导致⼤量请求⽆法在redis中⽆法处理。
2. Redis宕机

**应对方案：**

**<font color='blue'>针对缓存⼤量数据同时过期：</font>**

1. 避免给⼤量业务数据设置相同的过期时间，业务场景中总会出现同时实效的case，⽐如基于订单的下单时间。对于这种场景，可以在过期时间后⾯加个随机的时间⽐如（1-3分钟）。这样既保证了业务基本在相近的时间过期，也不会在同时间集中过期。
2. 降级，如果雪崩已经产⽣，可以对业务进⾏降级，⾮核⼼数据直接返回指定的静态数据（缓存中没有也不去数据库请求），只有核⼼数据持续访问缓存（如果缓存没有，也可以去访问数据库，由于限制了⾮核⼼数据的请求，这个时候db的压⼒应该不⼤）。

**<font color='blue'>针对redis宕机：</font>**

1. 服务彻底熔断，当前进来后直接返回，不再访问数据库，对服务使⽤⽅来说，整个服务是不可⽤的，对业务的影响最⼤，但是彻底保护了数据库。
2. 请求限流，在业务系统的请求⼊⼝控制每秒进⼊服务的次数，限流的⽐例可以基于之前的数据进⾏分析，⽐如在雪崩前⼊⼝的qps是10000，其中9000被redis承载，1000进⼊了数据库（说明数据库能承载1000的qps），那么这个时候可以将⼊⼝的qps 限制为1000，这样既保证了数据库的安全，也不⾄于业务不可⽤（部分可⽤状态）。
3. 主从集群部署，实现redis的⾼可⽤，当主节点宕机后从节点可以切换为主节点继续提供服务。

#### 缓存击穿

**缓存击穿：**热点数据在redis中找不到，和雪崩相⽐，击穿对应的热点数据数据量⽐较⼩，但是这些数据的请求量⾮常⾼，导致⼤量请求都被打到了数据库。击穿发⽣在热点数据失效时。

**应对⽅案：**对于缓存击穿解决⽅案⽐较简单，对于热点数据可以设置永不过期，这样就解决了失效问题。

#### 缓存穿透

**缓存穿透：**缓存穿透是指查询的数据既不在缓存也不在数据库，请求redis时候发现缓存缺失，再去访问数据库，发现数据库也没有，所以⽆法补全缓存数据，导致每次查询都会去请求数据库，当有⼤量类似的请求场景时候，也会对数据库造成巨⼤的压⼒。

**<font color='blue'>发⽣穿透的场景：</font>**

1. 业务误操作导致本应该存在的数据被误删除
2. 恶意攻击，专⻔查询数据库中没有的数据，利⽤穿透的漏洞。
3. 设计问题，代码不严谨，已知可能为空的数据没有去做判断。

**<font color='blue'>应对⽅案：</font>**

1. 给缓存赋空值或者缺省值，⼀旦发现没有业务数据，可以赋为空置或者留⼀个标示值，⽐如有值的时候对应的值是⼀个list，如果发现没有业务数据可以付⼀个空的list，这样等下次再来访问时，发现redis已经有缺省值，可以直接返回，避免了多次访问数据库。
2. 通过业务规则判断，如果通过某些规则就可以知道没有数据，则可以直接不⽤访问。
3. 使⽤==布隆过滤器==，可以快速判断数据是否存在，避免从数据库中查询是否存在，减轻数据库的压⼒。

## Spring + SpringBoot

### MVC三层架构？

三层架构是指：视图层 View、服务层 Service，与持久层 Dao。它们分别完成不同的功能。

- `View 层：`用于接收用户提交请求的代码在这里编写
- `Service 层：`系统的业务逻辑主要在这里完成
- `Dao 层：`直接操作数据库的代码在这里编写

### 转发和重定向区别？（用友Java）

|     区别     |   转发forward()    | 重定向sendRedirect() |
| :----------: | :----------------: | :------------------: |
|    根目录    |  包含项目访问地址  |   没有项目访问地址   |
|    地址栏    |    不会发生变化    |      会发生变化      |
|   哪里跳转   | 服务器端进行的跳转 |  浏览器端进行的跳转  |
| 请求域中数据 |      不会丢失      |        会丢失        |

### interceptor和filter的区别？

#### filter

**主要用途：**Servlet中的过滤器Filter是实现了`javax.servlet.Filter接口`的服务器端程序，主要的用途是

- 设置字符集
- 控制权限
- 控制转向
- 业务逻辑判断

**生命周期：**它是随你的web应用启动而启动的，**只初始化一次**，以后就可以拦截相关请求，只有当你的web应用停止或重新部署的时候才销毁。

**工作流程：**在web.xml文件配置好要拦截的客户端请求，拦截请求；对请求或响应(Request、Response)统一设置编码，简化操作；进行逻辑判断，如用户是否已经登陆、有没有权限访问该页面等等工作；将请求交给Servlet进行处理并生成响应，最后Filter再对服务器响应进行后处理。

`Filter可以负责拦截多个请求或响应，一个请求或响应也可以被多个Filter拦截`

<img src="https://img2020.cnblogs.com/blog/1905499/202104/1905499-20210420144401528-598952803.png">

#### Interceptor

拦截器是在AOP中应用，在service或者一个方法前调用一个方法，或者在方法后调用一个方法，是基于`JAVA的反射机制`。

**Interceptor在SpringMVC中的工作流程：**

- 当你提交对Action(默认是.action结尾的url)的请求时，ServletDispatcher会根据你的请求，去调度并执行相应的Action
- 在Action执行之前，调用被Interceptor截取，Interceptor在Action执行前后执行
- SpringMVC中的Interceptor 拦截请求是通过HandlerInterceptor来实现的

在SpringMVC中定义一个Interceptor：

- 定义的Interceptor类实现了Spring 的HandlerInterceptor 接口，或者这个类继承实现了HandlerInterceptor接口的类
- 定义的Interceptor类实现Spring的WebRequestInterceptor接口，或者是继承实现了WebRequestInterceptor的类

> `preHandler`(HttpServletRequest request,HttpServletResponse response,Object handler)：该方法将在请求处理之前进行调用
>
> - 每个Interceptor的调用会依据它的声明顺序依次执行
> - 最先执行的都是Interceptor中的preHandle方法
> - 可以在这个方法中进行一些前置初始化操作或者是对当前请求的一个预处理
> - 也可以在这个方法中进行一些判断来决定请求是否要继续进行下去
> - 该方法的返回值是布尔值Boolean类型的，当它返回为false 时，表示请求结束，后续的Interceptor 和Controller 都不会再执行
> - 当返回值为true 时就会继续调用下一个Interceptor的preHandle 方法
> - 如果已经是最后一个Interceptor的时候就会是调用当前请求的Controller 方法

> `postHandle `(HttpServletRequest request, HttpServletResponse response, Object handle, ModelAndView modelAndView)：postHandle方法都只能是在当前所属的Interceptor的preHandle方法的返回值为true时才能被调用（**即在当前请求进行处理之后，也就是Controller方法调用之后执行**）
>
> - 会在DispatcherServlet进行视图返回渲染之前被调用
> - 可以在这个方法中对Controller处理之后的ModelAndView对象进行操作

> `afterCompletion`(HttpServletRequest request, HttpServletResponse response, Object handle, Exception ex)：需要当前对应的Interceptor的preHandle方法的返回值为true时才会执行
>
> - 该方法将在整个请求结束之后，也就是在DispatcherServlet渲染了对应的视图之后执行
> - 这个方法的主要作用是用于进行资源清理工作的

|                            Filter                            |                         Interceptor                          |                           Summary                            |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|             Filter 接口定义在 javax.servlet 包中             | 接口 HandlerInterceptor 定义在org.springframework.web.servlet 包中 |                                                              |
|                   Filter 定义在 web.xml 中                   |                                                              |                                                              |
| Filter在只在 Servlet 前后起作用。Filters 通常将请求和响应（request/response） 当做黑盒子，Filter 通常不考虑servlet 的实现 | 拦截器能够深入到方法前后、异常抛出前后等，因此拦截器的使用具有更大的弹性。允许用户介入（hook into）请求的生命周期，在请求过程中获取信息，Interceptor 通常和请求更加耦合 | 在Spring构架的程序中，要优先使用拦截器。几乎所有 Filter 能够做的事情， interceptor 都能够轻松的实现 |
|                 Filter 是 Servlet 规范规定的                 | 拦截器既可以用于Web程序，也可以用于Application、Swing程序中  |                         使用范围不同                         |
|   Filter 是在 Servlet 规范中定义的，是 Servlet 容器支持的    |        拦截器是在 Spring容器内的，是Spring框架支持的         |                           规范不同                           |
|              Filter 不能够使用 Spring 容器资源               | 拦截器是一个Spring的组件，归Spring管理，配置在Spring文件中，因此能使用Spring里的任何资源、对象，例如 Service对象、数据源、事务管理等，通过IoC注入到拦截器即可 |               Spring 中使用 interceptor 更容易               |
|             Filter 是被 Server(like Tomcat) 调用             |                 Interceptor 是被 Spring 调用                 |            **Filter 总是优先于 Interceptor 执行**            |

<img src="https://img2020.cnblogs.com/blog/1905499/202104/1905499-20210420143156159-643009886.png">

<img src="https://img2020.cnblogs.com/blog/1905499/202104/1905499-20210420143216592-551944328.png">

### Spring和SpringBoot区别？（用友Java）

Spring Boot是Spring的扩展，使用“约定优于配置”的理念开发，所以使用Spring Boot开发同样的功能，往往不需要像Spring那样手动配置。Spring Boot的自动装配，使各个功能模块的引入和配置变得非常简单，几乎可以做到0配置。

Spring Boot在应用容器配置、数据库配置、安全配置、测试和部署方便都与Spring有不同，但基本上都更加简单，受益于自动装配，<font color='red'>最大的区别就是Spring更多的需要人工配置，Spring Boot实现了自动装配</font>。

### 一个类里面有两个方法A和B，方法A 有@Transaction，B没有，但B调用了A，外界调用B会不会触发事务？

**不同类之间的方法调用**，如类A的方法a()调用类B的方法b()，这种情况事务是正常起作用的。只要方法a()或b()配置了事务，运行中就会开启事务，产生代理。

**同一个类中，一个方法调用另外一个有注解（比如@Async，@Transational）的方法，注解是不会生效的。**

### SpringBoot的自动装配了解吗？（用友Java）

SpringBoot 定义了一套接口规范，这套规范规定：SpringBoot 在启动时会扫描外部引用 jar 包中的`META-INF/spring.factories`文件，将文件中配置的类型信息加载到 Spring 容器（此处涉及到 JVM 类加载机制与 Spring 的容器知识），并执行类中定义的各种操作。对于外部 jar 来说，只需要按照 SpringBoot 定义的标准，就能将自己的功能装置进 SpringBoot。

> 自动装配可以简单理解为：**通过注解或者一些简单的配置就能在 SpringBoot 的帮助下实现某块功能。**

#### 如何实现自动装配？

SpringBoot核心注解`SpringBootApplication`

```java
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
<1.>@SpringBootConfiguration
<2.>@ComponentScan
<3.>@EnableAutoConfiguration
public @interface SpringBootApplication {
}
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Configuration //实际上它也是一个配置类
public @interface SpringBootConfiguration {
}
```

可以把 `@SpringBootApplication`看作是 `@Configuration`、`@EnableAutoConfiguration`、`@ComponentScan` 注解的集合。

- `@EnableAutoConfiguration`：启用 SpringBoot 的自动配置机制
- `@Configuration`：允许在上下文中注册额外的 bean 或导入其他配置类
- `@ComponentScan`： 扫描被`@Component` (`@Service`,`@Controller`)注解的 bean，注解默认会扫描启动类所在的包下所有的类 ，可以自定义不扫描某些 bean。如下图所示，容器中将排除`TypeExcludeFilter`和`AutoConfigurationExcludeFilter`。

#### @EnableAutoConfiguration:实现自动装配的核心注解

`EnableAutoConfiguration` 只是一个简单地注解，自动装配核心功能的实现实际是通过 `AutoConfigurationImportSelector`类。

```java
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@AutoConfigurationPackage //作用：将main包下的所欲组件注册到容器中
@Import({AutoConfigurationImportSelector.class}) //加载自动装配类 xxxAutoconfiguration
public @interface EnableAutoConfiguration {
    String ENABLED_OVERRIDE_PROPERTY = "spring.boot.enableautoconfiguration";
    Class<?>[] exclude() default {};
    String[] excludeName() default {};
}
```

#### AutoConfigurationImportSelector:加载自动装配类

```java
public class AutoConfigurationImportSelector implements DeferredImportSelector, BeanClassLoaderAware, ResourceLoaderAware, BeanFactoryAware, EnvironmentAware, Ordered {
}
public interface DeferredImportSelector extends ImportSelector {
}
public interface ImportSelector {
    String[] selectImports(AnnotationMetadata var1);
}
```

`AutoConfigurationImportSelector` 类实现了 `ImportSelector`接口，也就实现了这个接口中的 `selectImports`方法，该方法主要用于**获取所有符合条件的类的全限定类名，这些类需要被加载到 IoC 容器中**。

```java
private static final String[] NO_IMPORTS = new String[0];
public String[] selectImports(AnnotationMetadata annotationMetadata) {
        // <1>.判断自动装配开关是否打开
        if (!this.isEnabled(annotationMetadata)) {
            return NO_IMPORTS;
        } else {
          //<2>.获取所有需要装配的bean
            AutoConfigurationMetadata autoConfigurationMetadata = AutoConfigurationMetadataLoader.loadMetadata(this.beanClassLoader);
            AutoConfigurationImportSelector.AutoConfigurationEntry autoConfigurationEntry = this.getAutoConfigurationEntry(autoConfigurationMetadata, annotationMetadata);
            return StringUtils.toStringArray(autoConfigurationEntry.getConfigurations());
        }
    }
```

`getAutoConfigurationEntry()`方法，这个方法主要负责加载自动配置类的。

-------

**主要步骤：**

1. 判断自动装配开关是否打开。默认`spring.boot.enableautoconfiguration=true`，可在 `application.properties` 或 `application.yml` 中设置
2. 用于获取`EnableAutoConfiguration`注解中的 `exclude` 和 `excludeName`
3. 获取需要自动装配的所有配置类，读取`META-INF/spring.factories`，不光是这个依赖下的`META-INF/spring.factories`被读取到，所有 Spring Boot Starter 下的`META-INF/spring.factories`都会被读取到
4. `spring.factories`中这么多配置，每次启动都要全部加载么？不会！这一步有经历了一遍筛选，`@ConditionalOnXXX` 中的所有条件都满足，该类才会生效。

**总结：**

Spring Boot 通过`@EnableAutoConfiguration`开启自动装配，通过 SpringFactoriesLoader 最终加载`META-INF/spring.factories`中的自动配置类实现自动装配，自动配置类其实就是通过`@Conditional`按需加载的配置类，想要其生效必须引入`spring-boot-starter-xxx`包实现起步依赖

### Spring特性（用友Java）？

- `方便解耦，简化开发`，Spring提供IOC容器，将对象间的依赖关系交由Spring进行控制
- `AOP编程支持`，通过Spring的AOP功能，方便进行面向切面的编程，许多不容易用传统OOP实现的功能可以通过AOP轻松应付
- `声明式事务的支持`，可以将我们从单调烦闷的事务管理代码中解脱出来，通过声明式方式灵活的进行事务的管理，提高开发效率和质量
- `方便程序的测试`，集成Junit，方便测试
- `方便集成各种优秀框架`，可集成SpringMVC、mybatis、Struts2、hibernate等框架
- `减低JavaEE API的使用难度`，Spring 对 JavaEE API（如 JDBC、JavaMail、远程调用等）进行了薄薄的封装层，使这些 API 的使用难度大为降低

### 列举一些重要的Spring模块？

下图对应Spring4.x版本。目前最新的5.x版本中 Web 模块的 Portlet 组件已经被废弃掉，同时增加了用于异步响应式处理的 WebFlux 组件。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-6/Spring主要模块.png">

- **Spring Core：** 基础,可以说 Spring 其他所有的功能都需要依赖于该类库。主要提供 IoC 依赖注入功能。
- **Spring Aspects** ： 该模块为与AspectJ的集成提供支持。
- **Spring AOP** ：提供了面向切面的编程实现。
- **Spring JDBC** : Java数据库连接。
- **Spring JMS** ：Java消息服务。
- **Spring ORM** : 用于支持Hibernate等ORM工具。
- **Spring Web** : 为创建Web应用程序提供支持。
- **Spring Test** : 提供了对 JUnit 和 TestNG 测试的支持。

### @Repository和@Mapper区别

这两种注解的区别在于：

  1、使用@mapper后，不需要在spring配置中设置扫描地址，通过mapper.xml里面的namespace属性对应相关的mapper类，spring将动态的生成Bean后注入到ServiceImpl中。

  2、@repository则需要在Spring中配置扫描包地址，然后生成dao层的bean，之后被注入到ServiceImpl中

`即：@Mapper可以单独使用`

### @RestController和@Controller

**`Controller` 返回一个页面**

单独使用 `@Controller` 不加 `@ResponseBody`的话一般使用在要返回一个视图的情况，这种情况属于比较传统的Spring MVC 的应用，对应于前后端不分离的情况。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-7/SpringMVC传统工作流程.png">

**`@RestController` 返回JSON 或 XML 形式数据**

但`@RestController`只返回对象，对象数据直接以 JSON 或 XML 形式写入 HTTP 响应(Response)中，这种情况属于 RESTful Web服务，这也是目前日常开发所接触的最常用的情况（前后端分离）。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-7/SpringMVCRestController.png">

**`@Controller +@ResponseBody` 返回JSON 或 XML 形式数据**

如果你需要在Spring4之前开发 RESTful Web服务的话，你需要使用`@Controller` 并结合`@ResponseBody`注解，也就是说`@Controller` +`@ResponseBody`= `@RestController`（Spring 4 之后新加的注解）。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-7/Spring3.xMVCRESTfulWeb%E6%9C%8D%E5%8A%A1%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%A8%8B.png">

### @Resource和@Autowired区别？

**@Autowired注解：是按类型装配依赖对象**，默认情况下它要求依赖对象必须存在，如果允许null值，可以设置它required属性为false

**@Resource注解：**和@Autowired一样，也可以标注在字段或属性的setter方法上，但它**默认按名称装配**。名称可以通过@Resource的name属性指定，如果没有指定name属性，当注解标注在字段上，即默认取字段的名称作为bean名称寻找依赖对象，当注解标注在属性的setter方法上，即默认取属性名作为bean名称寻找依赖对象

**<font color='red'>总结：@Resource按名称，是JDK的；@Autowired按类型，是Spring的</font>**

### Spring可以解决循环依赖吗？怎么解决（用友Java）？

#### 什么是循环依赖？

- 简单的说就是A依赖B，B依赖C，C依赖A这样就构成了循环依赖
- 循环依赖分为`构造器依赖`和`属性依赖`，众所周知的是Spring能够解决属性的循环依赖（set注入）。

#### 如何解决循环依赖？

Spring主要的思路就是依据`三级缓存`，在实例化A时调用doGetBean，发现A依赖的B的实例，此时调用doGetBean去实例B，实例化的B的时候发现又依赖A，如果不解决这个循环依赖的话此时的doGetBean将会无限循环下去，导致内存溢出，程序奔溃。`spring引用了一个早期对象，并且把这个"早期引用"并将其注入到容器中，让B先完成实例化，此时A就获取B的引用，完成实例化`。

#### 三级缓存？

Spring能够轻松的解决属性的循环依赖正式用到了三级缓存，在AbstractBeanFactory中有详细的注释。

```java
//一级缓存，用于存放完全初始化好的bean，从该缓存中取出的bean可以直接使用
private final Map<String,Object> singletonObjects = new ConcurrentHashMap<>(256);
//二级缓存，存放原始的bean对象（尚未填充属性），用于解决循环依赖
private final Map<String,Object> earlySingletonObjects = new HashMap<>(16);
//三级缓存，存放bean工厂对象，用于解决循环依赖
private final Map<String,ObjectFactory<?>> singletonFactories = new HashMap<>(16);
```

- getSingleton(beanName)源码可知，doGetBean最初是查询缓存，一二三级缓存全部查询，如果三级缓存存在则将Bean早期引用存放在二级缓存中并移除三级缓存。（升级为二级缓存）
- addSingletonFactory源码可知，Bean在实例化完成之后会直接将未装配的Bean工厂存放在**三级缓存**中，并且**移除二级缓存**
- addSingleton源码可知，Bean添加到一级缓存，移除二三级缓存

#### 为什么Spring不能解决构造器的循环依赖？

在Bean调用构造器实例化之前，一二三级缓存并没有Bean的任何相关信息，在实例化之后才放入三级缓存中，因此当getBean的时候缓存并没有命中，这样就抛出了循环依赖的异常了

#### 为什么多实例Bean不能解决循环依赖？

多实例Bean是每次创建都会调用`doGetBean`方法，根本没有使用一二三级缓存，肯定不能解决循环依赖

#### 总结

根据以上的分析，大概清楚了Spring是如何解决循环依赖的。假设A依赖B，B依赖A（注意：这里是set属性依赖）分以下步骤执行：

1. A依次执行**doGetBean**、查询缓存、**createBean**创建实例，实例化完成放入三级缓存singletonFactories中，接着执行**populateBean**方法装配属性，但是发现有一个属性是B的对象。
2. 因此再次调用doGetBean方法创建B的实例，依次执行doGetBean、查询缓存、createBean创建实例，实例化完成之后放入三级缓存singletonFactories中，执行populateBean装配属性，但是此时发现有一个属性是A对象。
3. 因此再次调用doGetBean创建A的实例，但是执行到getSingleton查询缓存的时候，从三级缓存中查询到了A的实例(早期引用，未完成属性装配)，此时直接返回A，不用执行后续的流程创建A了，那么B就完成了属性装配，此时是一个完整的对象放入到一级缓存singletonObjects中。
4. B创建完成了，则A自然完成了属性装配，也创建完成放入了一级缓存singletonObjects中。

### BeanFactory和FactoryBean区别（用友Java）？

`BeanFactory是所有Spring Bean容器的根接口`，给Spring容器定义一套规范，给IOC容器提供了一套完整的规范。

**定义方法：**

- getBean(String name): Spring容器中获取对应Bean对象的方法，如存在，则返回该对象

- containsBean(String name)：Spring容器中是否存在该对象
- isSingleton(String name)：通过beanName是否为单例对象
- isPrototype(String name)：判断bean对象是否为多例对象
- isTypeMatch(String name, ResolvableType typeToMatch):判断name值获取出来的bean与typeToMath是否匹配
- getType(String name)：获取Bean的Class类型
- getAliases(String name):获取name所对应的所有的别名

**主要实现类（包括抽象类）：**

- AbstractBeanFactory：抽象Bean工厂，绝大部分的实现类，都是继承于他
- DefaultListableBeanFactory:Spring默认的工厂类
- XmlBeanFactory：前期使用XML配置用的比较多的时候用的Bean工厂
- AbstractXmlApplicationContext:抽象应用容器上下文对象
- ClassPathXmlApplicationContext:XML解析上下文对象，用户创建Bean对象我们早期写Spring的时候用的就是他

------

FactoryBean，该类是SpringIOC容器是创建Bean的一种形式，这种方式创建Bean会有加成方式，融合了简单的工厂设计模式和装饰器模式。

**常用方法：**

- T getObject()：返回实例
- Class<?> getObjectType():返回该装饰对象的Bean的类型
- default boolean isSingleton():Bean是否为单例

**常用类：**

- ProxyFactoryBean :Aop代理Bean
- GsonFactoryBean:Gson

> 有些人就要问了，我直接使用Spring默认方式创建Bean不香么，为啥还要用FactoryBean做啥，在某些情况下，对于实例Bean对象比较复杂的情况下，使用传统方式创建bean会比较复杂，例如（使用xml配置），这样就出现了FactoryBean接口，可以让用户通过实现该接口来自定义该Bean接口的实例化过程。即包装一层，将复杂的初始化过程包装，让调用者无需关系具体实现细节。

---

**区别：**

1. BeanFactory:负责生产和管理Bean的一个工厂接口，提供一个Spring Ioc容器规范,
2. FactoryBean: 一种Bean创建的一种方式，对Bean的一种扩展。对于复杂的Bean对象初始化创建使用其可封装对象的创建细节。

### Spring IOC & AOP

#### IOC

IoC（Inverse of Control:控制反转）是一种**设计思想**，就是 **将原本在程序中手动创建对象的控制权，交由Spring框架来管理。** IoC 在其他语言中也有应用，并非 Spring 特有。 **IoC 容器是 Spring 用来实现 IoC 的载体， IoC 容器实际上就是个Map（key，value）,Map 中存放的是各种对象。**

将对象之间的相互依赖关系交给 IoC 容器来管理，并由 IoC 容器完成对象的注入。这样可以很大程度上简化应用的开发，把应用从复杂的依赖关系中解放出来。 **IoC 容器就像是一个工厂一样，当我们需要创建一个对象的时候，只需要配置好配置文件/注解即可，完全不用考虑对象是如何被创建出来的。** 在实际项目中一个 Service 类可能有几百甚至上千个类作为它的底层，假如我们需要实例化这个 Service，你可能要每次都要搞清这个 Service 所有底层类的构造函数，这可能会把人逼疯。如果利用 IoC 的话，你只需要配置好，然后在需要的地方引用就行了，这大大增加了项目的可维护性且降低了开发难度。

Spring 时代我们一般通过 XML 文件来配置 Bean，后来开发人员觉得 XML 文件来配置不太好，于是 SpringBoot 注解配置就慢慢开始流行起来。

Spring IOC初始化过程：

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-7/SpringIOC%E5%88%9D%E5%A7%8B%E5%8C%96%E8%BF%87%E7%A8%8B.png">

#### AOP

AOP(Aspect-Oriented Programming:面向切面编程)能够将那些与业务无关，**却为业务模块所共同调用的逻辑或责任（例如事务处理、日志管理、权限控制等）封装起来**，便于**减少系统的重复代码**，**降低模块间的耦合度**，并**有利于未来的可拓展性和可维护性**。

**Spring AOP就是基于动态代理的**，如果要代理的对象，实现了某个接口，那么Spring AOP会使用**JDK Proxy**，去创建代理对象，而对于没有实现接口的对象，就无法使用 JDK Proxy 去进行代理了，这时候Spring AOP会使用**Cglib** ，这时候Spring AOP会使用 **Cglib** 生成一个被代理对象的子类来作为代理，如下图所示：

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/2019-6/SpringAOPProcess.jpg">

当然你也可以使用 AspectJ ,Spring AOP 已经集成了AspectJ ，AspectJ 应该算的上是 Java 生态系统中最完整的 AOP 框架了。

使用 AOP 之后我们可以把一些通用功能抽象出来，在需要用到的地方直接使用即可，这样大大简化了代码量。我们需要增加新功能时也方便，这样也提高了系统扩展性。日志功能、事务管理等等场景都用到了 AOP 。

> JDK动态代理和CGLIB字节码生成的区别？
> （1）JDK动态代理只能对`实现了接口的类`生成代理，而不能针对类。
> （2）CGLIB是针对`类`实现代理，主要是对指定的类生成一个子类，覆盖其中的方法，因为是继承，所以该类或者方法最好不要生命成final。

### Spring AOP和AspectJ AOP有什么区别？

**Spring AOP 属于运行时增强，而 AspectJ 是编译时增强。** Spring AOP 基于代理(Proxying)，而 AspectJ 基于字节码操作(Bytecode Manipulation)。

Spring AOP 已经集成了 AspectJ ，AspectJ 应该算的上是 Java 生态系统中最完整的 AOP 框架了。AspectJ 相比于 Spring AOP 功能更加强大，但是 Spring AOP 相对来说更简单，

如果我们的切面比较少，那么两者性能差异不大。但是，当切面太多的话，最好选择 AspectJ ，它比Spring AOP 快很多。

### Spring IOC容器管理的bean是单例的吗？如何变为多例？（用友Java）

**SpringIOC容器管理的bean默认都是单例的**

Spring容器在默认情况下管理的bean是单例（singleton）的，即该bean只会创造一个对象，无论之后调用多少次该bean，都只会返回同一个对象

多例（prototype）模式，每次调用同一个bean，都会创造不同的对象

通过修改`scope`可以实现单例或者多例

```xml
 <bean id="apple" class="com.tsvv.pojo.Apple" scope="singleton"></bean>
 <bean id="orange" class="com.tsvv.pojo.Orange" scope="prototype"></bean>
```

### Spring中的bean的作用域有哪些？（用友Java）

- `singleton` : 唯一 bean 实例，Spring 中的 bean 默认都是单例的。
- `prototype `: 每次请求都会创建一个新的 bean 实例。
- `request `: 每一次HTTP请求都会产生一个新的bean，该bean仅在当前HTTP request内有效。
- `session `: 每一次HTTP请求都会产生一个新的 bean，该bean仅在当前 HTTP session 内有效。
- `global-session`： 全局session作用域，仅仅在基于portlet的web应用中才有意义，Spring5已经没有了。Portlet是能够生成语义代码(例如：HTML)片段的小型Java Web插件。它们基于portlet容器，可以像servlet一样处理HTTP请求。但是，与 servlet 不同，每个 portlet 都有不同的会话

### Spring中的单例bean的线程安全问题了解吗？

`的确是存在安全问题的。`因为，当多个线程操作同一个对象的时候，对这个对象的成员变量的写操作会存在线程安全问题。

但是，一般情况下，我们常用的 `Controller`、`Service`、`Dao` 这些 Bean 是无状态的。无状态的 Bean 不能保存数据，因此是线程安全的。

常见的有 2 种解决办法：

1. 在类中定义一个 `ThreadLocal` 成员变量，将需要的可变成员变量保存在 `ThreadLocal` 中（推荐的一种方式）。
2. 改变 Bean 的作用域为 “prototype”：每次请求都会创建一个新的 bean 实例，自然不会存在线程安全问题。

### @Component和@Bean的区别是什么？

1. 作用对象不同: `@Component` 注解作用于类，而`@Bean`注解作用于方法。
2. `@Component`通常是通过类路径扫描来自动侦测以及自动装配到Spring容器中（我们可以使用 `@ComponentScan` 注解定义要扫描的路径从中找出标识了需要装配的类自动装配到 Spring 的 bean 容器中）。`@Bean` 注解通常是我们在标有该注解的方法中定义产生这个 bean,`@Bean`告诉了Spring这是某个类的示例，当我需要用它的时候还给我。
3. `@Bean` 注解比 `Component` 注解的自定义性更强，而且很多地方我们只能通过 `@Bean` 注解来注册bean。比如当我们引用第三方库中的类需要装配到 `Spring`容器时，则只能通过 `@Bean`来实现。

```java
//@Bean注解示例
@Configuration
public class AppConfig {
    @Bean
    public TransferService transferService() {
        return new TransferServiceImpl();
    }
}
//相当于
<beans>
    <bean id="transferService" class="com.acme.TransferServiceImpl"/>
</beans>
```

### 将一个类声明为Spring的bean注解有哪些？

我们一般使用 `@Autowired` 注解自动装配 bean，要想把类标识成可用于 `@Autowired` 注解自动装配的 bean 的类,采用以下注解可实现：

- `@Component` ：通用的注解，可标注任意类为 `Spring` 组件。如果一个Bean不知道属于哪个层，可以使用`@Component` 注解标注。
- `@Repository` : 对应持久层即 Dao 层，主要用于数据库相关操作。
- `@Service` : 对应服务层，主要涉及一些复杂的逻辑，需要用到 Dao层。
- `@Controller` : 对应 Spring MVC 控制层，主要用于接受用户请求并调用 Service 层返回数据给前端页面。

### Spring中的bean的生命周期（用友Java）？

- Bean 容器找到配置文件中 Spring Bean 的定义。
- Bean 容器利用 Java Reflection API 创建一个Bean的实例。
- 如果涉及到一些属性值 利用 `set()`方法设置一些属性值。
- 如果 Bean 实现了 `BeanNameAware` 接口，调用 `setBeanName()`方法，传入Bean的名字。
- 如果 Bean 实现了 `BeanClassLoaderAware` 接口，调用 `setBeanClassLoader()`方法，传入 `ClassLoader`对象的实例。
- 与上面的类似，如果实现了其他 `*.Aware`接口，就调用相应的方法。
- 如果有和加载这个 Bean 的 Spring 容器相关的 `BeanPostProcessor` 对象，执行`postProcessBeforeInitialization()` 方法
- 如果Bean实现了`InitializingBean`接口，执行`afterPropertiesSet()`方法。
- 如果 Bean 在配置文件中的定义包含 init-method 属性，执行指定的方法。
- 如果有和加载这个 Bean的 Spring 容器相关的 `BeanPostProcessor` 对象，执行`postProcessAfterInitialization()` 方法
- 当要销毁 Bean 的时候，如果 Bean 实现了 `DisposableBean` 接口，执行 `destroy()` 方法。
- 当要销毁 Bean 的时候，如果 Bean 在配置文件中的定义包含 destroy-method 属性，执行指定的方法。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/18-9-17/5496407.jpg">

### SpringMVC知道哪些？说一下

MVC 是一种设计模式,Spring MVC 是一款很优秀的 MVC 框架。Spring MVC 可以帮助我们进行更简洁的Web层的开发，并且它天生与 Spring 框架集成。Spring MVC 下我们一般把后端项目分为 Service层（处理业务）、Dao层（数据库操作）、Entity层（实体类）、Controller层(控制层，返回数据给前台页面)。

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/18-10-11/60679444.jpg">

### SpringMVC工作原理了解吗？

<img src="https://my-blog-to-use.oss-cn-beijing.aliyuncs.com/18-10-11/49790288.jpg">

> **上图有误！**Spring MVC 的入口函数也就是前端控制器 `DispatcherServlet` 的作用是接收请求，响应结果。

流程说明：

1. 客户端（浏览器）发送请求，直接请求到 `DispatcherServlet`
2. `DispatcherServlet` 根据请求信息调用 `HandlerMapping`，解析请求对应的 `Handler`
3. 解析到对应的 `Handler`（也就是我们平常说的 `Controller` 控制器）后，开始由 `HandlerAdapter` 适配器处理
4. `HandlerAdapter` 会根据 `Handler `来调用真正的处理器来处理请求，并处理相应的业务逻辑
5. 处理器处理完业务后，会返回一个 `ModelAndView` 对象，`Model` 是返回的数据对象，`View` 是个逻辑上的 `View`
6. `ViewResolver` 会根据逻辑 `View` 查找实际的 `View`
7. `DispaterServlet` 把返回的 `Model` 传给 `View`（视图渲染）
8. 把 `View` 返回给请求者（浏览器）

### Spring框架中用到了哪些设计模式？

- **工厂设计模式🐕** : Spring使用工厂模式通过 `BeanFactory`、`ApplicationContext` 创建 bean 对象。
- **代理设计模式🐕** : Spring AOP 功能的实现。
- **单例设计模式🐕** : Spring 中的 Bean 默认都是单例的。
- **模板方法模式🐕** : Spring 中 `jdbcTemplate`、`hibernateTemplate` 等以 Template 结尾的对数据库操作的类，它们就使用到了模板模式。
- **包装器设计模式** : 我们的项目需要连接多个数据库，而且不同的客户在每次访问中根据需要会去访问不同的数据库。这种模式让我们可以根据客户的需求能够动态切换不同的数据源。
- **观察者模式:** Spring 事件驱动模型就是观察者模式很经典的一个应用。
- **适配器模式🐕** :Spring AOP 的增强或通知(Advice)使用到了适配器模式、spring MVC 中也是用到了适配器模式适配`Controller`。
- **装饰者模式🐕**

### Spring管理事务的方式有哪几种？（用友Java）

1. 编程式事务，在代码中硬编码。(不推荐使用)
2. 声明式事务，在配置文件中配置（推荐使用，分两类）
   - 基于XML的声明式事务
   - 基于注解的声明式事务

```java
//事务管理：声明
@Transactional(isolation = Isolation.READ_COMMITTED,propagation = Propagation.REQUIRED)
public int addComment(Comment comment){
    if (comment == null){
        throw new IllegalArgumentException("参数不能为空！");
    }
    //添加评论
    comment.setContent(HtmlUtils.htmlEscape(comment.getContent()));
    comment.setContent(sensitiveFilter.filter(comment.getContent()));
    int rows = commentMapper.insertComment(comment);
    //更新帖子评论数量
    if (comment.getEntityType() == ENTITY_TYPE_POST){
        int count = commentMapper.selectCountByEntity(comment.getEntityType(), comment.getEntityId());
        discussPostService.updateCommentCount(comment.getEntityId(),count);
    }
    return rows;
}
```

### Spring事务管理接口介绍？

- **`PlatformTransactionManager`**： （平台）事务管理器，Spring 事务策略的核心
- **`TransactionDefinition`**： 事务定义信息(事务隔离级别、传播行为、超时、只读、回滚规则)
- **`TransactionStatus`**： 事务运行状态

**`PlatformTransactionManager`** 会根据 **`TransactionDefinition`** 的定义比如事务超时时间、隔离级别、传播行为等来进行事务管理 ，而 **`TransactionStatus`** 接口则提供了一些方法来获取事务相应的状态比如是否新事务、是否可以回滚等等。通过这个接口，Spring 为各个平台如 JDBC(`DataSourceTransactionManager`)、Hibernate(`HibernateTransactionManager`)、JPA(`JpaTransactionManager`)等都提供了对应的事务管理器，但是具体的实现就是各个平台自己的事情了

```java
package org.springframework.transaction;
import org.springframework.lang.Nullable;
public interface PlatformTransactionManager {
    //获得事务
    TransactionStatus getTransaction(@Nullable TransactionDefinition var1) throws TransactionException;
    //提交事务
    void commit(TransactionStatus var1) throws TransactionException;
    //回滚事务
    void rollback(TransactionStatus var1) throws TransactionException;
}
```

----------

事务管理器接口 **`PlatformTransactionManager`** 通过 **`getTransaction(TransactionDefinition definition)`** 方法来得到一个事务，这个方法里面的参数是 **`TransactionDefinition`** 类 ，这个类就定义了一些基本的事务属性。

事务属性可以理解成事务的一些基本配置，描述了事务策略如何应用到方法上，包含五个方面：`隔离级别、传播行为、回滚规则、是否只读、事务超时`

```java
package org.springframework.transaction;
import org.springframework.lang.Nullable;
public interface TransactionDefinition {
    int PROPAGATION_REQUIRED = 0;
    int PROPAGATION_SUPPORTS = 1;
    int PROPAGATION_MANDATORY = 2;
    int PROPAGATION_REQUIRES_NEW = 3;
    int PROPAGATION_NOT_SUPPORTED = 4;
    int PROPAGATION_NEVER = 5;
    int PROPAGATION_NESTED = 6;
    int ISOLATION_DEFAULT = -1;
    int ISOLATION_READ_UNCOMMITTED = 1;
    int ISOLATION_READ_COMMITTED = 2;
    int ISOLATION_REPEATABLE_READ = 4;
    int ISOLATION_SERIALIZABLE = 8;
    int TIMEOUT_DEFAULT = -1;
    // 返回事务的传播行为，默认值为 REQUIRED。
    int getPropagationBehavior();
    //返回事务的隔离级别，默认值是 DEFAULT
    int getIsolationLevel();
    // 返回事务的超时时间，默认值为-1。如果超过该时间限制但事务还没有完成，则自动回滚事务。
    int getTimeout();
    // 返回是否为只读事务，默认值为 false
    boolean isReadOnly();
    @Nullable
    String getName();
}
```

---------

`TransactionStatus`接口用来记录事务的状态 该接口定义了一组方法,用来获取或判断事务的相应状态信息。`PlatformTransactionManager.getTransaction(…)`方法返回一个 `TransactionStatus` 对象。

```java
public interface TransactionStatus{
    boolean isNewTransaction(); // 是否是新的事务
    boolean hasSavepoint(); // 是否有恢复点
    void setRollbackOnly();  // 设置为只回滚
    boolean isRollbackOnly(); // 是否为只回滚
    boolean isCompleted; // 是否已完成
}
```

### Spring事务中的隔离级别有哪几种？

**TransactionDefinition 接口中定义了五个表示隔离级别的常量：**

- **TransactionDefinition.ISOLATION_DEFAULT:** 使用后端数据库默认的隔离级别，Mysql 默认采用的 REPEATABLE_READ隔离级别 Oracle 默认采用的 READ_COMMITTED隔离级别.
- **TransactionDefinition.ISOLATION_READ_UNCOMMITTED:** 最低的隔离级别，允许读取尚未提交的数据变更，**可能会导致脏读、幻读或不可重复读**
- **TransactionDefinition.ISOLATION_READ_COMMITTED:** 允许读取并发事务已经提交的数据，**可以阻止脏读，但是幻读或不可重复读仍有可能发生**
- **TransactionDefinition.ISOLATION_REPEATABLE_READ:** 对同一字段的多次读取结果都是一致的，除非数据是被本身事务自己所修改，**可以阻止脏读和不可重复读，但幻读仍有可能发生。**
- **TransactionDefinition.ISOLATION_SERIALIZABLE:** 最高的隔离级别，完全服从ACID的隔离级别。所有的事务依次逐个执行，这样事务之间就完全不可能产生干扰，也就是说，**该级别可以防止脏读、不可重复读以及幻读**。但是这将严重影响程序的性能。通常情况下也不会用到该级别。

> **MySQL InnoDB的REPEATABLE-READ（可重读）并不保证避免幻读，需要应用使用加锁读来保证。而这个加锁度使用到的机制就是 Next-Key Locks。**InnoDB 存储引擎在 **分布式事务** 的情况下一般会用到 **SERIALIZABLE(可串行化)** 隔离级别。

### Spring事务中哪几种事务传播行为？

> 事务传播行为是为了解决业务层方法之间互相调用的事务问题。当事务方法被另一个事务方法调用时，必须指定事务应该如何传播

**支持当前事务的情况：**

- **TransactionDefinition.PROPAGATION_REQUIRED：** 如果当前存在事务，则加入该事务；如果当前没有事务，则创建一个新的事务。
- **TransactionDefinition.PROPAGATION_SUPPORTS：** 如果当前存在事务，则加入该事务；如果当前没有事务，则以非事务的方式继续运行。
- **TransactionDefinition.PROPAGATION_MANDATORY：** 如果当前存在事务，则加入该事务；如果当前没有事务，则抛出异常。（mandatory：强制性）

**不支持当前事务的情况：**

- **TransactionDefinition.PROPAGATION_REQUIRES_NEW：** 创建一个新的事务，如果当前存在事务，则把当前事务挂起。
- **TransactionDefinition.PROPAGATION_NOT_SUPPORTED：** 以非事务方式运行，如果当前存在事务，则把当前事务挂起。
- **TransactionDefinition.PROPAGATION_NEVER：** 以非事务方式运行，如果当前存在事务，则抛出异常。

**其他情况：**

- **TransactionDefinition.PROPAGATION_NESTED：** 如果当前存在事务，则创建一个事务作为当前事务的嵌套事务来运行；如果当前没有事务，则该取值等价于TransactionDefinition.PROPAGATION_REQUIRED。

### @Transactional(rollbackFor=Exception.class)注解了解吗？

Exception分为运行时异常RuntimeException和非运行时异常。

当`@Transactional`注解作用于类上时，该类的所有 public 方法将都具有该类型的事务属性，同时，我们也可以在方法级别使用该标注来覆盖类级别的定义。如果类或者方法加了这个注解，那么这个类里面的方法抛出异常，就会回滚，数据库里面的数据也会回滚。

在`@Transactional`注解中如果不配置`rollbackFor`属性,那么事务只会在遇到`RuntimeException`的时候才会回滚,加上`rollbackFor=Exception.class`,可以让事务在遇到非运行时异常时也回滚。

### @Transactional常见配置

|   属性名    |                             说明                             |
| :---------: | :----------------------------------------------------------: |
| propagation |   事务的传播行为，默认值为 REQUIRED，可选的值在上面介绍过    |
|  isolation  |   事务的隔离级别，默认值采用 DEFAULT，可选的值在上面介绍过   |
|   timeout   | 事务的超时时间，默认值为-1（不会超时）。如果超过该时间限制但事务还没有完成，则自动回滚事务 |
|  readOnly   |            指定事务是否为只读事务，默认值为 false            |
| rollbackFor | 用于指定能够触发事务回滚的异常类型，并且可以指定多个异常类型 |

### @Transactional自调用问题

若同一类中的其他没有 `@Transactional` 注解的方法内部调用有 `@Transactional` 注解的方法，有`@Transactional` 注解的方法的事务会失效。

这是由于`Spring AOP`代理的原因造成的，因为只有当 `@Transactional` 注解的方法在类以外被调用的时候，Spring 事务管理才生效。

`MyService` 类中的`method1()`调用`method2()`就会导致`method2()`的事务失效。

```java
@Service
public class MyService {
private void method1() {
     method2();
     //......
}
@Transactional
 public void method2() {
     //......
  }
}
```

## Kafka

### Kafka为什么吞吐量大、速度快？

1. **顺序读写**

基于磁盘的**随机读写确实很慢，但磁盘的顺序读写性能却很高**，一般而言要高出磁盘随机读写三个数量级，**一些情况下磁盘顺序读写性能甚至要高于内存随机读写**。

 磁盘的顺序读写是磁盘使用模式中最有规律的，并且操作系统也对这种模式做了大量优化，Kafka就是使用了磁盘顺序读写来提升的性能。**Kafka的message是不断追加到本地磁盘文件末尾的，而不是随机的写入**，这使得Kafka写入吞吐量得到了显著提升 。

2. **Page Cache**

- I/O Scheduler 会将连续的小块写组装成大块的物理写从而提高性能
- I/O Scheduler 会尝试将一些写操作重新按顺序排好，从而减少磁盘头的移动时间
- 充分利用所有空闲内存（非 JVM 内存）。如果使用应用层 Cache（即 JVM 堆内存），会增加 GC 负担
- 读操作可直接在 Page Cache 内进行。如果消费和生产速度相当，甚至不需要通过物理磁盘（直接通过 Page Cache）交换数据
- 如果进程重启，JVM 内的 Cache 会失效，但 Page Cache 仍然可用

3. **零拷贝**

linux操作系统 “零拷贝” 机制使用了sendfile方法， 允许操作系统将数据从Page Cache 直接发送到网络，只需要最后一步的copy操作将数据复制到 NIC 缓冲区， 这样避免重新复制数据 。

<img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9zMi5heDF4LmNvbS8yMDE5LzA3LzA4L1pyNTF6Vi5wbmc">

`通过这种 “零拷贝” 的机制，Page Cache 结合 sendfile 方法，Kafka消费端的性能也大幅提升。这也是为什么有时候消费端在不断消费数据时，我们并没有看到磁盘io比较高，此刻正是操作系统缓存在提供数据。`

当Kafka客户端从服务器读取数据时，如果不使用零拷贝技术，那么大致需要经历这样的一个过程：

- 操作系统将数据从磁盘上读入到内核空间的读缓冲区中。
- 应用程序（也就是Kafka）从内核空间的读缓冲区将数据拷贝到用户空间的缓冲区中。
- 应用程序将数据从用户空间的缓冲区再写回到内核空间的socket缓冲区中。
- 操作系统将socket缓冲区中的数据拷贝到NIC缓冲区中，然后通过网络发送给客户端。

4. **批量读写**

Kafka数据读写也是批量的而不是单条的。

除了利用底层的技术外，Kafka还在应用程序层面提供了一些手段来提升性能。最明显的就是使用批次。在向Kafka写入数据时，可以启用批次写入，这样可以避免在网络上频繁传输单个消息带来的延迟和带宽开销。假设网络带宽为10MB/S，一次性传输10MB的消息比传输1KB的消息10000万次显然要快得多。

5. **利用 Partition 实现并行处理**

由于不同 Partition 可位于不同机器，因此可以充分利用集群优势，实现机器间的并行处理。另一方面，由于 Partition 在物理上对应一个文件夹，即使多个 Partition 位于同一个节点，也可通过配置让同一节点上的不同 Partition 置于不同的磁盘上，从而实现磁盘间的并行处理，充分发挥多磁盘的优势。

### 为什么使用消息队列？

主要特点是：**解耦、异步、削峰**

缺点：系统可用性降低、系统负载度高、一致性问题

|         特性          |               ActiveMQ                |                      RabbitMQ                      |                           RocketMQ                           |                            Kafka                             |
| :-------------------: | :-----------------------------------: | :------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|      单机吞吐量       | 万级，比 RocketMQ、Kafka 低一个数量级 |                    同 ActiveMQ                     |                     10 万级，支撑高吞吐                      | 10 万级，高吞吐，一般配合大数据类的系统来进行实时数据计算、日志采集等场景 |
| topic数量对吞吐量影响 |                                       |                                                    | topic 可以达到几百/几千的级别，吞吐量会有较小幅度的下降，这是 RocketMQ 的一大优势，在同等机器下，可以支撑大量的 topic | topic 从几十到几百个时候，吞吐量会大幅度下降，在同等机器下，Kafka 尽量保证 topic 数量不要过多，如果要支撑大规模的 topic，需要增加更多的机器资源 |
|        时效性         |                 ms 级                 |     微秒级，这是 RabbitMQ 的一大特点，延迟最低     |                            ms 级                             |                       延迟在 ms 级以内                       |
|        可用性         |      高，基于主从架构实现高可用       |                    同 ActiveMQ                     |                      非常高，分布式架构                      | 非常高，分布式，一个数据多个副本，少数机器宕机，不会丢失数据，不会导致不可用 |
|      消息可靠性       |         有较低的概率丢失数据          |                      基本不丢                      |              经过参数优化配置，可以做到 0 丢失               |                         同 RocketMQ                          |
|       功能支持        |         MQ 领域的功能极其完备         | 基于 erlang 开发，并发能力很强，性能极好，延时很低 |           MQ 功能较为完善，还是分布式的，扩展性好            | 功能较为简单，主要支持简单的 MQ 功能，在大数据领域的实时计算以及日志采集被大规模使用 |

#### 介绍下Kafka？

Kafka 一个最基本的架构认识：由多个 broker 组成，每个 broker 是一个节点；你创建一个 topic，这个 topic 可以划分为多个 partition，每个 partition 可以存在于不同的 broker 上，每个 partition 就放一部分数据。

这就是**天然的分布式消息队列**，就是说一个 topic 的数据，是**分散放在多个机器上的，每个机器就放一部分数据**。

Kafka 0.8 以前，是没有 HA 机制的，就是任何一个 broker 宕机了，那个 broker 上的 partition 就废了，没法写也没法读，没有什么高可用性可言。

Kafka 0.8 以后，提供了 HA 机制，就是 replica（复制品） 副本机制。每个 partition 的数据都会同步到其它机器上，形成自己的多个 replica 副本。所有 replica 会选举一个 leader 出来，那么生产和消费都跟这个 leader 打交道，然后其他 replica 就是 follower。写的时候，leader 会负责把数据同步到所有 follower 上去，读的时候就直接读 leader 上的数据即可。只能读写 leader？很简单，**要是你可以随意读写每个 follower，那么就要 care 数据一致性的问题**，系统复杂度太高，很容易出问题。Kafka 会均匀地将一个 partition 的所有 replica 分布在不同的机器上，这样才可以提高容错性。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/kafka-after.png">

这么搞，就有所谓的**高可用性**了，因为如果某个 broker 宕机了，没事儿，那个 broker 上面的 partition 在其他机器上都有副本的。如果这个宕机的 broker 上面有某个 partition 的 leader，那么此时会从 follower 中**重新选举**一个新的 leader 出来，大家继续读写那个新的 leader 即可。这就有所谓的高可用性了。

**写数据**的时候，生产者就写 leader，然后 leader 将数据落地写本地磁盘，接着其他 follower 自己主动从 leader 来 pull 数据。一旦所有 follower 同步好数据了，就会发送 ack 给 leader，leader 收到所有 follower 的 ack 之后，就会返回写成功的消息给生产者。（当然，这只是其中一种模式，还可以适当调整这个行为）

**消费**的时候，只会从 leader 去读，但是只有当一个消息已经被所有 follower 都同步成功返回 ack 的时候，这个消息才会被消费者读到。

#### 如何保证消息不被重复消费？如何保持消息消费的幂等性？

Kafka 实际上有个 offset 的概念，就是每个消息写进去，都有一个 offset，代表消息的序号，然后 consumer 消费了数据之后，**每隔一段时间**（定时定期），会把自己消费过的消息的 offset 提交一下，表示“我已经消费过了，下次我要是重启啥的，你就让我继续从上次消费到的 offset 来继续消费吧”。

但是凡事总有意外，比如我们之前生产经常遇到的，就是你有时候重启系统，看你怎么重启了，如果碰到点着急的，直接 kill 进程了，再重启。这会导致 consumer 有些消息处理了，但是没来得及提交 offset，尴尬了。重启之后，少数消息会再次消费一次。

举个例子吧。假设你有个系统，消费一条消息就往数据库里插入一条数据，要是你一个消息重复两次，你不就插入了两条，这数据不就错了？但是你要是消费到第二次的时候，自己判断一下是否已经消费过了，若是就直接扔了，这样不就保留了一条数据，从而保证了数据的正确性。

**一条数据重复出现两次，数据库里就只有一条数据，这就保证了系统的幂等性。**

<font color='blue'>幂等性，通俗点说，就一个数据，或者一个请求，给你重复来多次，你得确保对应的数据是不会改变的，不能出错。</font>

几个保证幂等性的思路：

- 比如你拿个数据要写库，你先根据主键查一下，如果这数据都有了，你就别插入了，update 一下好吧。
- 比如你是写 Redis，那没问题了，反正每次都是 set，天然幂等性。
- 比如你不是上面两个场景，那做的稍微复杂一点，你需要让生产者发送每条数据的时候，里面加一个全局唯一的 id，类似订单 id 之类的东西，然后你这里消费到了之后，先根据这个 id 去比如 Redis 里查一下，之前消费过吗？如果没有消费过，你就处理，然后这个 id 写 Redis。如果消费过了，那你就别处理了，保证别重复处理相同的消息即可。
- 比如基于数据库的唯一键来保证重复数据不会重复插入多条。因为有唯一键约束了，重复数据插入只会报错，不会导致数据库中出现脏数据。

#### 如何保证消息的可靠传输？

- 消费端丢失数据
  - 唯一可能导致消费者弄丢数据的情况，就是说，你消费到了这个消息，然后消费者那边**自动提交了 offset**，让 Kafka 以为你已经消费好了这个消息，但其实你才刚准备处理这个消息，你还没处理，你自己就挂了，此时这条消息就丢咯。
  - Kafka 会自动提交 offset，那么只要**关闭自动提交** offset，在处理完之后自己手动提交 offset，就可以保证数据不会丢。但是此时确实还是**可能会有重复消费**，比如你刚处理完，还没提交 offset，结果自己挂了，此时肯定会重复消费一次，自己保证幂等性就好了。
  - 生产环境碰到的一个问题，就是说我们的 Kafka 消费者消费到了数据之后是写到一个内存的 queue 里先缓冲一下，结果有的时候，你刚把消息写入内存 queue，然后消费者会自动提交 offset。然后此时我们重启了系统，就会导致内存 queue 里还没来得及处理的数据就丢失了。
- kafka丢失数据
  - Kafka 某个 broker 宕机，然后重新选举 partition 的 leader。大家想想，要是此时其他的 follower 刚好还有些数据没有同步，结果此时 leader 挂了，然后选举某个 follower 成 leader 之后，不就少了一些数据？这就丢了一些数据啊。
  - 给 topic 设置 `replication.factor` 参数：这个值必须大于 1，要求每个 partition 必须有至少 2 个副本。
  - 在 Kafka 服务端设置 `min.insync.replicas` 参数：这个值必须大于 1，这个是要求一个 leader 至少感知到有至少一个 follower 还跟自己保持联系，没掉队，这样才能确保 leader 挂了还有一个 follower 吧。
  - 在 producer 端设置 `acks=all` ：这个是要求每条数据，必须是**写入所有 replica 之后，才能认为是写成功了**。
  - 在 producer 端设置 `retries=MAX` （很大很大很大的一个值，无限次重试的意思）：这个是**要求一旦写入失败，就无限重试**，卡在这里了。
- 生产端丢失数据
  - 如果设置了 `acks=all` ，一定不会丢，要求是，你的 leader 接收到消息，所有的 follower 都同步到了消息之后，才认为本次写成功了。如果没满足这个条件，生产者会自动不断的重试，重试无限次。

#### 如何保证消息的顺序性？

**Kafka**：比如说我们建了一个 topic，有三个 partition。生产者在写的时候，其实可以指定一个 key，比如说我们指定了某个订单 id 作为 key，那么这个订单相关的数据，一定会被分发到同一个 partition 中去，而且这个 partition 中的数据一定是有顺序的。
消费者从 partition 中取出来数据的时候，也一定是有顺序的。到这里，顺序还是 ok 的，没有错乱。接着，我们在消费者里可能会搞**多个线程来并发处理消息**。因为如果消费者是单线程消费处理，而处理比较耗时的话，比如处理一条消息耗时几十 ms，那么 1 秒钟只能处理几十条消息，这吞吐量太低了。而多个线程并发跑的话，顺序可能就乱掉了。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/kafka-order-01.png">

解决方案：

- 一个 topic，一个 partition，一个 consumer，内部单线程消费，单线程吞吐量太低，一般不会用这个。
- 写 N 个内存 queue，具有相同 key 的数据都到同一个内存 queue；然后对于 N 个线程，每个线程分别消费一个内存 queue 即可，这样就能保证顺序性。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/kafka-order-02.png">

## ElasticSearch

### 什么是ElasticSearch？

Lucene 是最先进、功能最强大的搜索库。ElasticSearch 基于 Lucene，隐藏了 lucene 的复杂性，提供了简单易用的 RESTful api / Java api 接口（另外还有其他语言的 api 接口）。

- 分布式的文档存储引擎
- 分布式的搜索引擎和分析引擎
- 分布式，支持 PB 级数据

### ElasticSearch核心概念

#### Near Realtime

- 从写入数据到数据可以被搜索到有一个小延迟（大概是 1s）
- 基于 ES 执行搜索和分析可以达到秒级

#### Cluster集群

集群包含多个节点，每个节点属于哪个集群都是通过一个配置来决定的，对于中小型应用来说，刚开始一个集群就一个节点很正常。

#### Node节点

Node 是集群中的一个节点，节点也有一个名称，默认是随机分配的。默认节点会去加入一个名称为 `elasticsearch` 的集群。如果直接启动一堆节点，那么它们会自动组成一个 elasticsearch 集群，当然一个节点也可以组成 elasticsearch 集群。

#### Document&field

<font color='red'>文档是 ES 中最小的数据单元，一个 document 可以是一条客户数据、一条商品分类数据、一条订单数据，通常用 json 数据结构来表示。每个 index 下的 type，都可以存储多条 document。一个 document 里面有多个 field，每个 field 就是一个数据字段。</font>

```json
{
  "product_id": "1",
  "product_name": "iPhone X",
  "product_desc": "苹果手机",
  "category_id": "2",
  "category_name": "电子产品"
}
```

#### Index

索引包含了一堆有相似结构的文档数据，比如商品索引。一个索引包含很多 document，一个索引就代表了一类相似或者相同的 ducument。

#### Type

类型，每个索引里可以有一个或者多个 type，type 是 index 的一个逻辑分类，比如商品 index 下有多个 type：日化商品 type、电器商品 type、生鲜商品 type。每个 type 下的 document 的 field 可能不太一样。

#### shard

单台机器无法存储大量数据，ES 可以将一个索引中的数据切分为多个 shard，分布在多台服务器上存储。有了 shard 就可以横向扩展，存储更多数据，让搜索和分析等操作分布到多台服务器上去执行，提升吞吐量和性能。每个 shard 都是一个 lucene index。

#### replica

任何一个服务器随时可能故障或宕机，此时 shard 可能就会丢失，因此可以为每个 shard 创建多个 replica 副本。replica 可以在 shard 故障时提供备用服务，保证数据不丢失，多个 replica 还可以提升搜索操作的吞吐量和性能。primary shard（建立索引时一次设置，不能修改，默认 5 个），replica shard（随时修改数量，默认 1 个），默认每个索引 10 个 shard，5 个 primary shard，5 个 replica shard，最小的高可用配置，是 2 台服务器。

shard 分为 primary shard 和 replica shard。而 primary shard 一般简称为 shard，而 replica shard 一般简称为 replica。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/es-cluster-0.png">

#### ES核心概念 vs DB核心概念

|    ES    |      DB      |
| :------: | :----------: |
|  index   |    数据库    |
|   type   | 数据库中的表 |
| document | 表中一行数据 |

### ES 的分布式架构原理能说一下么（ES 是如何实现分布式的啊）？

ElasticSearch 设计的理念就是分布式搜索引擎，底层其实还是基于 lucene 的。核心思想就是在多台机器上启动多个 ES 进程实例，组成了一个 ES 集群。ES 中存储数据的**基本单位是索引**，比如说你现在要在 ES 中存储一些订单数据，你就应该在 ES 中创建一个索引 `order_idx` ，所有的订单数据就都写到这个索引里面去，一个索引差不多就是相当于是 mysql 里的一张表。

```markdown
index -> type -> mapping -> document -> field。
```

你搞一个索引，这个索引可以拆分成多个 `shard` ，每个 shard 存储部分数据。拆分多个 shard 是有好处的，一是**支持横向扩展**，比如你数据量是 3T，3 个 shard，每个 shard 就 1T 的数据，若现在数据量增加到 4T，怎么扩展，很简单，重新建一个有 4 个 shard 的索引，将数据导进去；二是**提高性能**，数据分布在多个 shard，即多台服务器上，所有的操作，都会在多台机器上并行分布式执行，提高了吞吐量和性能。接着就是这个 shard 的数据实际是有多个备份，就是说每个 shard 都有一个 `primary shard` ，负责写入数据，但是还有几个 `replica shard` 。 `primary shard` 写入数据之后，会将数据同步到其他几个 `replica shard` 上去。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/es-cluster.png">

ES 集群多个节点，会自动选举一个节点为 master 节点，这个 master 节点其实就是干一些管理的工作的，比如维护索引元数据、负责切换 primary shard 和 replica shard 身份等。要是 master 节点宕机了，那么会重新选举一个节点为 master 节点。

如果是非 master 节点宕机了，那么会由 master 节点，让那个宕机节点上的 primary shard 的身份转移到其他机器上的 replica shard。接着你要是修复了那个宕机机器，重启了之后，master 节点会控制将缺失的 replica shard 分配过去，同步后续修改的数据之类的，让集群恢复正常。

说得更简单一点，就是说如果某个非 master 节点宕机了。那么此节点上的 primary shard 不就没了。那好，master 会让 primary shard 对应的 replica shard（在其他机器上）切换为 primary shard。如果宕机的机器修复了，修复后的节点也不再是 primary shard，而是 replica shard。

### ES 写入数据和查询数据的工作原理是什么啊？底层的 Lucene 介绍一下呗？

#### ES写数据过程

- 客户端选择一个 node 发送请求过去，这个 node 就是 `coordinating node` （协调节点）。
- `coordinating node` 对 document 进行**路由**，将请求转发给对应的 node（有 primary shard）。
- 实际的 node 上的 `primary shard` 处理请求，然后将数据同步到 `replica node` 。
- `coordinating node` 如果发现 `primary node` 和所有 `replica node` 都搞定之后，就返回响应结果给客户端。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/es-write.png">

#### ES读数据过程

可以通过 `doc id` 来查询，会根据 `doc id` 进行 hash，判断出来当时把 `doc id` 分配到了哪个 shard 上面去，从那个 shard 去查询。

- 客户端发送请求到**任意**一个 node，成为 `coordinate node` 。
- `coordinate node` 对 `doc id` 进行哈希路由，将请求转发到对应的 node，此时会使用 `round-robin` **随机轮询算法**，在 `primary shard` 以及其所有 replica 中随机选择一个，让读请求负载均衡。
- 接收请求的 node 返回 document 给 `coordinate node` 。
- `coordinate node` 返回 document 给客户端。

#### ES搜索数据过程

- 客户端发送请求到一个 `coordinate node` 。
- 协调节点将搜索请求转发到**所有**的 shard 对应的 `primary shard` 或 `replica shard` ，都可以。
- query phase：每个 shard 将自己的搜索结果（其实就是一些 `doc id` ）返回给协调节点，由协调节点进行数据的合并、排序、分页等操作，产出最终结果。
- fetch phase：接着由协调节点根据 `doc id` 去各个节点上**拉取实际**的 `document` 数据，最终返回给客户端。

#### 写数据底层原理

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/es-write-detail.png">

先写入内存 buffer，在 buffer 里的时候数据是搜索不到的；同时将数据写入 translog 日志文件。

如果 buffer 快满了，或者到一定时间，就会将内存 buffer 数据 `refresh` 到一个新的 `segment file` 中，但是此时数据不是直接进入 `segment file` 磁盘文件，而是先进入 `os cache` 。这个过程就是 `refresh` 。

每隔 1 秒钟，es 将 buffer 中的数据写入一个**新的** `segment file` ，每秒钟会产生一个**新的磁盘文件** `segment file` ，这个 `segment file` 中就存储最近 1 秒内 buffer 中写入的数据。

但是如果 buffer 里面此时没有数据，那当然不会执行 refresh 操作，如果 buffer 里面有数据，默认 1 秒钟执行一次 refresh 操作，刷入一个新的 segment file 中。

操作系统里面，磁盘文件其实都有一个东西，叫做 `os cache` ，即操作系统缓存，就是说数据写入磁盘文件之前，会先进入 `os cache` ，先进入操作系统级别的一个内存缓存中去。只要 `buffer` 中的数据被 refresh 操作刷入 `os cache` 中，这个数据就可以被搜索到了。

为什么叫 es 是**准实时**的？ `NRT` ，全称 `near real-time` 。默认是每隔 1 秒 refresh 一次的，所以 es 是准实时的，因为写入的数据 1 秒之后才能被看到。可以通过 es 的 `restful api` 或者 `java api` ，**手动**执行一次 refresh 操作，就是手动将 buffer 中的数据刷入 `os cache` 中，让数据立马就可以被搜索到。只要数据被输入 `os cache` 中，buffer 就会被清空了，因为不需要保留 buffer 了，数据在 translog 里面已经持久化到磁盘去一份了。

重复上面的步骤，新的数据不断进入 buffer 和 translog，不断将 `buffer` 数据写入一个又一个新的 `segment file` 中去，每次 `refresh` 完 buffer 清空，translog 保留。随着这个过程推进，translog 会变得越来越大。当 translog 达到一定长度的时候，就会触发 `commit` 操作。

commit 操作发生第一步，就是将 buffer 中现有数据 `refresh` 到 `os cache` 中去，清空 buffer。然后，将一个 `commit point` 写入磁盘文件，里面标识着这个 `commit point` 对应的所有 `segment file` ，同时强行将 `os cache` 中目前所有的数据都 `fsync` 到磁盘文件中去。最后**清空** 现有 translog 日志文件，重启一个 translog，此时 commit 操作完成。

这个 commit 操作叫做 `flush` 。默认 30 分钟自动执行一次 `flush` ，但如果 translog 过大，也会触发 `flush` 。flush 操作就对应着 commit 的全过程，我们可以通过 es api，手动执行 flush 操作，手动将 os cache 中的数据 fsync 强刷到磁盘上去。

translog 日志文件的作用是什么？你执行 commit 操作之前，数据要么是停留在 buffer 中，要么是停留在 os cache 中，无论是 buffer 还是 os cache 都是内存，一旦这台机器死了，内存中的数据就全丢了。所以需要将数据对应的操作写入一个专门的日志文件 `translog` 中，一旦此时机器宕机，再次重启的时候，es 会自动读取 translog 日志文件中的数据，恢复到内存 buffer 和 os cache 中去。

translog 其实也是先写入 os cache 的，默认每隔 5 秒刷一次到磁盘中去，所以默认情况下，可能有 5 秒的数据会仅仅停留在 buffer 或者 translog 文件的 os cache 中，如果此时机器挂了，会**丢失** 5 秒钟的数据。但是这样性能比较好，最多丢 5 秒的数据。也可以将 translog 设置成每次写操作必须是直接 `fsync` 到磁盘，但是性能会差很多。

实际上你在这里，如果面试官没有问你 es 丢数据的问题，你可以在这里给面试官炫一把，你说，其实 es 第一是准实时的，数据写入 1 秒后可以搜索到；可能会丢失数据的。有 5 秒的数据，停留在 buffer、translog os cache、segment file os cache 中，而不在磁盘上，此时如果宕机，会导致 5 秒的**数据丢失**。

**总结一下**，数据先写入内存 buffer，然后每隔 1s，将数据 refresh 到 os cache，到了 os cache 数据就能被搜索到（所以我们才说 es 从写入到能被搜索到，中间有 1s 的延迟）。每隔 5s，将数据写入 translog 文件（这样如果机器宕机，内存数据全没，最多会有 5s 的数据丢失），translog 大到一定程度，或者默认每隔 30mins，会触发 commit 操作，将缓冲区的数据都 flush 到 segment file 磁盘文件中。

#### 删除/更新数据底层原理

如果是删除操作，commit 的时候会生成一个 `.del` 文件，里面将某个 doc 标识为 `deleted` 状态，那么搜索的时候根据 `.del` 文件就知道这个 doc 是否被删除了。

如果是更新操作，就是将原来的 doc 标识为 `deleted` 状态，然后新写入一条数据。

buffer 每 refresh 一次，就会产生一个 `segment file` ，所以默认情况下是 1 秒钟一个 `segment file` ，这样下来 `segment file` 会越来越多，此时会定期执行 merge。每次 merge 的时候，会将多个 `segment file` 合并成一个，同时这里会将标识为 `deleted` 的 doc 给**物理删除掉**，然后将新的 `segment file` 写入磁盘，这里会写一个 `commit point` ，标识所有新的 `segment file` ，然后打开 `segment file` 供搜索使用，同时删除旧的 `segment file` 。

### ES倒排索引

在搜索引擎中，每个文档都有一个对应的文档 ID，文档内容被表示为一系列关键词的集合。例如，文档 1 经过分词，提取了 20 个关键词，每个关键词都会记录它在文档中出现的次数和出现位置。

那么，倒排索引就是**关键词到文档** ID 的映射，每个关键词都对应着一系列的文件，这些文件中都出现了关键词。

举例有如下文档：

| DocId |                      Doc                       |
| :---: | :--------------------------------------------: |
|   1   |           谷歌地图之父跳槽 Facebook            |
|   2   |           谷歌地图之父加盟 Facebook            |
|   3   |    谷歌地图创始人拉斯离开谷歌加盟 Facebook     |
|   4   | 谷歌地图之父跳槽 Facebook 与 Wave 项目取消有关 |
|   5   |     谷歌地图之父拉斯加盟社交网站 Facebook      |

对文档分词后，得到如下<font color='blue'>倒排索引</font>

| WordId | Word     | DocIds    |
| ------ | -------- | --------- |
| 1      | 谷歌     | 1,2,3,4,5 |
| 2      | 地图     | 1,2,3,4,5 |
| 3      | 之父     | 1,2,4,5   |
| 4      | 跳槽     | 1,4       |
| 15     | Facebook | 1,2,3,4,5 |
| 6      | 加盟     | 2,3,5     |
| 7      | 创始人   | 3         |
| 8      | 拉斯     | 3,5       |
| 9      | 离开     | 3         |
| 10     | 与       | 4         |
| ...    | ...      | ...       |

另外，实用的倒排索引还可以记录更多的信息，比如文档频率信息，表示在文档集合中有多少个文档包含某个单词。

那么，有了倒排索引，搜索引擎可以很方便地响应用户的查询。比如用户输入查询 `Facebook` ，搜索系统查找倒排索引，从中读出包含这个单词的文档，这些文档就是提供给用户的搜索结果。

要注意倒排索引的两个重要细节：

- <font color='blue'>倒排索引中的所有词项对应一个或多个文档；</font>
- <font color='red'>倒排索引中的词项根据字典顺序升序排列</font>

### ES 在数据量很大的情况下（数十亿级别）如何提高查询效率啊？

你往 es 里写的数据，实际上都写到磁盘文件里去了，**查询的时候**，操作系统会将磁盘文件里的数据自动缓存到<font color='red'> filesystem cache </font>里面去。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/es-search-process.png">

es 的搜索引擎严重依赖于底层的 `filesystem cache` ，你如果给 `filesystem cache` 更多的内存，尽量让内存可以容纳所有的 `idx segment file ` 索引数据文件，那么你搜索的时候就基本都是走内存的，性能会非常高。

性能差距究竟可以有多大？我们之前很多的测试和压测，如果走磁盘一般肯定上秒，搜索性能绝对是秒级别的，1 秒、5 秒、10 秒。但如果是走 `filesystem cache` ，是走纯内存的，那么一般来说性能比走磁盘要高一个数量级，基本上就是毫秒级的，从几毫秒到几百毫秒不等。

这里有个真实的案例。某个公司 es 节点有 3 台机器，每台机器看起来内存很多，64G，总内存就是 `64 * 3 = 192G` 。每台机器给 es jvm heap 是 `32G` ，那么剩下来留给 `filesystem cache` 的就是每台机器才 `32G` ，总共集群里给 `filesystem cache` 的就是 `32 * 3 = 96G` 内存。而此时，整个磁盘上索引数据文件，在 3 台机器上一共占用了 `1T` 的磁盘容量，es 数据量是 `1T` ，那么每台机器的数据量是 `300G` 。这样性能好吗？ `filesystem cache` 的内存才 100G，十分之一的数据可以放内存，其他的都在磁盘，然后你执行搜索操作，大部分操作都是走磁盘，性能肯定差。

归根结底，你要让 es 性能要好，最佳的情况下，就是你的机器的内存，至少可以容纳你的总数据量的一半。

根据我们自己的生产环境实践经验，最佳的情况下，是仅仅在 es 中就存少量的数据，就是你要**用来搜索的那些索引**，如果内存留给 `filesystem cache` 的是 100G，那么你就将索引数据控制在 `100G` 以内，这样的话，你的数据几乎全部走内存来搜索，性能非常之高，一般可以在 1 秒以内。

比如说你现在有一行数据。 `id,name,age ....` 30 个字段。但是你现在搜索，只需要根据 `id,name,age` 三个字段来搜索。如果你傻乎乎往 es 里写入一行数据所有的字段，就会导致说 `90%` 的数据是不用来搜索的，结果硬是占据了 es 机器上的 `filesystem cache` 的空间，单条数据的数据量越大，就会导致 `filesystem cahce` 能缓存的数据就越少。其实，仅仅写入 es 中要用来检索的**少数几个字段**就可以了，比如说就写入 es `id,name,age` 三个字段，然后你可以把其他的字段数据存在 mysql/hbase 里，我们一般是建议用 `es + hbase` 这么一个架构。

hbase 的特点是**适用于海量数据的在线存储**，就是对 hbase 可以写入海量数据，但是不要做复杂的搜索，做很简单的一些根据 id 或者范围进行查询的这么一个操作就可以了。从 es 中根据 name 和 age 去搜索，拿到的结果可能就 20 个 `doc id` ，然后根据 `doc id` 到 hbase 里去查询每个 `doc id` 对应的**完整的数据**，给查出来，再返回给前端。

写入 es 的数据最好小于等于，或者是略微大于 es 的 filesystem cache 的内存容量。然后你从 es 检索可能就花费 20ms，然后再根据 es 返回的 id 去 hbase 里查询，查 20 条数据，可能也就耗费个 30ms，可能你原来那么玩儿，1T 数据都放 es，会每次查询都是 5~10s，现在可能性能就会很高，每次查询就是 50ms。

#### 数据预热

举个例子，拿微博来说，你可以把一些大 V，平时看的人很多的数据，你自己提前后台搞个系统，每隔一会儿，自己的后台系统去搜索一下热数据，刷到 `filesystem cache` 里去，后面用户实际上来看这个热数据的时候，他们就是直接从内存里搜索了，很快。

或者是电商，你可以将平时查看最多的一些商品，比如说 iphone 8，热数据提前后台搞个程序，每隔 1 分钟自己主动访问一次，刷到 `filesystem cache` 里去。

#### 冷热分离

es 可以做类似于 mysql 的水平拆分，就是说将大量的访问很少、频率很低的数据，单独写一个索引，然后将访问很频繁的热数据单独写一个索引。最好是将**冷数据写入一个索引中，然后热数据写入另外一个索引中**，这样可以确保热数据在被预热之后，尽量都让他们留在 `filesystem os cache` 里，**别让冷数据给冲刷掉**。

你看，假设你有 6 台机器，2 个索引，一个放冷数据，一个放热数据，每个索引 3 个 shard。3 台机器放热数据 index，另外 3 台机器放冷数据 index。然后这样的话，你大量的时间是在访问热数据 index，热数据可能就占总数据量的 10%，此时数据量很少，几乎全都保留在 `filesystem cache` 里面了，就可以确保热数据的访问性能是很高的。但是对于冷数据而言，是在别的 index 里的，跟热数据 index 不在相同的机器上，大家互相之间都没什么联系了。如果有人访问冷数据，可能大量数据是在磁盘上的，此时性能差点，就 10% 的人去访问冷数据，90% 的人在访问热数据，也无所谓了。

## Spring Quartz

### Spring Quartz详解

`Quartz是做什么用的？Quartz框架主要核心组件包括那几部分，分别作用是什么？`

**1）**Quartz是一个由java编写的开源作业调度框架，简单来说，Quartz就是启动定时任务的框架，像linux系统中的corntab，可以定时启动任务。

**2）**Quartz框架主要核心组件包括调度器、触发器、作业。调度器作为作业的总指挥，触发器作为作业的操作者，作业为应用的功能模块。

> Job为作业的接口，为任务调度的对象；JobDetail用来描述Job的实现类及其它相关的静态信息；Trigger做为作业的定时管理工具，一个Trigger只能对应一个作业实例，而一个作业实例可对应多个触发器；Scheduler做为定时任务容器，是quartz最上层的东西，它提携了所有触发器和作业，使它们协调工作，每个Scheduler都存有JobDetail和Trigger的注册，一个Scheduler中可以注册多个JobDetail和多个Trigger。

## Spring Security

### Spring Security流程

Spring Security是一个能够为基于Spring的企业应用系统提供声明式的安全访问控制解决方案的安全框架。它提供了一组可以在Spring应用上下文中配置的Bean，充分利用了Spring IoC，DI（控制反转Inversion of Control ,DI:Dependency Injection 依赖注入）和AOP（面向切面编程）功能，可以很好地跟Spring相关的功能集成起来，拥有比较好的社区支持，也相对来说比较的复杂。  

- 它的设计是基于框架内大范围的依赖的，可以被划分为以下几块。    
  - Web/Http 安全：这是最复杂的部分。通过建立 filter 和相关的 service bean 来实现框架的认证机制。当访问受保护的 URL 时会将用户引入登录界面或者是错误提示界面。 
  - 业务对象或者方法的安全：控制方法访问权限的。 
  - AuthenticationManager：处理来自于框架其他部分的认证请求。 
  - AccessDecisionManager：为 Web 或方法的安全提供访问决策。会注册一个默认的，但是我们也可以通过普通 bean 注册的方式使用自定义的 AccessDecisionManager。 
  - AuthenticationProvider：AuthenticationManager 是通过它来认证用户的。 
  - UserDetailsService：跟 AuthenticationProvider 关系密切，用来获取用户信息的。

1、 首先， 当用户登录时， 前端会把用户输入的用户名、 密码信息传输到后台， 后台用一个类对象将其封装起来，通常使用的是UsernamePasswordAuthenticationToken这个类。

2、 再来到程序负责验证这个类对象。 验证方法是调用Service根据username从数据库中取用户信息到实体类的实例中，比较两者的密码， 如果密码正确就成功登陆， 同时把包含着用户的用户名、 密码、 所具有的权限等信息的类对象放到SecurityContextHolder(安全上下文容器， 类似Session) 中去。

3、 其次， 在用户访问一个资源的时候， 需要先判断是否是受限资源。 如果是的话还要判断当前是否未登录，没有的话就跳到登录页面。

4、 最后如果用户已经登录， 并访问一个受限资源的时候， 程序要根据url去数据库中取出该资源所对应的所有可以访问的角色， 然后拿着当前用户的所有角色一一对比， 判断用户是否可以访问。

### Spring Security中四种权限控制方式？

- 表达式控制URL路径权限

```java
protected void configure(HttpSecurity http) throws Exception {
    http.authorizeRequests()
            .antMatchers("/admin/**").hasRole("admin")
            .antMatchers("/user/**").hasAnyRole("admin", "user")
            .anyRequest().authenticated()
            .and()
            ...
}
```

这里表示访问 `/admin/**` 格式的路径需要 admin 角色，访问 `/user/**` 格式的路径需要 admin 或者 user 角色。

- 表达式控制方法权限
- 使用过滤注解
- 动态权限

### Spring Security 防止用户在多处同时登录（一个用户同时只能登录一次）

```java
//以下这句就可以控制单个用户只能创建一个session，也就只能在服务器登录一次 
http.sessionManagement().maximumSessions(1).expiredUrl("/login");
```

在org.springframework.security.web.authentication.session.ConcurrentSessionControlAuthenticationStrategy包下的onAuthentication方法（每次用户登录都会触发），会依据用户登录的authentication取出改用户在服务器的所有session，并计算该用户在服务器创建了多少个session，如果session多于设置的数量，会使用排序算法，得到最早的session，并将其设置为过期（删除）。

## 计算机网络

### OSI七层模型？TCP/IP四层模型？

1. **应⽤层：**其作⽤是通过应⽤程序间的交互来完成特定的⽹络应⽤。例如域名系统 DNS，⽀持万维⽹应⽤的 HTTP 协议，电⼦邮件系统采⽤的 SMTP 协议等。在应⽤层交互的数据单元我们称之为报⽂。
2. **表示层：**其作⽤是使通信的应⽤程序能够解释交换数据的含义，其位于 OSI 参考模型的第六层，向上为应⽤层提供服务，向下接收来⾃会话层的服务。该层提供的服务主要包括数据压缩，数据加密以及数据描述。
3. **会话层：**负责建⽴、管理和终⽌表示层实体之间的通信会话。
4. **传输层：**为两台主机进程之间的通信提供服务。应⽤程序利⽤该服务传送应⽤层报⽂。该服务并不针对某⼀特定的应⽤，多种应⽤可以使⽤同⼀个传输层服务。
5. **⽹络层：**两台计算机之间传送数据时其通信链路往往不⽌⼀条，所传输的信息甚⾄可能经过很多通信⼦⽹。⽹络层的主要任务就是选择合适的⽹间路由和交换节点，确保数据按时成功传送。
6. **数据链路层：**在两个相邻节点之间传送数据时，数据链路层将⽹络层交下来的 IP 数据报组装成帧，在两个相邻节点间的链路上传送帧。
7. **物理层：**实现计算机节点之间⽐特流的透明传送，尽可能屏蔽掉具体传输介质和物理设备的差异。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/tcpip.png">

> **路由器？交换机？集线器分别在哪一层？**
>
> 路由器位于网络层，交换机位于数据链路层，集线器位于物理层

### TCP和UDP区别？使用场景？（用友Java）

#### 区别

1. **连接**

- tcp是⾯向连接的传输层协议，传输数据前先要建⽴连接。
- udp是不需要连接，即刻传输数据

2. **服务对象**

- tcp是⼀对⼀的两点服务，即⼀条连接只有两个端点
- udp⽀持⼀对⼀、⼀对多、多对多的交互通信

3. **可靠性**

- tcp是可靠交付数据的，数据可以⽆差错、不丢失、不重复、按序到达
- udp是尽最⼤努⼒交付，不保证可靠交付数据

4. **拥塞控制、流量控制**

- tcp有拥塞控制和流量控制机制，保证数据传输的安全性
- udp则没有，即使⽹络⾮常拥堵了，也不会影响udp的发送速率

5. **⾸部开销**

- tcp⾸部⻓度较⻓，会有⼀定的开销，⾸部在没有使⽤【选项】字段时是20个字节，如果使⽤了
  【选项】字段则会变⻓的。
- udp⾸部只有8个字节，并且是固定不变的，开销较少。

6. **传输⽅式**

- tcp是流式传输，没有边界，但保证顺序和可靠
- udp是⼀个包⼀个包的发送，是有边界的，但可能会丢包和乱序

7. **分⽚不同**

- tcp的数据⼤⼩如果⼤于MSS⼤⼩，则会在`传输层进⾏分⽚`，⽬标主机收到后，也同样在`传输层组装tcp数据包`，如果中途丢失了⼀个分⽚，只需要传输丢失的这个分⽚。
- udp的数据⼤⼩如果⼤于MTU⼤⼩，则会在`网络层进⾏分⽚`，⽬标主机收到后，在`网络层组装完数据`，接着再传给传输层，但是如果中途丢了⼀个分⽚，则就需要重传所有的数据包，这样传输效率⾮常差，所以通常udp的报⽂应该⼩于MTU。

#### 使用场景

TCP 是面向连接，能保证数据的可靠性交付，因此经常用于：

- FTP文件传输

- HTTP / HTTPS

UDP 面向无连接，它可以随时发送数据，再加上UDP本身的处理既简单又高效，因此经常用于：

- 包总量较少的通信，如 DNS 、SNMP等
- 视频、音频等多媒体通信
- 广播通信

### 详细介绍一下TCP的三次握手机制和四次挥手机制？（用友Java）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/sanciwoshou.png">

#### 三次握手机制？（百度测开）

- <font color='blue'>第一次握手：</font>客户端请求建立连接，向服务端发送一个同步报文（SYN=1），同时选择一个随机数 seq = x 作为初始序列号，并进入`SYN_SENT`状态，等待服务器确认。
- <font color='blue'>第二次握手：</font>服务端收到连接请求报文后，如果同意建立连接，则向客户端发送同步确认报文
  （SYN=1，ACK=1），确认号为 ack = x + 1，同时选择一个随机数 seq = y 作为初始序列号，此时
  服务器进入`SYN_RECV`状态。
- <font color='blue'>第三次握手：</font>客户端收到服务端的确认后，向服务端发送一个确认报文（ACK=1），确认号为 ack = y + 1，序列号为 seq = x + 1，客户端和服务器进入`ESTABLISHED`状态，完成三次握手。

#### 为什么需要三次握手，而不是两次？

1. **防止已过期的连接请求报文突然又传送到服务器，因而产生错误和资源浪费，即阻止重复历史连接的初始化**

> 客户端由于某种原因发送了两个不同序号的 SYN 包，我们知道⽹络环境是复杂的，旧的数据包有可能先到达服务器。如果是两次握⼿，服务器收到旧的 SYN 就会⽴刻建⽴连接，那么会造成⽹络异常。
>
> `如果是三次握⼿，服务器需要回复 SYN+ACK 包，客户端会对⽐应答的序号，如果发现是旧的报⽂，就会给服务器发 RST 报⽂，直到正常的 SYN 到达服务器后才正常建⽴连接`。
>
> 在双方两次握手即可建立连接的情况下，假设客户端发送 A 报文段请求建立连接，由于网络原因造成 A 暂时无法到达服务器，服务器接收不到请求报文段就不会返回确认报文段。
>
> 客户端在长时间得不到应答的情况下重新发送请求报文段 B，这次 B 顺利到达服务器，服务器随即返回确认报文并进入 ESTABLISHED 状态，客户端在收到确认报文后也进入 ESTABLISHED 状态，双方建立连接并传输数据，之后正常断开连接。
>
> 此时姗姗来迟的 A 报文段才到达服务器，服务器随即返回确认报文并进入 ESTABLISHED 状态，但是已经进入 CLOSED 状态的客户端无法再接受确认报文段，更无法进入 ESTABLISHED 状态，这将导致服务器长时间单方面等待，造成资源浪费。

2. **三次握手才能让双方均确认自己和对方的发送和接收能力都正常**

> 第一次握手：客户端只是发送处请求报文段，什么都无法确认，而服务器可以确认自己的接收能力和对方的发送能力正常；
>
> 第二次握手：客户端可以确认自己发送能力和接收能力正常，对方发送能力和接收能力正常；
>
> 第三次握手：服务器可以确认自己发送能力和接收能力正常，对方发送能力和接收能力正常；

3. **告知对方自己的初始序号值，并确认收到对方的初始序号值**

> TCP 实现了可靠的数据传输，原因之一就是 TCP 报文段中维护了序号字段和确认序号字段，通过这两个字段双方都可以知道在自己发出的数据中，哪些是已经被对方确认接收的。这两个字段的值会在初始序号值得基础递增，如果是两次握手，只有发起方的初始序号可以得到确认，而另一方的初始序号则得不到确认。

#### 三次握手连接阶段，最后一次ACK包丢失，会发生什么？

**服务端：**

- 第三次的ACK在网络中丢失，那么服务端该TCP连接的状态为SYN_RECV,并且会根据 TCP的超时重传机制，会等待3秒、6秒、12秒后重新发送SYN+ACK包，以便客户端重新发送ACK包。
- 如果重发指定次数之后，仍然未收到 客户端的ACK应答，那么一段时间后，服务端自动关闭这个连接。

**客户端：**

客户端认为这个连接已经建立，如果客户端向服务端发送数据，服务端将以RST包（Reset，标示复位，
用于异常的关闭连接）响应。此时，客户端知道第三次握手失败。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/sicihuishou.png">

#### 四次挥手机制？

- <font color='blue'>第一次挥手：</font>客户端向服务端发送连接释放报文（FIN=1，ACK=1），主动关闭连接，同时等待服务端的确认。
  - 序列号 seq = u，即客户端上次发送的报文的最后一个字节的序号 + 1
  - 确认号 ack = k, 即服务端上次发送的报文的最后一个字节的序号 + 1
- <font color='blue'>第二次挥手：</font>服务端收到连接释放报文后，立即发出确认报文（ACK=1），序列号 seq = k，确认号 ack = u + 1。
  - 这时 TCP 连接处于半关闭状态，即客户端到服务端的连接已经释放了，但是服务端到客户端的连接还未释放。这表示客户端已经没有数据发送了，但是服务端可能还要给客户端发送数据。
- <font color='blue'>第三次挥手：</font>服务端向客户端发送连接释放报文（FIN=1，ACK=1），主动关闭连接，同时等待 A 的确认。
  - 序列号 seq = w，即服务端上次发送的报文的最后一个字节的序号 + 1。
  - 确认号 ack = u + 1，与第二次挥手相同，因为这段时间客户端没有发送数据
- <font color='blue'>第四次挥手：</font>客户端收到服务端的连接释放报文后，立即发出确认报文（ACK=1），序列号 seq = u + 1，确认号为 ack = w + 1。
  - 此时，客户端就进入了 `TIME-WAIT `状态。注意此时客户端到 TCP 连接还没有释放，必须经过 `2*MSL`（最长报文段寿命）的时间后，才进入 CLOSED 状态。而服务端只要收到客户端发出的确
    认，就立即进入 CLOSED 状态。可以看到，服务端结束 TCP 连接的时间要比客户端早一些。

#### 为什么客户端的TIME-WAIT状态必须等待2MSL？

1. **确保 ACK 报文能够到达服务端，从而使服务端正常关闭连接**

> 第四次挥手时，客户端第四次挥手的 ACK 报文不一定会到达服务端。服务端会超时重传 FIN/ACK 报文，此时如果客户端已经断开了连接，那么就无法响应服务端的二次请求，这样服务端迟迟收不到 FIN/ACK 报文的确认，就无法正常断开连接。
>
> MSL 是报文段在网络上存活的最长时间。客户端等待 2MSL 时间，即`「客户端 ACK 报文 1MSL 超时 + 服务端 FIN 报文 1MSL 传输」`，就能够收到服务端重传的 FIN/ACK 报文，然后客户端重传一次 ACK 报文，并重新启动 2MSL 计时器。如此保证服务端能够正常关闭。
>
> 如果服务端重发的 FIN 没有成功地在 2MSL 时间里传给客户端，服务端则会继续超时重试直到断开连接。

2. **防止已失效的连接请求报文段出现在之后的连接中**

> TCP 要求在 2MSL 内不使用相同的序列号。客户端在发送完最后一个 ACK 报文段后，再经过时间 2MSL，就可以保证本连接持续的时间内产生的所有报文段都从网络中消失。这样就可以使下一个连接中不会出现这种旧的连接请求报文段。或者即使收到这些过时的报文，也可以不处理它。

#### TIME-WAIT 状态过多会产生什么后果？怎样处理？

1. 从服务器来讲，短时间内关闭了大量的Client连接，就会造成服务器上出现大量的TIME_WAIT连接，严重消耗着服务器的资源，此时部分客户端就会显示连接不上。

2. 从客户端来讲，`客户端TIME_WAIT过多，就会导致端口资源被占用`，因为端口就65536个，被占满就会导致无法创建新的连接。

<font color='red'>解决办法：</font>

- 服务器可以设置 `SO_REUSEADDR 套接字`选项来避免 TIME_WAIT状态，此套接字选项告诉内核，即使此端口正忙（处于TIME_WAIT状态），也请继续并重用它。
- 调整系统内核参数，修改/etc/sysctl.conf文件

> `net.ipv4.tcp_tw_reuse = 1 `表示开启重用。允许将TIME-WAIT sockets重新用于新的TCP连接，默认为0，表示关闭；
>
> `net.ipv4.tcp_tw_recycle = 1 `表示开启TCP连接中TIME-WAIT sockets的快速回收，默认为0，表示关闭。

- 强制关闭，发送 RST 包越过TIME_WAIT状态，直接进入CLOSED状态

### TCP如何保证可靠性？

- **检验和：**通过检验和的方式，接收端可以检测出来数据是否有差错和异常，假如有差错就会直接丢弃TCP段，重新发送。
- **数据分块：**应⽤数据被分割成 TCP 认为最适合发送的数据块。
- **序列号/确认应答：**序列号的作用不仅仅是应答的作用，有了序列号能够将接收到的数据根据序列号排序，并且去掉重复序列号的数据。TCP传输的过程中，每次接收方收到数据后，都会对传输方进行确认应答。也就是发送ACK报文，这个ACK报文当中带有对应的确认序列号，告诉发送方，接收到了哪些数据，下一次的数据从哪里发。
- **超时重传：**超时重传是指发送出去的数据包到接收到确认包之间的时间，如果超过了这个时间会被认为是丢包了，需要重传，最大超时时间是动态计算的。
- **ARQ协议：**也是为了实现可靠传输的，它的基本原理就是每发完⼀个分组就停⽌发送，等待对⽅确认，在收到确认后再发下⼀个分组。
- **拥塞控制：**在数据传输过程中，可能由于网络状态的问题，造成网络拥堵，此时引入拥塞控制机制，在保证TCP可靠性的同时，提高性能。
- **流量控制：** TCP 连接的双⽅都有⼀个固定⼤⼩的缓冲空间，发送⽅发送的数据量不能超过接收端缓冲区的⼤⼩。当接收⽅来不及处理发送⽅的数据，会提示发送⽅降低发送的速率，防⽌产⽣丢包。<font color='red'>TCP 通过滑动窗⼝协议来⽀持流量控制机制。</font>

### 详细讲一下TCP的滑动窗口？

在进行数据传输时，如果传输的数据比较大，就需要拆分为多个数据包进行发送。TCP 协议需要对数据进行确认后，才可以发送下一个数据包。这样一来，就会在等待确认应答包环节浪费时间。

为了避免这种情况，TCP引入了窗口概念。`窗口大小指的是不需要等待确认应答包而可以继续发送数据包的最大值。`

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/huadongchuankou.png">

从上面的图可以看到滑动窗口左边的是已发送并且被确认的分组，滑动窗口右边是还没有轮到的分组。

滑动窗口里面也分为两块，`一块是已经发送但是未被确认的分组`，`另一块是窗口内等待发送的分组`。随着已发送的分组不断被确认，窗口内等待发送的分组也会不断被发送。整个窗口就会往右移动，让还没轮到的分组进入窗口内。可以看到滑动窗口起到了一个限流的作用，也就是说当前滑动窗口的大小决定了当前 TCP 发送包的速率，而`滑动窗口的大小取决于拥塞控制窗口和流量控制窗口的两者间的最小值`。

### 详细讲下拥塞控制？（用友Java）

TCP使用了四种算法来实现拥塞控制：

- **慢开始 (slow-start)**
- **拥塞避免 (congestion avoidance)**
- **快重传 (fast retransmit)**
- **快恢复 (fast recovery)**

发送方维持一个叫做`拥塞窗口cwnd`（congestion window）的状态变量。当`cwnd >= 慢开始门限（ssthresh）`时，改用拥塞避免算法。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/yongsaikongzhi2.png">

**<font color='blue'>慢开始：</font>**不要一开始就发送大量的数据，由小到大逐渐增加拥塞窗口的大小，令 cwnd = 1，发送⽅只能发送 1 个报⽂段；当收到确认后，将 cwnd 加倍，因此之后发送⽅能够发送的报⽂段数量为：2、4、8 ...

**<font color='blue'>拥塞避免：</font>**拥塞避免算法让拥塞窗口缓慢增长，即每经过一个往返时间RTT就把发送方的拥塞窗口cwnd加1而不是加倍，这样拥塞窗口按`线性规律`缓慢增长。如果出现了超时，则令 ssthresh = cwnd / 2，然后重新执⾏慢开始.

**<font color='blue'>快重传：</font>**我们可以剔除一些不必要的拥塞报文，提高网络吞吐量。比如接收方在收到一个失序的报文段后就立即发出重复确认，而不要等到自己发送数据时捎带确认。`快重传规定：发送方只要一连收到三个重复确认就应当立即重传对方尚未收到的报文段，而不必继续等待设置的重传计时器时间到期`。

**<font color='blue'>快恢复：</font>**主要是配合快重传。当发送方连续收到三个重复确认时，就执行“乘法减小”算法，把ssthresh门限减半（为了预防网络发生拥塞），但接下来并不执行慢开始算法，因为如果网络出现拥塞的话就不会收到好几个重复的确认，收到三个重复确认说明网络状况还可以。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/yongsaikongzhi1.png">

### HTTP常见状态码？

**「200 OK」**是最常⻅⻅的成功状态码，表示⼀切正常。如果是⾮HEAD请求，服务器返回的响应头都会
有 body 数据。

**「204 No Content」**也是常⻅⻅的成功状态码，与 200 OK 基本相同，但响应头没有 body 数据。

**「206 Partial Content」**是应⽤于 HTTP 分块下载或断点续传，表示响应返回的 body 数据并不是资源
的全部，⽽是其中的⼀部分，也是服务器处理成功的状态。

**「301 Moved Permanently」**表示永久重定向，说明请求的资源已经不存在了，需改⽤新的 URL 再次
访问。

**「302 Found」**表示临时重定向，说明请求的资源还在，但暂时需要⽤另⼀个 URL 来访问。

**「304 Not Modiﬁed」**不具有跳转的含义，表示资源未修改，重定向已存在的缓冲⽂件，也称缓存重定 
向，⽤于缓存控制。

**「400 Bad Request」**表示客户端请求的报⽂有错误，但只是个笼统的错误。

**「403 Forbidden」**表示服务器禁⽌访问资源，并不是客户端的请求出错。

**「404 Not Found」**表示请求的资源在服务器上不存在或未找到，所以⽆法提供给客户端。

**「500 Internal Server Error」**与 400 类型，是个笼统通⽤的错误码，服务器发⽣了什么错误，我们并
不知道。

**「501 Not Implemented」**表示客户端请求的功能还不⽀持，类似“即将开业，敬请期待”的意思。

**「502 Bad Gateway」**通常是服务器作为⽹关或代理时返回的错误码，表示服务器⾃身⼯作正常，访问
后端服务器发⽣了错误。

**「503 Service Unavailable」**通常表示服务器目前无法使用（由于超载或停机维护），这只是暂时状态。

### IP报文格式和TCP报文格式是什么？

<img src="https://pic4.zhimg.com/80/v2-ef4d72148300f496eddc926709bb7a97_720w.jpg">

--------------------

<img src="https://images2015.cnblogs.com/blog/964016/201608/964016-20160829215953168-1927861560.png">

### get和post区别？（携程测开，百度测开）

- **用途区别**
  - get是从服务器上获取数据
  - post是向服务器提交数据
- **安全性区别**
  - get是通过URL请求传递用户所输入的信息内容，这些信息内容在提交的过程中都会暴露在浏览器的地址栏中，所以说安全性极低
  - post不会将提交的内容暴露在浏览器地址栏中，放在body中，相比get是安全的
- **长度限制**
  - get在请求提交数据参数时浏览器与服务器对URL（统一资源定位符）都有长度的限制
  - post没有长度限制
- **幂等性**
  - get方法获取资源，没有副作用，所以是幂等的
  - post用于创建资源，是有副作用的，且副作用不同，所以post不是幂等的
- **数据包**
  - get会产生一个TCP数据包
  - post会产生两个TCP数据包（不一定，FireFox浏览器只会产生一个数据包）
- **编码格式**
  - get请求只能进行url编码
  - post请求支持多种编码格式

### 传输层端口范围？

传输层端口号为16位整数，可以编号65536个（`2的16次方`）

### 讲下HTTP的多路复用？

Keep-Alive: 一定时间内，同一域名多次请求数据，只建立一次HTTP请求，其他请求可复用每一次建立的连接通道，以达到提高请求效率的问题，这里面所说的一定时间是可以配置的，不管你用的是Apache还是nginx。

### 讲下HTTP请求报文和响应报文的格式？

#### 请求报文格式

1. **请求行（请求方法+URI协议+版本）**
2. **请求头部**
3. **空行**
4. **请求主体**

```json
GET/sample.jspHTTP/1.1 请求行
Accept:image/gif.image/jpeg, 请求头部
Accept-Language:zh-cn
Connection:Keep-Alive
Host:localhost
User-Agent:Mozila/4.0(compatible;MSIE5.01;Window NT5.0)
Accept-Encoding:gzip,deflate
username=jinqiao&password=1234 请求主体
```

#### 响应报文

1. **状态行（版本+状态码+原因短语）**
2. **响应首部**
3. **空行**
4. **响应主体**

```html
HTTP/1.1 200 OK
Server:Apache Tomcat/5.0.12
Date:Mon,6Oct2003 13:23:42 GMT
Content-Length:112

<html>
    <head>
        <title>HTTP响应示例<title>
    </head>
    <body>
        Hello HTTP!
    </body>
</html>
```

### HTTP为什么是无状态协议？

服务器向我们的客户发送请求的文件，而不存储任何关于该客户的状态信息，比如说，我们的用户在几秒钟内两次请求同一个对象，服务器不会因为刚刚才给该客户提供了对象，就不会再提供对象，服务器会重新发送该对象给我们的客户，就好像我们的服务器忘记了刚刚不久之前才做的事情那样。

### HTTP1.0和HTTP1.1的区别？

1. **长连接：**HTTP 1.1支持长连接（Persistent Connection）和请求的流水线（Pipelining）处理，在一个TCP连接上可以传送多个HTTP请求和响应，减少了建立和关闭连接的消耗和延迟，在HTTP1.1中默认开启`Connection：keep-alive`，一定程度上弥补了HTTP1.0每次请求都要创建连接的缺点。
2. **缓存处理：**在HTTP1.0中主要使用header里的If-Modified-Since,Expires来做为缓存判断的标准，HTTP1.1则引入了更多的缓存控制策略，可供选择的缓存头来控制缓存策略。
3. **带宽优化及网络连接的使用：**HTTP1.0中，存在一些浪费带宽的现象，例如客户端只是需要某个对象的一部分，而服务器却将整个对象送过来了，并且不支持断点续传功能，HTTP1.1则在请求头引入了range头域，它允许只请求资源的某个部分，即返回码是206（Partial Content），这样就方便了开发者自由的选择以便于充分利用带宽和连接。
4. **错误通知的管理：**在HTTP1.1中新增了24个错误状态响应码，如409（Conflict）表示请求的资源与资源的当前状态发生冲突；410（Gone）表示服务器上的某个资源被永久性的删除。
5. **Host头处理：**在HTTP1.0中认为每台服务器都绑定一个唯一的IP地址，因此，请求消息中的URL并没有传递主机名（hostname）。但随着虚拟主机技术的发展，在一台物理服务器上可以存在多个虚拟主机（Multi-homed Web Servers），并且它们共享一个IP地址。HTTP1.1的请求消息和响应消息都应支持Host头域，且请求消息中如果没有Host头域会报告一个错误（400 Bad Request）。

### HTTP1.1和HTTP2.0的区别？

- **新的二进制格式：**HTTP1.1的解析是基于文本。基于文本协议的格式解析存在天然缺陷，文本的
  表现形式有多样性，要做到健壮性考虑的场景必然很多，二进制则不同，只认0和1的组合。基于这
  种考虑HTTP2.0的协议解析决定采用二进制格式，实现方便且健壮。
- **多路复用：**即连接共享，即每一个request都是用作连接共享机制的。一个request对应一个id，
  这样一个连接上可以有多个request，每个连接的request可以随机的混杂在一起，接收方可以根据
  request的 id将request再归属到各自不同的服务端请求里面。
- **头部压缩：**HTTP1.1的头部（header）带有大量信息，而且每次都要重复发送；HTTP2.0使用
  encoder来减少需要传输的header大小，通讯双方各自cache一份header fields表，既避免了重复
  header的传输，又减小了需要传输的大小。
- **服务端推送：**服务器除了对最初请求的响应外，服务器还可以额外的向客户端推送资源，而无需
  客户端明确的请求。

### HTTP九种请求方式？（用友Java）

HTTP1.0定义了三种请求方法： GET, POST 和 HEAD方法。

HTTP1.1新增了五种请求方法：OPTIONS, PUT, DELETE, TRACE 、PATCH和 CONNECT 方法

- **POST 请求**
  POST ：表示向指定资源提交数据，数据包含在请求头中。有可能导致新的资源建立或原有资源修改。 POST 请求是 HTTP 请求中使用最多的一种请求方式。
- **GET 请求**
  GET ：表示请求指定的页面信息，并返回实体内容。
- **HEAD 请求**
  HEAD ：类似于 GET，只不过返回的响应体中没有具体内容，只有报文头，用于获取报文头。
- **PUT 请求**
  PUT ：从客户端向服务器传送的数据取代指定的内容，即向指定的位置上传最新的内容。
- **PATCH 请求**
  PATCH ：对 PUT 方法的补充，用来对已知资源进行局部更新。
- **OPTIONS 请求**
  OPTIONS ：返回服务器针对特殊资源所支持的 HTML请求方式或允许客户端查看服务器的性能。
- **DELETE 请求**
  DELETE ：请求服务器删除 Request-URL 所标识的资源。
- **CONNECT 请求**
  CONNECT ：HTTP 1.1 中预留给能够将连接改为管道方式的代理服务器。
- **TRACE 请求**
  TRACE ：回显服务器收到的请求，主要用于测试和诊断。

<img src="https://images2018.cnblogs.com/blog/1418466/201808/1418466-20180810112625596-2103906128.png">

### HTTP和HTTPs区别？（百度测开）

1. https协议需要到ca申请证书，一般免费证书较少，因而需要一定费用。
2. http是超文本传输协议，信息是明文传输，https则是具有安全性的ssl加密传输协议。
3. http和https使用的是完全不同的连接方式，用的端口也不一样，前者是80，后者是443。
4. http的连接很简单，是无状态的；HTTPS协议是由SSL+HTTP协议构建的可进行加密传输、身份认证的网络协议，比http协议安全。

### HTTPS公开密钥的认证过程以及建立过程？

#### 密钥认证过程

1）服务器把⾃⼰的公开密钥登陆⾄数字证书认证机构

2）数字证书认证机构⽤⾃⼰的私有密钥向服务器的公开密码署数字签名并颁发公钥证书

3）客户端拿到服务器的公钥证书后，使⽤数字认证机构的公开密钥向数字认证机构验证公钥证书上的数字签名，确保服务器公钥的真实性

4）认证成功后，客户端使⽤服务器的公开密钥对报⽂进⾏加密发送

5）服务器⽤私有密钥对报⽂解密

#### HTTPS建立过程

1）客户端发送`Client Hello`报⽂开始SSL通信，报⽂中包括：客户端⽀持的SSL版本，加密组件列表(加密算法，密钥⻓度等)

2）服务器发送`Server Hello`报⽂作为响应，报⽂中包括：服务器从客户端筛选出的SSL版本，加密组件列表

3）服务器发送`Certificate`报⽂，报⽂中包括：公开密钥证书

4）服务器发送`Server Hello Done`报⽂，最初阶段的SSL握⼿协商部分结束

5）客户端发送`Client Key Exchange`报⽂，报⽂中包括：`Pre-master secret`即使⽤公开密钥加密过的随机密码串

6）客户端发送`Change Cipher Spec`报⽂，提示服务器在此之后的通信采⽤Pre-master secret进⾏加密

7）客户端发送`Finished`报⽂，报⽂中包括：连接⾄今的全部报⽂的整体校验值。

8）若校验成功，服务器发送`Change Cipher Spec`报⽂

9）服务器发送`Finished`报⽂

10）SSL连接建⽴完成

### HTTPs绝对安全吗？

不是绝对安全的，可以通过中间人攻击。

> 中间人攻击是指攻击者与通讯的两端分别创建独立的联系，并交换其所收到的数据，使通讯的两端认为他们正在通过一个私密的连接与对方直接对话，但事实上整个会话都被攻击者完全控制。
>
> HTTPS 使用了 SSL 加密协议，是一种非常安全的机制，目前并没有方法直接对这个协议进行攻击，一般都是在建立 SSL 连接时，拦截客户端的请求，利用中间人获取到 CA证书、非对称加密的公钥、对称加密的密钥；有了这些条件，就可以对请求和响应进行拦截和篡改。

<img src="https://img-service.csdnimg.cn/img_convert/562fb8cd74af9482e93be73c8e16ea25.png">

**过程原理：**

1. 本地请求被劫持（如DNS劫持等），所有请求均发送到中间人的服务器
2. 中间人服务器返回中间人自己的证书
3. 客户端创建随机数，通过中间人证书的公钥对随机数加密后传送给中间人，然后凭随机数构造对
4. 加密对传输内容进行加密传输
5. 中间人因为拥有客户端的随机数，可以通过对称加密算法进行内容解密
6. 中间人以客户端的请求内容再向官方网站发起请求
7. 因为中间人与服务器的通信过程是合法的，官方网站通过建立的安全通道返回加密后的数据
8. 中间人凭借与官方网站建立的对称加密算法对内容进行解密
9. 中间人通过与客户端建立的对称加密算法对官方内容返回的数据进行加密传输
10. 客户端通过与中间人建立的对称加密算法对返回结果数据进行解密

### 一次完整的浏览器输入网址之后的过程？（用友Java）

1. **域名解析**

> 浏览器首先搜索自己的DNS缓存，若没有，则搜索操作系统的DNS缓存（维护一张域名与IP的对应表）；若没有，则搜索操作系统的hosts文件（维护一张域名与IP的对应表），若都没找到，则去本地域名服务器中查找，本地域名服务器收到客户端的请求后，如果缓存⾥的表格能找到 XXX，则它直接返回 IP 地址。如果没有，本地 DNS 会去问它的根域名服务器，再去问顶级域名服务区，再去问权威域名服务器，返回对应IP地址XXX

2. **TCP连接（三次握手）**
3. **发起HTTP请求**
4. **服务器响应 http 请求，客户端得到 html 代码。服务器 web 应用程序收到 http 请求后，就开始处理请求，处理之后就返回给浏览器 html 文件**
5. **浏览器解析html代码，并请求html中的静态资源**
6. **浏览器对页面进行渲染，并呈现给用户**

### 为什么DNS使用UDP而不是TCP？

<font color='red'>DNS在进行区域传输的时候使用TCP，普通的查询使用UDP。</font>

**采用TCP传输，则域名解析时间为：**DNS域名解析时间 = TCP连接时间 + DNS交易时间

**采用UDP传输，则域名解析时间为：**DNS域名解析时间 = DNS交易时间

很显然，采用UDP传输，DNS域名解析时间更小

- 使用UDP传输是由于效率高，传输小于等于512字节报文；使用TCP传输是由于可以传输大于512字节报文。
- 使用签名是保证数据来源的可靠性。
- 使用TCP传输，同样是可以传输证书链、签名。
- 使用UDP同样可以传输远远大于576字节的数据，只要应用程序可以标识数据ID。

### 什么是SYN flooding?如何防御？

**SYN flooding：攻击者可以在短时间内发送大量的伪SYN包，占用服务器的TCB（传输控制块）队列资源，致使正常用户无法连接。**

<font color='blue'>SYN cookie</font>机制的想法是在服务器**仅收到SYN之后根本不分配资源;仅当服务器收到最终的ACK数据包时才分配资源，这解决了SYN泛洪攻击问题。**

### ping的原理？

ping是基于<font color='blue'>ICMP（互联网控制报文协议）</font>协议工作的，<font color='blue'>ICMP报文是封装在IP包里面的，工作在网络层</font>。

ICMP主要功能：**确认 IP 包是否成功送达目标地址、报告发送过程中 IP 包被废弃的原因和改善网络设置等，分为两种类型——查询报文类型和差错报文类型。**

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/c86ca9624f59b5e798441f7a614fb7c7.webp">

**ICMP工作流程：**

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/3a727f48ee82d5c9a974be909c217ad2.webp">

### Cookie和Session的区别？（百度测开）

1. Cookie 保存在客户端（浏览器），Session 保存在服务器端
2. Cookie 可设置为长时间保持，比如我们经常使用的默认登录功能，Session 一般失效时间较短，客户端关闭或者 Session 超时都会失效
3. Cookie 存储在客户端，比较容易遭到不法获取，早期有人将用户的登录名和密码存储在 Cookie 中导致信息被窃取；Session 存储在服务端，安全性相对 Cookie 要好一些
4. 单个 Cookie 保存的数据不能超过 4K，Session 可存储数据远高于 Cookie
5. Cookie 只能保存 ASCII，Session 可以存任意数据类型

### cookie失效了session还能用吗？（携程测开）

一般默认情况下，在会话中，`服务器存储 session 的 sessionid 是通过 cookie 存到浏览器里`。

**<font color='red'>如果浏览器禁用了 cookie，浏览器请求服务器无法携带 sessionid，服务器无法识别请求中的用户身份，session失效。</font>**

但是可以通过其他方法在禁用 cookie 的情况下，可以继续使用session。

- **通过url重写，把 sessionid 作为参数追加的原 url 中，后续的浏览器与服务器交互中携带 sessionid 参数**
- **服务器的返回数据中包含 sessionid，浏览器发送请求时，携带 sessionid 参数**
- **通过 Http 协议其他 header 字段，服务器每次返回时设置该 header 字段信息，浏览器中 js 读取该 header 字段，请求服务器时，js设置携带该 header 字段**

### TCP粘包和拆包问题？

**为什么会发生TCP粘包和拆包？**

① 发送⽅写⼊的数据⼤于套接字缓冲区的⼤⼩，此时将发⽣拆包。

② 发送⽅写⼊的数据⼩于套接字缓冲区⼤⼩，由于 TCP 默认使⽤ Nagle 算法，只有当收到⼀个确认后，才将分组发送给对端，当发送⽅收集了多个较⼩的分组，就会⼀起发送给对端，这将会发⽣粘包。

③ 进⾏ MSS （最⼤报⽂⻓度）⼤⼩的 TCP 分段，当 TCP 报⽂的数据部分⼤于 MSS 的时候将发⽣拆包。

④ 发送⽅发送的数据太快，接收⽅处理数据的速度赶不上发送端的速度，将发⽣粘包。

**常见的解决方法**

① 在消息的头部添加消息⻓度字段，服务端获取消息头的时候解析消息⻓度，然后向后读取相应⻓度的内容。

② 固定消息数据的⻓度，服务端每次读取既定⻓度的内容作为⼀条完整消息，当消息不够⻓时，空位补上固定字符。但是该⽅法会浪费⽹络资源。

③ 设置消息边界，也可以理解为分隔符，服务端从数据流中按消息边界分离出消息内容，⼀般使⽤换⾏符。

### 如何让UDP的传输变得可靠？

- **确认机制**，UDP要想可靠，就要接收方收到UDP之后回复个确认包
- **超时重传**，发送方有个机制，收不到确认包就要重新发送，每个包有递增的序号，接收方发现中间丢了包就要发重传请求
- **滑动窗口**，当网络太差时候频繁丢包，防止越丢包越重传的恶性循环，要有个发送窗口的限制，发送窗口的大小根据网络传输情况调整，调整算法要有一定自适应性

### 什么是SQL注入，如何避免？

SQL 注入就是在用户输入的字符串中加入 SQL 语句，如果在设计不良的程序中忽略了检查，那么这些注入进去的 SQL 语句就会被数据库服务器误认为是正常的 SQL 语句而运行，攻击者就可以执行计划外的命令或访问未被授权的数据。

**如何做到SQL注入？**

- 恶意拼接查询
- 利用注释执行非法命令
- 传入非法参数
- 添加额外条件

**如何避免SQL注入？**

- 限制数据库权限，给用户提供仅仅能够满足其工作的最低权限
- 对进入数据库的特殊字符（’”\尖括号&*;等）转义处理
- 提供参数化查询接口，不要直接使用原生SQL

## 操作系统

### 内核态和用户态的区别和切换？（用友Java）

#### 区别

- 内核态与用户态是操作系统的两种运行级别，当程序运行在3级特权级上时，就可以称之为运行在用户态。**因为这是最低特权级，是普通的用户进程运行的特权级，大部分用户直接面对的程序都是运行在用户态；**

- 当程序运行在0级特权级上时，就可以称之为运行在内核态。

- 运行在用户态下的程序不能直接访问操作系统内核数据结构和程序。当我们在系统中执行一个程序时，大部分时间是运行在用户态下的，在其需要操作系统帮助完成某些它没有权力和能力完成的工作时就会切换到内核态（比如操作硬件）。

- 这两种状态的主要差别是

  > - 处于用户态执行时，进程所能访问的内存空间和对象受到限制，其所处于占有的处理器是可被抢占的
  > - 处于内核态执行时，则能访问所有的内存空间和对象，且所占有的处理器是不允许被抢占的。

#### 切换

<img src="https://segmentfault.com/img/bVbHtam/view">

### kill -9中的-9是什么意思？

kill和kill -9，两个命令在linux中都有杀死进程的效果，执行kill命令，系统会发送一个SIGTERM信号给对应的程序。当程序接收到该signal信号后，有以下几种情况：
    （1）程序立刻停止
    （2）当程序释放相应资源后再停止
    （3）程序可能仍然继续运行

大部分程序接收到`SIGTERM`信号后，会先释放自己的资源，然后再停止。但是也有程序可能接收信号后，做一些其他的事情（如果程序正在等待IO，可能就不会立马做出响应，我在使用wkhtmltopdf转pdf的项目中遇到这现象），也就是说，SIGTERM多半是会被阻塞的。

kill -9命令，系统给对应程序发送的信号是`SIGKILL`，即exit。`exit信号不会被系统阻塞`，所以kill -9能顺利杀掉进程

### 线程和协程的区别？

- 线程和进程都是同步机制，而协程是异步机制。
- 线程是抢占式，而协程是非抢占式的。需要用户释放使用权切换到其他协程，因此同一时间其实只有一个协程拥有运行权，相当于单线程的能力。
- 一个线程可以有多个协程，一个进程也可以有多个协程。
- 协程不被操作系统内核管理，而完全是由程序控制。线程是被分割的CPU资源，协程是组织好的代码流程，线程是协程的资源。但协程不会直接使用线程，协程直接利用的是执行器关联任意线程或线程池。
- 协程能保留上一次调用时的状态。

### 并发和并行的区别？

- 并发就是在一段时间内，多个任务都会被处理；但在某一时刻，只有一个任务在执行。单核处理器可以做到并发。比如有两个进程A和B，A运行一个时间片之后，切换到B，B运行一个时间片之后又切换到A。因为切换速度足够快，所以宏观上表现为在一段时间内能同时运行多个程序。
- 并行就是在同一时刻，有多个任务在执行。这个需要多核处理器才能完成，在微观上就能同时执行多条指令，不同的程序被放到不同的处理器上运行，这个是物理上的多个进程同时进行。

### 进程有那些状态？状态的切换？（用友Java）

进程一共有5种状态，分别是创建、就绪、运行（执行）、终止、阻塞

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/jinchengzhuangtai.png">

- 运行状态就是进程正在CPU上运行。在单处理机环境下，每一时刻最多只有一个进程处于运行状态。 
- 就绪状态就是说进程已处于准备运行的状态，即进程获得了除CPU之外的一切所需资源，一旦得到CPU即可运行。 
- 阻塞状态就是进程正在等待某一事件而暂停运行，比如等待某资源为可用或等待I/O完成。即使CPU空闲，该进程也不能运行。 

> **<font color='blue'>运行态→阻塞态：</font>**往往是由于等待外设，等待主存等资源分配或等待人工干预而引起的。
>
> **<font color='blue'>阻塞态→就绪态：</font>**则是等待的条件已满足，只需分配到处理器后就能运行。
>
> **<font color='blue'>运行态→就绪态：</font>**不是由于自身原因，而是由外界原因使运行状态的进程让出处理器，这时候就变成就
> 绪态。例如时间片用完，或有更高优先级的进程来抢占处理器等。
>
> **<font color='blue'>就绪态→运行态：</font>**系统按某种策略选中就绪队列中的一个进程占用处理器，此时就变成了运行态。

### 进程间通信方式？（百度测开）

#### 管道（有名和匿名）

**管道：**管道这种通讯方式有两种限制，一是半双工的通信，数据只能单向流动，二是只能在具有亲缘关系的进程间使用。进程的亲缘关系通常是指父子进程关系。

管道可以分为两类：`匿名管道`和`命名管道`。匿名管道是单向的，只能在有亲缘关系的进程间通信；命名管道以磁盘文件的方式存在，可以实现本机任意两个进程通信。

#### 信号

**信号 ：**信号是一种比较复杂的通信方式，信号可以在任何时候发给某一进程，而无需知道该进程的状态。<font color='red'>信号是进程间通信机制中唯⼀的**异步通信机制**，因为可以在任何时候发送信号给某⼀进程。</font>

Linux系统中常用信号：

> （1）SIGHUP：用户从终端注销，所有已启动进程都将收到该进程。系统缺省状态下对该信号的处理是终止进程。
> 
>（2）SIGINT：程序终止信号。程序运行过程中，按Ctrl+C 键将产生该信号。
> 
>（3）SIGQUIT：程序退出信号。程序运行过程中，按Ctrl+\\ 键将产生该信号。
> 
>（4）SIGBUS和SIGSEGV：进程访问非法地址。
> 
>（5）SIGFPE：运算中出现致命错误，如除零操作、数据溢出等。
> 
>（6）SIGKILL：用户终止进程执行信号。shell下执行kill -9 发送该信号。
> 
>（7）SIGTERM：结束进程信号。shell下执行kill 进程pid 发送该信号。
> 
>（8）SIGALRM：定时器信号。
> 
>（9）SIGCLD：子进程退出信号。如果其父进程没有忽略该信号也没有处理该信号，则子进程退出后将形成僵尸进程。

#### 信号量

**信号量：**信号量是一个计数器，可以用来控制多个进程对共享资源的访问。它常作为一种锁机制，防止某进程正在访问共享资源时，其他进程也访问该资源。因此，主要作为进程间以及同一进程内不同线程之间的同步手段。

#### 消息队列

**消息队列：**消息队列是消息的链接表，包括Posix消息队列和System V消息队列。有足够权限的进程可以向队列中添加消息，被赋予读权限的进程则可以读走队列中的消息。消息队列克服了信号承载信息量少，管道只能承载无格式字节流以及缓冲区大小受限等缺点。

#### 共享内存

**共享内存：**共享内存就是映射一段能被其他进程所访问的内存，这段共享内存由一个进程创建，但多个进程都可以访问。共享内存是最快的 IPC 方式，它是针对其他进程间通信方式运行效率低而专门设计的。它往往与其他通信机制，如信号量，配合使用，来实现进程间的同步和通信。

#### Socket

Socket：与其他通信机制不同的是，它可用于不同机器间的进程通信。

### 多进程和多线程区别？（百度测开）

#### 多进程

在同一个时间里，同一个计算机系统中如果允许两个或两个以上的进程处于运行状态，这便是多任务。现代的操作系统几乎都是多任务操作系统，能够同时管理多个进程的运行。**多进程不能共享全局变量，当使用全局变量的时候势必会造成，race condition。**

#### 多线程

在基于线程的多任务的环境中，所有进程至少有一个线程，但是它们可以具有多个任务。这意味着单个程序可以并发执行两个或者多个任务。**同一进程的所有线程是共享同一内存，多线程则可以共享全局变量。**

#### 优缺点

- **多进程优点：**

1、每个进程互相独立，不影响主程序的稳定性，子进程崩溃没关系；

2、通过增加CPU，就可以容易扩充性能；

3、可以尽量减少线程加锁/解锁的影响，极大提高性能，就算是线程运行的模块算法效率低也没关系；

4、每个子进程都有2GB地址空间和相关资源，总体能够达到的性能上限非常大。

- **多进程缺点：**

1、逻辑控制复杂，需要和主程序交互；

2、需要跨进程边界，如果有大数据量传送，就不太好，适合小数据量传送、密集运算 多进程调度开销比较大；

3、最好是多进程和多线程结合，即根据实际的需要，每个CPU开启一个子进程，这个子进程开启多线程可以为若干同类型的数据进行处理。当然你也可以利用多线程+多CPU+轮询方式来解决问题……

- **多线程的优点：**

1、无需跨进程边界；

2、程序逻辑和控制方式简单；

3、所有线程可以直接共享内存和变量等；

4、线程方式消耗的总资源比进程方式好。

- **多线程缺点：**

1、每个线程与主程序共用地址空间，受限于2GB地址空间；

2、线程之间的同步和加锁控制比较麻烦；

3、一个线程的崩溃可能影响到整个程序的稳定性；

4、到达一定的线程数程度后，即使再增加CPU也无法提高性能，例如Windows Server 2003，大约是1500个左右的线程数就快到极限了（线程堆栈设定为1M），如果设定线程堆栈为2M，还达不到1500个线程总数；

5、线程能够提高的总性能有限，而且线程多了之后，线程本身的调度也是一个麻烦事儿，需要消耗较多的CPU。

#### 使用场景

**<font color='blue'>多进程CPU密集型，多线程I/O密集型</font>**

多进程模型的优势是CPU

多线程模型主要优势为线程间切换代价较小，因此适用于I/O密集型的工作场景，因此I/O密集型的工作场景经常会由于I/O阻塞导致频繁的切换线程。同时，多线程模型也适用于单机多核分布式场景。

### 计算机管理内存？（分页和分段）

#### 分页

<font color='blue'>把内存空间划分为大小相等且固定的块，作为主存的基本单位。因为程序数据存储在不同的页面中，
而页面又离散的分布在内存中，因此需要一个页表来记录映射关系，以实现从页号到物理块号的映射。</font>

访问分页系统中内存数据需要两次的内存访问 (一次是从内存中访问页表，从中找到指定的物理块号，加上页内偏移得到实际物理地址；第二次就是根据第一次得到的物理地址访问内存取出数据)。

#### 分段

<font color='blue'>分页是为了提高内存利用率，而分段是为了满足程序员在编写代码的时候的一些逻辑需求(比如数据共享，数据保护，动态链接等)。</font>

分段内存管理当中，地址是二维的，一维是段号，二维是段内地址；其中每个段的长度是不一样的，而且每个段内部都是从0开始编址的。由于分段管理中，每个段内部是连续内存分配，但是段和段之间是离散分配的，因此也存在一个逻辑地址到物理地址的映射关系，相应的就是段表机制。

#### 分页和分段的区别

- 分页对程序员是透明的，但是分段需要程序员显式划分每个段。 
- 分页的地址空间是一维地址空间，分段是二维的。 
- 页的大小不可变，段的大小可以动态改变。 
- 分页主要用于实现虚拟内存，从而获得更大的地址空间；分段主要是为了使程序和数据可以被划分为逻辑上独立的地址空间并且有助于共享和保护。

### 什么情况下会造成多线程上下文切换？

一个线程的状态由 RUNNING 转为 BLOCKED ，再由 BLOCKED 转为 RUNNABLE ，然后再被调度器选中执行，这就是一个上下文切换的过程。

当一个线程从 RUNNING 状态转为 BLOCKED 状态时，我们称为一个线程的暂停，线程暂停被切出之后，操作系统会保存相应的上下文，以便这个线程稍后再次进入 RUNNABLE 状态时能够在之前执行进度的基础上继续执行。

当一个线程从 BLOCKED 状态进入到 RUNNABLE 状态时，我们称为一个线程的唤醒，此时线程将获取上次保存的上下文继续完成执行，多线程的上下文切换实际上就是由多线程两个运行状态的互相切换导致的。

- 一种是程序本身触发的切换，这种我们称为自发性上下文切换。自发性上下文切换指线程由 Java 程序调用导致切出，在多线程编程中，执行调用以下方法或关键字，常常就会引发自发性上下文切换。
  - **sleep()、wait()、yield()、join()、park()、synchronized、lock**
- 另一种是由系统或者虚拟机诱发的非自发性上下文切换。常见的有：线程被分配的时间片用完，虚拟机垃圾回收导致或者执行优先级的问题导致。GC可能导致STW(stop-the-world)，这是一种线程暂停的行为。

### 死锁的必要条件、预防方法、检测？（用友Java、百度测开）

<font color='red'>产生：</font>多个线程同时被阻塞，它们中的一个或者全部在等待某个资源被释放或者是都是处于等待而无法被唤醒时，由于线程被无限地阻塞，因此程序不能正常终止。

<font color='red'>条件：</font>

1. 互斥，资源一个时刻只能由一个线程占用
2. 不可剥夺，分配给一个进程的资源不能强制性的被抢占
3. 请求与保持，已经得到了某个资源的进程可以请求其他新的资源
4. 循环等待，有两个或两个以上的进程组成一条环路，该环路种每个进程都在等待下一个进程释放资源

<font color='red'>预防：</font>

1. 无法破坏互斥条件，临界资源需要互斥访问
2. 破坏请求与保持条件，规定所有进程在开始执行前请求所需的所有资源
3. 破坏不可剥夺，，当一个进程占有一个独占性资源而无法满足时，主动释放占有的资源
4. 破坏环路等待，给资源统一编号，进程按照编号顺序请求资源

<font color='red'>检测：</font>

- **画出资源分配图**，系统死锁，可利用资源分配图来描述。如下图所示，用长方形代表一个进程，用框代表一类资源。由于一种类型的资源可能有多个，用框中的一个点代表一类资源中的一个资源。从进程到资源的有向边叫请求边，表示该进程申请一个单位的该类资源；从资源到进程的边叫分配边，表示该类资源已经有一个资源被分配给了该进程。
- 简化资源分配图
- **使用死锁定理判断**
  - 如果资源分配图中没有环路，则系统没有死锁； 
  - 如果资源分配图中出现了环路，则系统可能有死锁。 

### 进程和线程开销？

一个程序进行起来后，会使用很多资源，比如使用寄存器，内存，文件等。每当切换进程时，必须要考虑保存当前进程的状态。状态包括存放在内存中的程序的代码和数据，它的栈、通用目的寄存器的内容、程序计数器、环境变量以及打开的文件描述符的集合，这个状态叫做上下文（Context）。可见，想要切换进程，保存的状态还不少。

线程是运行在进程上下文中的逻辑流，简单说，线程可以理解为一个方法(Java)或函数（C），这个线程可以独立完成一项任务。同样线程有自己的上下文，包括唯一的整数线程ID， 栈、栈指针、程序计数器、通用目的寄存器和条件码。可以理解为线程上下文是进程上下文的子集。

### 为什么进程上下文切换比线程上下文切换代价高?

**进程切换分两步：**

- 切换页目录以使用新的地址空间
- 切换内核栈和硬件上下文

对于linux来说，线程和进程的最大区别就在于地址空间，对于线程切换，第1步是不需要做的，第2是进程和线程切换都要做的

**切换的性能消耗：**

1. 线程上下文切换和进程上下问切换一个最主要的区别是线程的切换虚拟内存空间依然是相同的，但是进程切换是不同的。这两种上下文切换的处理都是通过操作系统内核来完成的。内核的这种切换过程伴随的最显著的性能损耗是将寄存器中的内容切换出。
2. 另外一个隐藏的损耗是`上下文的切换会扰乱处理器的缓存机制`。简单的说，一旦去切换上下文，处理器中所有已经缓存的内存地址一瞬间都作废了。还有一个显著的区别是当你改变虚拟内存空间的时候，处理的页表缓冲（processor's Translation Lookaside Buffer (TLB)）或者相当的神马东西会被全部刷新，这将导致内存的访问在一段时间内相当的低效，但是在线程的切换中，不会出现这个问题。

### 什么是虚拟内存？

虚拟内存就是说，让物理内存扩充成更大的逻辑内存，从而让程序获得更多的可用内存。虚拟内存使用部分加载的技术，让一个进程或者资源的某些页面加载进内存，从而能够加载更多的进程，甚至能加载比内存大的进程，这样看起来好像内存变大了，这部分内存其实包含了磁盘或者硬盘，并且就叫做虚拟内存。

### 为什么虚拟地址空间切换会比较耗时？

进程都有自己的虚拟地址空间，把虚拟地址转换为物理地址需要查找页表，页表查找是一个很慢的过程，因此通常使用Cache来缓存常用的地址映射，这样可以加速页表查找，这个Cache就是TLB（translation Lookaside Buffer，TLB本质上就是一个Cache，是用来加速页表查找的）。

由于每个进程都有自己的虚拟地址空间，那么显然每个进程都有自己的页表，那么当进程切换后页表也要进行切换，页表切换后TLB就失效了，Cache失效导致命中率降低，那么虚拟地址转换为物理地址就会变慢，表现出来的就是程序运行会变慢，而线程切换则不会导致TLB失效，因为线程无需切换地址空间，因此我们通常说线程切换要比较进程切换块，原因就在这里。

### epoll相比于select的优势？

select实现多路复用的方式是，将已经连接的socket都放到一个`文件描述符集合`，然后调用`select函数`将文件描述符集合`拷贝`到内核里，让内核来检查是否有网络事件产生，检查方式很粗暴，就是通过`遍历文件描述符集合`的方式，当检查到有事件产生后，将次socket标记为可读或可写，接着再把整个文件描述符集合`拷贝`回用户态里，然后用户态还需要再通过`遍历`的方式找到可读或可写的socket，然后对其处理。

对于select这种方式，需要进行**2次遍历文件描述符集合**，一次是在内核态里，一次是在用户态里，而且还会产生**2次拷贝**，先从用户空间拷贝到内核空间，再从内核空间拷贝到用户空间中。

select 使⽤固定⻓度的 BitsMap，表示⽂件描述符集合，⽽且所⽀持的⽂件描述符的个数是有限制的，在 Linux 系统中，由内核中的 FD_SETSIZE 限制， 默认最⼤值为 1024 ，只能监听 0~1023 的⽂件描述符。

poll 不再⽤ BitsMap 来存储所关注的⽂件描述符，取⽽代之⽤动态数组，以链表形式来组织，突破了 select 的⽂件描述符个数限制，当然还会受到系统⽂件描述符限制。

但是 poll 和 select 并没有太⼤的本质区别，**都是使⽤「线性结构」存储进程关注的 Socket 集合，因此都需要遍历⽂件描述符集合来找到可读或可写的 Socket，时间复杂度为 O(n)，⽽且也需要在⽤户态与内核态之间拷⻉⽂件描述符集合**，这种⽅式随着并发数上来，性能的损耗会呈指数级增⻓。

----------

**<font color='blue'>epoll通过两个方面，很好的解决了select/poll的问题</font>**

**第⼀点，**epoll 在内核⾥使⽤**红⿊树来跟踪进程所有待检测的⽂件描述字**，把需要监控的 socket 通过 
**epoll_ctl() 函数**加⼊内核中的红⿊树⾥，红⿊树是个⾼效的数据结构，增删查⼀般时间复杂度是 **O(logn)** ，通过对这棵⿊红树进⾏操作，这样就不需要像 select/poll 每次操作时都传⼊整个 socket 集合，只需要传⼊⼀个待检测的 socket，减少了内核和⽤户空间⼤量的数据拷⻉和内存分配。

**第⼆点，** epoll 使⽤事件驱动的机制，内核里**维护了⼀个链表来记录就绪事件**，当某个 socket 有事件发⽣时，通过回调函数内核会将其加⼊到这个就绪事件列表中，当用户调用 **epoll_wait() 函数**时，只会返回有事件发⽣的⽂件描述符的个数，不需要像 select/poll 那样轮询扫描整个 socket 集合，⼤⼤提⾼了检测的效率。

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/epoll.png">

epoll 的⽅式即使监听的 Socket 数量越多的时候，效率不会⼤幅度降低，能够同时监听的 Socket 的数⽬也⾮常的多了，上限就为系统定义的进程打开的最⼤⽂件描述符个数。因⽽，**epoll 被称为解决 C10K 问题的利器。**

epoll ⽀持两种事件触发模式，分别是**边缘触发（edge-triggered，ET）**和**⽔平触发（level-triggered，LT）**。

- 使⽤边缘触发模式时，当被监控的 Socket 描述符上有可读事件发⽣时，**服务器端只会从 epoll_wait** 
  **中苏醒⼀次**，即使进程没有调⽤ read 函数从内核读取数据，也依然只苏醒⼀次，因此我们程序要保证⼀次性将内核缓冲区的数据读取完；
- 使用水平触发模式时，当被监控的 Socket 上有可读事件发⽣时，**服务器端不断地从 epoll_wait 中苏醒，直到内核缓冲区数据被 read 函数读完才结束**，⽬的是告诉我们有数据需要读取；

## Linux

### Linux全局替换文件字符

```shell
sed -i "s/abc/haha/g" ./Dockerfile
将当前目录下的Dockerfile文件里abc都替换为haha
```

### Linux查找文件中包含某字符的行数

```shell
find ./Dockerfile | xargs cat | grep ap | wc -l
显示在Dockerfile文件里包含ap这个字符的行数
```

### Linux查看某个进程文件的启动位置

```shell
ps -ef | grep shutdown
找进程id
cd /proc/进程id
看软连接cwd->XXXX
```

### Linux按照文件大小排序？

```shell
# 文件夹
du -s ./* | sort -nr
---------------------------
1> 要显示一个目录树及其每个子树的磁盘使用情况
du /home/linux
这在/home/linux目录及其每个子目录中显示了磁盘块数。

2> 要通过以1024字节为单位显示一个目录树及其每个子树的磁盘使用情况
du -k /home/linux
这在/home/linux目录及其每个子目录中显示了 1024 字节磁盘块数。

3> 以MB为单位显示一个目录树及其每个子树的磁盘使用情况
du -m /home/linux
这在/home/linux目录及其每个子目录中显示了 MB 磁盘块数。

4> 以GB为单位显示一个目录树及其每个子树的磁盘使用情况
du -g /home/linux
这在/home/linux目录及其每个子目录中显示了 GB 磁盘块数。

5>查看当前目录下所有目录以及子目录的大小：
du -h .
“.”代表当前目录下。也可以换成一个明确的路径
-h表示用K、M、G的人性化形式显示

6>查看当前目录下user目录的大小，并不想看其他目录以及其子目录：
du -sh user
-s表示总结的意思，即只列出一个总结的值
du -h --max-depth=0 user
--max-depth=n表示只深入到第n层目录，此处设置为0，即表示不深入到子目录。

7>列出user目录及其子目录下所有目录和文件的大小：
du -ah user
-a表示包括目录和文件

8>列出当前目录中的目录名不包括xyz字符串的目录的大小：
du -h --exclude='*xyz*'


9>想在一个屏幕下列出更多的关于user目录及子目录大小的信息：
du -0h user
-0（杠零）表示每列出一个目录的信息，不换行，而是直接输出下一个目录的信息。

10>只显示一个目录树的全部磁盘使用情况
du -s /home/linux
```

### Linxu查看文件总行数？查看倒数10行？是否包含某个字符串？

```shell
# 查看文件总行数
wc -l ./DockerFile
# 查看倒数10行和前10行
tail -n 10 ./DockerFile
head -n 10 ./DockerFile
# 查看文件是否包含某个字符串
grep --color=auto -rns "apk" ./Dockerfile
```

### Linux显示进程和线程？

```shell
# 查找进程
ps -ef | grep XXX
# 不显示本身进程
ps -aux | grep XXX
```

### Linux查看端口号？

```shell
netstat -nlp | grep 端口号
```

## 设计模式

### 设计模式几大基本原则？

#### 单依职责原则

就是一个类而言，应该仅有一个引起它变化的原因。简单来说，一个类中应该是一组相关性很高的函数、数据的封装。

比如当要做一个图片加载器的时候，不应该把所有的东西都写在一个类中，应该各个功能独立出来，可以分成图片加载功能和缓存功能等模块，这样类中的代码逻辑清晰可读性、可扩展性和可维护性会大大提高。

#### 开闭原则

软件中的对象（类、模块、函数等）应该对于扩展是开放的，对于修改是封闭的。在软件的生命周期内，因为变化、升级和维护等原因需要对软件原有代码进行修改时，可能会讲错误引入原本已经经过测试的旧代码中，破坏原有系统。因此，当软件需要变化时，我们应该尽量通过扩展的方式来实现变化，而不是通过修改已有的代码来实现。

#### 里式替换原则

所有引用基类的地方必须能透明地使用其子类对象。面向对象的语言三大特点是：继承、封装、多态，里式替换原则就是依赖于继承、多态这个两大特点。简单说就是只要父类出现的地方子类就可以出现，而且替换为子类也不会产生任何错误或异常，或者可能根本就不需要知道父类还是子类。但是反过来就不行了，有子类出现的地方，父类未必就能适应。

#### 依赖倒置原则

其指出了一种特点的解耦形式，使得高层次的模块不依赖于低层次的模块的实现细节的目的，依赖模块被颠倒了。
 几个关键点：
 （1）高层模块不应该依赖底层模块，两者都应该依赖其抽象。
 （2）抽象不依赖于细节。
 （3）细节应该依赖抽象。

#### 接口隔离原则

客户端不应该依赖它不需要的接口。另一种定义是：类之间的依赖关系应该建立在最小的接口上。接口隔离原则将非常庞大、臃肿的接口拆分成更小和更具体的接口，这样客户端将会只需知道他们感兴趣的方法。接口隔离原则的目的是系统解开耦合，从而容易重构、更改和重新部署。

#### 迪米特原则

也称为最小知识原则。一个对象应该对其他对象有最少的了解。通俗的讲，一个类应该对自己需要耦合或调用的类知道得最小，类的内部如何实现与调用者或者依赖者没关系，调用者或者依赖者只需要知道它需要的方法即可，其他的可一概不管。类与类之间关系越密切，耦合越大，当一个类方法改变时，对另一个类的影响也越大。

### 单例模式Double Check 双重校验锁实现方式为什么要加volatile关键字？

```java
public class Singleton {
    private static volatile Singleton singleton = null;      //声明singleton时必须要加volatile关键字
    private Singleton() {}
    public static Singleton getInstance(){
        //第一次校验singleton是否为空
        if(singleton==null){                                 //1
            synchronized (Singleton.class){                  //2
                //第二次校验singleton是否为空                  
                if(singleton==null){                         //3
                    singleton = new Singleton();             //4
                }
            }
        }
        return singleton;                                    //5
    }
```

- **第一个作用**

因为 `singleton = new Singleton()` 这句话可以分为三步：

1. 为 singleton 分配内存空间；
2. 初始化 singleton；
3. 将 singleton 指向分配的内存空间；

但是由于JVM具有指令重排的特性，执行顺序有可能变成 1-3-2。 指令重排在单线程下不会出现问题，但是在多线程下会导致一个线程获得一个未初始化的实例。例如：线程Thread1先执行了1、3，此时singleton已经指向了分配的内存空间，所以不为null，若这时有Thread2调用 getInstance() 在` //1 处`发现 singleton 不为空，因此直接跳到 `//5 处 `return singleton， 但是此时Thread1并未对 singleton 进行初始化，那么返回的singleton是未被完整创建的singleton。而使用 volatile 会禁止JVM指令重排，从而保证在多线程下也能正常执行。

- **第二个作用**

volatile关键字保证了变量的可见性，被volatile关键字修饰的变量有如下好处：

1. 在当前线程的工作内存中修改之后会立即更新回主内存；
2. 在其他线程从自己的工作内存中读取该变量值之前，会先从主内存中更新最新的值到各自的工作内存。

因此当进入synchronized同步代码块的线程成功创建了实例，并释放了锁之后，等待在` //2 处`的的某个线程拿到锁进入同步代码块，并进行第二次if判断时，读取到的singleton已经成功创建实例，就不会再创建第二个实例，而是直接到` //5 `返回创建好的singleton。

### 如何破坏单例模式？

#### 通过反射破坏

```java
//Double check
public class Singleton{
    private volatile static Singleton singleton;
    private Singleton(){}
    public static Singleton getSingleton() {
        if (singleton == null) {
            synchronized (Singleton.class) {
                if (singleton == null) {
                    singleton = new Singleton();
                }
            }
        }
        return singleton;
    }
}
//--------破坏+测试方法---------
public class SingletonTests {
    public static void main(String[] args) throws Exception {
        Singleton singleton = Singleton.getSingleton();
        Singleton singleton1=Singleton.getSingleton();
        Constructor constructor=Singleton.class.getDeclaredConstructor(null);
        constructor.setAccessible(true);
        Singleton singleton2 =(Singleton) constructor.newInstance(null);
        System.out.println(singleton.hashCode());
        System.out.println(singleton1.hashCode());
        System.out.println(singleton2.hashCode());
    }
}
//-------结果-------
692404036
692404036
1554874502
//----------如何防止反射破坏呢？-------
//防止调用私有构造器，也就是调用一次之后，再调用就报错，抛出异常
    public class Singleton {
        private static int num = 0;

        private volatile static Singleton singleton;

        private Singleton() {
            synchronized (Singleton.class) {
                if (num == 0) {
                    num++;
                } else {
                    throw new RuntimeException("Don't use this method");
                }
            }
        }

    public static Singleton getSingleton() {
        if (singleton == null) {
            synchronized (Singleton.class) {
                if (singleton == null) {
                    singleton = new Singleton();
                }
            }
        }
        return singleton;
    }
}
```

#### 实现cloneable接口

如果单例对象已经将构造方法声明成为`private`，并且重写了构造方法，那么暂时无法调用到构造方法。但是还有一种情况，那就是拷贝，拷贝的时候是不需要经过构造方法的。但是要想拷贝，必须实现`Clonable`方法，而且需要重写`clone`方法。

```java
public class Singleton implements Cloneable {
    private static int num = 0;

    private volatile static Singleton singleton;

    private Singleton() {
        synchronized (Singleton.class) {
            if (num == 0) {
                num++;
            } else {
                throw new RuntimeException("Don't use this method");
            }
        }
    }

    public static Singleton getSingleton() {
        if (singleton == null) {
            synchronized (Singleton.class) {
                if (singleton == null) {
                    singleton = new Singleton();
                }
            }
        }
        return singleton;
    }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
//-------------------测试代码如下-----------------------
public class SingletonTests {
    public static void main(String[] args) throws Exception {
        Singleton singleton1=Singleton.getSingleton();
        System.out.println(singleton1.hashCode());
        Singleton singleton2 = (Singleton) singleton1.clone();
        System.out.println(singleton2.hashCode());
    }
}
```

#### 序列化破坏单例模式

序列化，实际上和`clone`差不多，但是不一样的地方在于我们很多对象都是必须实现序列化接口的，但是实现了序列化接口之后，对单例的保证有什么风险呢？`风险就是序列化之后，再反序列化回来，对象的内容是一样的，但是对象却不是同一个对象了`。

```java
public class Singleton implements Serializable {
    private static int num = 0;

    private volatile static Singleton singleton;

    private Singleton() {
        synchronized (Singleton.class) {
            if (num == 0) {
                num++;
            } else {
                throw new RuntimeException("Don't use this method");
            }
        }
    }

    public static Singleton getSingleton() {
        if (singleton == null) {
            synchronized (Singleton.class) {
                if (singleton == null) {
                    singleton = new Singleton();
                }
            }
        }
        return singleton;
    }
}
//-------------------测试代码如下--------------------
public class SingletonTests {
    public static void main(String[] args) throws Exception {

        Singleton singleton1 = Singleton.getSingleton();
        ObjectOutputStream objectOutputStream = new ObjectOutputStream(new FileOutputStream("file"));
        objectOutputStream.writeObject(singleton1);
        File file = new File("tempFile");
        ObjectInputStream objectInputStream = new ObjectInputStream(new FileInputStream(file));
        Singleton singleton2 = (Singleton) objectInputStream.readObject();
        System.out.println(singleton1.hashCode());
        System.out.println(singleton2.hashCode());
    }
}
```

### 枚举是如何防止反射破坏单例模式的？

单例模式三个主要特点：1、构造方法私有化；2、实例化的变量引用私有化；3、获取实例的方法共有

枚举Enum是个抽象类，其实一旦一个类声明为枚举，实际上就是继承了Enum，所以会有（String.class,int.class）的构造器。既然是可以获取到父类Enum的构造器，那你也许会说刚才我的反射是因为自身的类没有无参构造方法才导致的异常，并不能说单例枚举避免了反射攻击。

### 单例模式Double Check为什么需要两次if判断？

<img src="https://img-blog.csdnimg.cn/20191111103744108.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zODk4MzkyOQ==,size_16,color_FFFFFF,t_70">

<font color='red'>内层判断：</font>**如果内层不加if判断，就会实例化多次**，这是显而易见的，这就违背了单例模式的单例二字。这个校验是防止二次创建实例，假如有一种情况，当singleton还未被创建时，线程t1调用getInstance方法，由于第一次判断singleton==null，此时线程t1准备继续执行，但是由于资源被线程t2抢占了，此时t2页调用getInstance方法，同样的，由于singleton并没有实例化，t2同样可以通过第一个if，然后继续往下执行，同步代码块，第二个if也通过，然后t2线程创建了一个实例singleton。此时t2线程完成任务，资源又回到t1线程，t1此时也进入同步代码块，如果没有这个第二个if，那么，t1就也会创建一个singleton实例，那么，就会出现创建多个实例的情况，但是加上第二个if，就可以完全避免这个多线程导致多次创建实例的问题。

<font color='red'>外层判断：</font>试图想想一种情况，当线程1走完了内层判断，对象实例化了，线程3也调用了getInstace函数，如果没有加外层的判断线程3还是要继续等待线程2的完成，而加上外层判断，就不需要等待了，直接返回了实例化的对象。这个是为了代码提高代码执行效率，由于单例模式只要一次创建实例即可，所以当创建了一个实例之后，再次调用getInstance方法就不必要进入同步代码块，不用竞争锁。直接返回前面创建的实例即可。

总结：**外层的判断是为了提高效率【不必synchronized等待】，里层的判断就是第一次实例化需要**。

### Java设计模式(六种)

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/401339-20170928225241215-295252070.png">

- **单例模式**：就是采取一定的方法保证在整个的软件系统中，对某个类**只能存在一个对象实例**，并且该类只提供一个取得其对象实例的方法

  - **单例模式八种方式：**
    - <font color='blue'>饿汉式（静态常量）</font>
    - <font color='blue'>饿汉式（静态代码块）</font>
    - 懒汉式（线程不安全）
    - 懒汉式（线程安全，同步方法）
    - 懒汉式（线程安全，同步代码块）
    - <font color='blue'>双重检查</font>
    - <font color='blue'>静态内部类</font>
    - <font color='blue'>枚举</font>

- **工厂模式**：属于创建型模式，是工厂模式的一种。

  - **传统方式**优缺点：

    - 优点：利于理解，简单易操作
    - 缺点：违反了设计模式的ocp原则，即对扩展开放，对修改关闭

  - **简单工厂模式：** 属于创建型模式，是工厂模式的一种。是由一个工厂对象决定创建出哪一种产品类的实例。<font color='red'>定义了一个创建对象的类，由这个类来封装实例化对象的行为（代码）</font>

  - **工厂方法模式**：<font color='red'>定义了一个创建对象的抽象方法，由子类决定要实例化的类</font>。工厂方法模式将对象的实例化推迟到子类。

  - **抽象工厂模式**：<font color='red'>定义了一个interface用于创建相关或有依赖关系的对象簇</font>，而无需指明具体的类

    - 可以将简单工厂模式和工厂方法模式进行整合
    - 从设计层面上看，抽象工厂模式就是对简单工厂模式的改进（进一步抽象）
    - 将工厂抽象成两层，<font color='blue'>AbsFactory（抽象工厂）</font>和具体实现的工厂子类。程序员可以根据创建对象类型使用相应的工厂子类，这样将单个的简单工厂类变成了工厂簇，利用代码的维护和扩展

  - 意义：将实例化对象的代码提取出来，放到一个类中统一管理和维护，达到和主项目的依赖关系的解耦，提高项目的扩展和维护性

  - > 创建对象实例时，不要直接new类，而是把这个new类的动作放到一个工厂的方法中，并返回。
    >
    > 不要让类继承具体类，而是继承抽象类或者是实现interface（接口）
    >
    > 不要覆盖基类中已经实现的方法

- **代理模式：**为一个对象提供一个替身，以控制对这个对象的访问。即通过代理对象访问目标对象，这样做的好处是——<font color='red'>可以在目标对象实现的基础上，增强额外的功能操作，即扩展目标对象的功能</font>；被代理的对象可以是远程对象、创建开销大的对象或需要安全控制的对象；代理模式三种形式{<font color='orange'>静态代理、动态代理(JDK代理)、Cglib代理(可以在内存动态的创建对象，不需要实现接口，属于动态代理的范畴)</font>}

  - **静态代理：**使用时，需要定义接口或者父类，被代理对象（即目标对象）与代理对象一起实现相同接口或者是继承相同父类
  - **动态代理：**代理对象不需要实现接口，但是目标对象要实现接口，否则不能用动态代理；代理对象的生成是利用JDK的API，动态的在内存中构建代理对象<font color='blue'>（java.lang.reflect.Proxy——JDK实现代理使用newProxyInstance方法）</font>
  - **Cglib代理：**可以不实现接口；它是在内存中构建一个子类对象从而实现对目标对象功能扩展；是一个强大的高性能代码生成包，可以在运行期扩展java类与实现java接口，Spring AOP使用，实现方法的拦截
    - 在AOP编程中如何选择代理模式：
      1. 目标对象需要实现接口，<font color='green'>用JDK代理</font>
      2. 目标对象不需要实现接口，<font color='green'>用Cglib代理</font>
    - Cglib包的底层是通过使用字节码处理框架ASM来转换字节码并生成新的类

- **适配器模式(Adapter Pattern)：**<font color='red'>将某个类的接口转换成客户端期望的另一个接口表示，主目的是兼容性</font>，让原本因接口不匹配不能一起工作的两个类可以协同工作，其别名为包装器（Wrapper）

  - **工作原理：**
    - 将一个类的接口转换为另一种接口，<font color='blue'>让原本接口不兼容的类可以兼容</font>
    - 从用户角度看不到适配者，是解耦的
    - 用户调用适配器转化出来的目标接口方法，适配器再调用被适配者的相关接口方法
    - 用户收到反馈，感觉只是和目标接口交互
  - **主要分为三类：**
    - <font color='green'>类适配器模式</font>
      1. Java是单继承机制，所以类适配器需要继承src类这一点算是一个缺点，因为这要求dst必须是接口，有一定局限性
      2. src类的方法在Adapter中都会暴露出来，增加了使用的成本
      3. 由于其继承了src类，所以它可以根据需求重写src类的方法，使得Adapter的灵活性增强
    - <font color='green'>对象适配器模式</font>
      1. 基本思路和类适配器相同，只是将Adapter类作修改，不是继承src类，而是持有src类的实例，以解决兼容性问题
      2. 根据“合成复用原则”，在系统中尽量使用关联关系来替代继承关系，解决了类适配器必须继承src的局限性问题，也不再要求dst必须是接口
      3. 对象适配器是适配者模式最常用的一种
      4. 使用成本更低，更灵活
    - <font color='green'>接口适配器模式</font>
      1. 当不需要全部实现接口提供的方法时，可先设计一个抽象类实现接口，并为接口中每个方法提供一个默认实现（空方法），那么该抽象类的子类可有选择的覆盖父类的某些方法来实现需求
      2. 适用于一个接口不想使用其所有的方法的情况
  - **注意事项和细节：**
    - 三种命名方式是根据src是以怎样的形式给到Adapter来命名的
    - 类适配器：以类给到，在Adapter里，将src当作类，继承
    - 对象适配器：以对象给到，在Adapter里，将src作为一个对象，持有
    - 接口适配器：以接口给到，在Adapter里，将src作为一个接口，实现
    - Adapter模式最大的作用就是将原本不兼容的接口融合在一起工作

- **模板方法模式：**<font color='red'>在一个抽象类公开定义了执行它的方法的模板，它的子类可以按需要重写方法实现，但调用将以抽象类中定义的方式进行</font>。模板方法模式定义一个操作中的算法的骨架，而将一些步骤延迟到子类中，使得子类可以不改变一个算法的结构，就可以重定义该算法的某些特定步骤

  - <font color='blue'>钩子方法</font>：在模板方法模式的父类中，可以定义一个方法，默认不做任何事，子类可以视情况要不要覆盖它，该方法称为<font color='blue'>“钩子”</font>
  - 注意事项和细节：
    - **基本思想：**算法只存在于一个地方，也就是在父类中，容易修改。需要修改算法时，只要修改父类的模板方法或者已经实现的某些步骤，子类就会继承这些修改
    - <font color='blue'>实现了最大化代码复用</font>。父类的模板方法和已实现的某些步骤会被子类继承而直接使用
    - 既统一了算法，也提供了很大的灵活性。父类的模板方法确保了算法的结构保持不变，同时由于类提供部分步骤的实现
    - <font color='blue'>不足之处：每一个不同的实现都需要一个子类实现，导致类的个数增加，使得系统更加庞大</font>
    - <font color='green'>一般模板方法都加上final关键字，防止子类重写模板方法</font>
    - 模板方法使用场景：当要完成在某个过程，该过程要执行一系列步骤，这一系列的步骤基本相同，但其个别步骤在实现时可能不同，通常靠拢用模板方法处理

- **装饰者模式：**<font color='red'>动态的将新功能附加到对象上</font>。在对象功能扩展方面，它比继承更有弹性，装饰者模式体现了开闭原则（ocp）

#### 单例模式——饿汉式（静态常量）

```java
public class SingletonTest01 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1); //true
        System.out.println(instance.hashCode());//21685669
        System.out.println(instance1.hashCode());//21685669
    }
}
/*
饿汉式(静态变量)
 */
class Singleton{
    //1.构造器私有化，外部能new
    private Singleton(){

    }
    //2.本类内部创建对象实例
    private final static Singleton instance = new Singleton();
    //3.提供一个公有的静态方法，返回实例对象
    public static Singleton getInstance(){
        return instance;
    }
}
```

> 优缺点说明：
>
> - **优点**：写法简单，就是在类加载的时候完成实例化，避免了线程同步问题。
> - **缺点**：在类加载的时候完成实例化，未达到lazy loading的效果。若是从始至终从未使用过这个实例，会造成内存的浪费。
> - 这种方式基于**classloader**机制避免了多线程同步问题。不过，instance在类装载时就实例化，在单例模式中大多数都是调用**getInstance()**方法，但是导致类装载的原因有很多种，因此不能确定有其他的方式导致类装载，这时候初始化instance就没有达到lazy loading的效果
> - **结论**：可用，**可能**会造成内存浪费

#### 单例模式——饿汉式（静态代码块）

```java
public class SingletonTest01 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1); //true
        System.out.println(instance.hashCode());//21685669
        System.out.println(instance1.hashCode());//21685669
    }
}
/*
饿汉式(静态代码块)
 */
class Singleton{
    //1.构造器私有化，外部能new
    private Singleton(){
    }
    //2.本类内部创建对象实例
    private static Singleton instance;
    //在静态代码块中创建单例对象
    static {
        instance = new Singleton();
    }
    //3.提供一个公有的静态方法，返回实例对象
    public static Singleton getInstance(){
        return instance;
    }
}
```

> 优缺点说明：
>
> - 和上面方法类似，只不过将类实例化的过程放在了静态代码块中，也是在类装载的时候，就执行静态代码块中的代码，初始化类的实例。优缺点和上面一样。
> - 结论：可用，但是可能会造成内存浪费。

#### 单例模式——懒汉式（线程不安全）

```java
package com.wzc.Singleton.type3;

public class SingletonTest03 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1);
        System.out.println(instance.hashCode());
        System.out.println(instance1.hashCode());
    }
}
/*
懒汉式，线程不安全
 */
class Singleton{
    private static Singleton instance;
    private Singleton(){
    }
    //提供一个静态的公有方法，当使用到该方法时，才去创建instance，即懒汉式
    public static Singleton getInstance(){
        if (instance == null){
            instance = new Singleton();
        }
        return instance;
    }
}
```

> 优缺点说明：
>
> - 起到了lazy loading效果，但只能在单线程下使用
> - 如果在多线程下，一个线程进入了if(Singleton == null)判断语句块，还未来得及往下执行，另一个线程也通过了这个判断语句，便会产生多个实例
> - 结论：实际开发中，不使用这种方式

#### 单例模式——懒汉式（线程安全，同步方法）

```java
package com.wzc.Singleton.type4;

public class SingletonTest04 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1);
        System.out.println(instance.hashCode());
        System.out.println(instance1.hashCode());
    }
}
/*
懒汉式，线程安全，synchronized锁
 */
class Singleton{
    private static Singleton instance;
    private Singleton(){
    }
    //提供一个静态的公有方法，当使用到该方法时，才去创建instance，即懒汉式
    public static synchronized Singleton getInstance(){
        if (instance == null){
            instance = new Singleton();
        }
        return instance;
    }
}
```

> 优缺点说明：
>
> - 解决了线程不安全问题
> - 效率太低了，每个线程在想获得类的实例时候，执行getInstance()方法都要进行同步。而其实这个方法只执行一次实例化代码就够了，后面想获得该类实例，直接return就行了
> - 结论：实际开发中，不推荐使用

#### 单例模式——（双重检查）

```java
package com.wzc.Singleton.type4;

public class SingletonTest04 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1);
        System.out.println(instance.hashCode());
        System.out.println(instance1.hashCode());
    }
}
/*
双重检查
 */
class Singleton{
    //volatile：在这里主要是禁止指令重排（分配内存空间，变量赋值，初始化对象顺序不能错乱）
    private static volatile Singleton instance;
    private Singleton(){
    }
    //提供一个静态的公有方法，加入双重检查代码，解决线程安全问题，同时解决懒加载问题
    public static Singleton getInstance(){
        if (instance == null){
            synchronized (Singleton.class){
                if(instance == null){
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}

```

> 优缺点说明：
>
> - **Double-check**是多线程开发中经常使用的，两次if判断可以保证线程安全
> - 实例化代码只用执行一次，后面再次访问时，判断**if(singleton == null)**，直接return实例化对象，也避免反复进行方法同步
> - 线程安全，延迟加载，效率较高
> - 结论：实际开发中，推荐使用

#### 单例模式——（静态内部类）

```java
package com.wzc.Singleton.type5;

public class SingletonTest05 {
    public static void main(String[] args) {
        //测试
        Singleton instance = Singleton.getInstance();
        Singleton instance1 = Singleton.getInstance();
        System.out.println(instance == instance1);
        System.out.println(instance.hashCode());
        System.out.println(instance1.hashCode());
    }
}
/*
静态内部类
 */
class Singleton{
    //构造器私有化
    private Singleton(){
    }
    /*
    写一个静态内部类，该类中有一个静态属性Singleton
    jvm底层类装载时是线程安全的
    SingletonInstance类在Singleton类装载时并不会马上装载
     */
    private static class SingletonInstance{
        private static final Singleton INSTANCE = new Singleton();
    }
    //提供一个静态的公有方法，加入双重检查代码，解决线程安全问题，同时解决懒加载问题
    public static Singleton getInstance(){
        return SingletonInstance.INSTANCE;
    }
}
```

> 优缺点说明：
>
> - 采用了类装载的机制来保证初始化实例时只有一个线程
> - 静态内部类方式在**Singleton**类被装载时并不会立即实例化，而是在需要实例化时，调用**getInstance()**方法，才会装载到**SingletonInstance**类，完成Singleton的实例化
> - 类的静态属性只会在第一次加载类的时候初始化，**JVM**帮助我们保证了线程安全性，在类进行初始化时，别的线程无法进入
> - 优点：避免了线程不安全，利用静态内部类的特点实现延迟加载，效率高
> - 结论：推荐使用

#### 单例模式——（枚举）

```java
package com.wzc.Singleton.type6;

public class SingletonTest06 {
    public static void main(String[] args) {
        Singleton instance = Singleton.INSTANCE;
        Singleton instance1 = Singleton.INSTANCE;
        System.out.println(instance == instance1);
        System.out.println(instance.hashCode());
        System.out.println(instance1.hashCode());
    }
}
/*
枚举
 */
enum Singleton{
    INSTANCE;//属性
    public void sayOk(){
        System.out.println("ok");
    }
}
```

> 优缺点说明：
>
> - 利用枚举实现单例模式，不仅避免多线程同步问题，也能防止反序列化重新创建新的对象
> - 结论：推荐使用

-------------------

#### 工厂模式——（简单工厂模式）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1010726-20200329213128054-1086621221.png">

```java
public class ShapeFactory {
    public Shape getShape(String shapeType){
        if(shapeType.equalsIgnoreCase("circle")){
            return new Circle();
        }else if(shapeType.equalsIgnoreCase("rectangle")){
            return new Rectangle();
        }else if(shapeType.equalsIgnoreCase("squere")){
            return new Squere();
        }
        return null;
    }
    public Shape getShape(Class clazz) throws Exception{
        return (Shape) clazz.newInstance();
    }
}
```

> - 首先来说简单工厂，简单工厂模式，又叫做静态工厂模式（Static Factory Method），由一个工厂对象决定创建出哪一种产品类的实例，简单工厂模式的实质是由一个工厂类根据传入的参数，动态决定应该创建哪一个产品类。**属于`创建型`模式，但不属于GOF23设计模式**。
> - 工厂类负责创建的对象比较少；客户端（应用层）只需要知道传入工厂类的参数，对于如何创建对象（逻辑）不关心。
> - 优点：只需要传入一个正确的参数，就可以获取你所需要的对象，而无需知道其细节创建。
> - 缺点：工厂类的职责相对过重，增加新的产品，需要修改工厂类的判断逻辑，**违背了开闭原则**。

#### 工厂模式——（工厂方法模式）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1010726-20200329222122971-729845567.png">

```java
public interface Shape {
    void draw();
}

public class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("画一个圆");
    }
}

public class Rectangle implements Shape {
    @Override
    public void draw() {
        System.out.println("画一个矩形");
    }
}
```

```java
/*
工厂部分
*/
public abstract class ShapeFactory {
    public abstract Shape getShape();
}

public class CircleFactory extends ShapeFactory {
    @Override
    public Shape getShape() {
        return new Circle();
    }
}

public class RectangleFactroy extends ShapeFactory {
    @Override
    public Shape getShape() {
        return new Rectangle();
    }
}
```

> 工厂方法模式（Factory Method），又称多态性工厂模式，属于设计模式三大分类中的**`创建型模式`**，作为抽象工厂模式的孪生兄弟，**工厂方法模式定义了一个创建对象的接口，但由子类决定要实例化的类是哪一个，也就是说工厂模式让实例化推迟到子类。**
>
> 在工厂模式中，**核心的工厂类不再负责所有的产品的创建，而是将具体的工作交给子类去做。**该核心类成为一个抽象工厂角色，仅负责给出具体工厂子类必须实现的接口，而不接触哪一个产品应当被实例化这种细节。
>
> - 优点：用户只需要关系所需产品对应的工厂，无须关心创建细节；加入新产品**符合开闭原则**，提高可扩展性。
> - 缺点：类的个数容易过多，增加复杂度；增加了系统的抽象性和理解难度。
>
> 工厂方法模式**非常符合“开闭原则”**，**当需要增加一个新产品时，我们只需要增加一个具体的产品类和与之对应的具体工厂即可，无须关系产品的创建过程，甚至连具体的产品类名称都不需要知道。**虽然他很好的符合了“开闭原则”，但是由于**每新增一个新产品时就需要增加两个类，这样势必就会导致系统的复杂度增加**。
>
> 工厂方法模式通常适用于以下场景。
>
> - 客户只知道创建产品的工厂名，而不知道具体的产品名。如 TCL 电视工厂、海信电视工厂等。
> - 创建对象的任务由多个具体子工厂中的某一个完成，而抽象工厂只提供创建产品的接口。
> - 客户不关心创建产品的细节，只关心产品的品牌。

#### 工厂模式——（抽象工厂模式）

<img src="https://wzcwangzichen.oss-cn-shanghai.aliyuncs.com/Picture/1010726-20200329223226182-21218742.png">

```java
/**
 * 手机产品接口
 */
public interface IPhoneProduct {

    /**
     * 开机
     */
    void start();

    /**
     * 关机
     */
    void shutdown();

    /**
     * 拨打电话
     */
    void callUp();

    /**
     * 发送短信
     */
    void sendSMS();

}

/**
 * 路由器产品接口
 */
public interface IRouterProduct {

    /**
     * 开机
     */
    void start();

    /**
     * 关机
     */
    void shutdown();

    /**
     * 开启wifi
     */
    void openWifi();

    /**
     * 设置参数
     */
    void setting();

}

/**
 * 抽象产品工厂（定义了同一个产品族的产品生产行为）
 */
public interface IProductFactory {

    /**
     * 生产手机
     * @return
     */
    IPhoneProduct produceTelPhone();

    /**
     * 生产路由器
     * @return
     */
    IRouterProduct produceRouter();
}
```

```java
/*
产品类
*/
/**
 * 华为手机产品
 */
public class HuaweiPhone implements IPhoneProduct {
    @Override
    public void start() {
        System.out.println("开启华为手机");
    }

    @Override
    public void shutdown() {
        System.out.println("关闭华为手机");
    }

    @Override
    public void callUp() {
        System.out.println("用华为手机打电话");
    }

    @Override
    public void sendSMS() {
        System.out.println("用华为手机发短信");
    }
}

/**
 * 华为路由器产品
 */
public class HuaweiRouter implements IRouterProduct {
    @Override
    public void start() {
        System.out.println("启动华为路由器");
    }

    @Override
    public void shutdown() {
        System.out.println("关闭华为路由器");
    }

    @Override
    public void openWifi() {
        System.out.println("打开华为路由器的wifi功能");
    }

    @Override
    public void setting() {
        System.out.println("设置华为路由器参数");
    }
}

/**
 * 小米手机产品
 */
public class XiaomiPhone implements IPhoneProduct {
    @Override
    public void start() {
        System.out.println("开启小米手机");
    }

    @Override
    public void shutdown() {
        System.out.println("关闭小米手机");
    }

    @Override
    public void callUp() {
        System.out.println("用小米手机打电话");
    }

    @Override
    public void sendSMS() {
        System.out.println("用小米手机发短信");
    }
}

/**
 * 小米路由器产品
 */
public class XiaomiRouter implements IRouterProduct {
    @Override
    public void start() {
        System.out.println("启动小米路由器");
    }

    @Override
    public void shutdown() {
        System.out.println("关闭小米路由器");
    }

    @Override
    public void openWifi() {
        System.out.println("打开小米路由器的wifi功能");
    }

    @Override
    public void setting() {
        System.out.println("设置小米路由器参数");
    }
}
```

```java
/*
产品工厂
*/
/**
 * 华为产品工厂
 */
public class HuaweiProductFactory implements IProductFactory{
    @Override
    public IPhoneProduct produceTelPhone() {
        System.out.println(">>>>>>生产华为手机");
        return new HuaweiPhone();
    }

    @Override
    public IRouterProduct produceRouter() {
        System.out.println(">>>>>>生产华为路由器");
        return new HuaweiRouter();
    }

    @Override
    public IComputer produceComput() {
        return null;
    }
}

/**
 * 小米产品工厂
 */
public class XiaomiProductFactory implements IProductFactory {
    @Override
    public IPhoneProduct produceTelPhone() {
        System.out.println(">>>>>>生产小米手机");
        return new XiaomiPhone();
    }

    @Override
    public IRouterProduct produceRouter() {
        System.out.println(">>>>>>生产小米路由器");
        return new XiaomiRouter();
    }

    @Override
    public IComputer produceComput() {
        return null;
    }
}
```

```java
/**
 * 测试类
 * 使用 FactoryProducer 来获取 AbstractFactory，通过传递类型信息来获取实体类的对象。
 */
public class Test {
   public static void main(String[] args) {

      System.out.println("===================小米系列产品=================");
      //小米产品工厂实例
      IProductFactory xiaomiProductFactory = new XiaomiProductFactory();
      //生产小米路由器
      IRouterProduct xiaomiRouter = xiaomiProductFactory.produceRouter();
      xiaomiRouter.start();
      xiaomiRouter.setting();
      xiaomiRouter.openWifi();
      xiaomiRouter.shutdown();
      //生产小米手机
      IPhoneProduct xiaomiPhone = xiaomiProductFactory.produceTelPhone();
      xiaomiPhone.start();
      xiaomiPhone.callUp();
      xiaomiPhone.sendSMS();
      xiaomiPhone.shutdown();

      System.out.println("===================华为系列产品=================");
      //华为产品工厂实例
      IProductFactory huaweiProductFactory = new HuaweiProductFactory();
      //生产华为路由器
      IRouterProduct huaweiRouter = huaweiProductFactory.produceRouter();
      huaweiRouter.start();
      huaweiRouter.setting();
      huaweiRouter.openWifi();
      huaweiRouter.shutdown();
      //生产华为手机
      IPhoneProduct huaweiPhone = huaweiProductFactory.produceTelPhone();
      huaweiPhone.start();
      huaweiPhone.callUp();
      huaweiPhone.sendSMS();
      huaweiPhone.shutdown();
   }
}
---------------------------------------------------------------
===================小米系列产品=================
>>>>>>生产小米路由器
启动小米路由器
设置小米路由器参数
打开小米路由器的wifi功能
关闭小米路由器
>>>>>>生产小米手机
开启小米手机
用小米手机打电话
用小米手机发短信
关闭小米手机
===================华为系列产品=================
>>>>>>生产华为路由器
启动华为路由器
设置华为路由器参数
打开华为路由器的wifi功能
关闭华为路由器
>>>>>>生产华为手机
开启华为手机
用华为手机打电话
用华为手机发短信
关闭华为手机
```

> 抽象工厂（AbstractFactory）模式的定义：是一种为访问类提供一个创建一组相关或相互依赖对象的接口，且访问类无须指定所要产品的具体类就能得到同族的不同等级的产品的模式结构。抽象工厂模式是工厂方法模式的升级版本，工厂方法模式只生产一个等级的产品，而抽象工厂模式可生产多个等级的产品。
>
> 使用抽象工厂模式一般要满足以下条件：
>
> - 系统中有多个产品族，每个具体工厂创建同一族但属于不同等级结构的产品。
> - 系统一次只可能消费其中某一族产品，即同族的产品一起使用。
>
> 优缺点：
>
> - 优点：具体产品在应用层代码隔离，无须关心创建细节；将一个系列的产品族统一到一起创建。
> - 缺点：规定了所有可能被创建的产品集合，产品族中扩展新的产品困难，需要修改抽象工厂的接口；增加了系统的抽象性和理解难度
>
> 抽象工厂模式的主要角色如下。
>
> 1. **抽象工厂（Abstract Factory）**：提供了创建产品的接口，它包含多个创建产品的方法 newProduct()，可以创建多个不同等级的产品。
> 2. **具体工厂（Concrete Factory）**：主要是实现抽象工厂中的多个抽象方法，完成具体产品的创建。
> 3. **抽象产品（Product）**：定义了产品的规范，描述了产品的主要特性和功能，抽象工厂模式有多个抽象产品。
> 4. **具体产品（ConcreteProduct）**：实现了抽象产品角色所定义的接口，由具体工厂来创建，它 同具体工厂之间是多对一的关系。
>
> 抽象工厂模式通常适用于以下场景：
>
> 1. 当需要创建的对象是一系列相互关联或相互依赖的产品族时，如电器工厂中的电视机、洗衣机、空调等。
> 2. 系统中有多个产品族，但每次只使用其中的某一族产品。如有人只喜欢穿某一个品牌的衣服和鞋。
> 3. 系统中提供了产品的类库，且所有产品的接口相同，客户端不依赖产品实例的创建细节和内部结构。

----

#### 代理模式——（静态代理）

```java
//ITeacherDao.java
package com.wzc.proxy.staticproxy;

public interface ITeacherDao {
    void teach();
}

//TeacherDao.java
package com.wzc.proxy.staticproxy;

public class TeacherDao implements ITeacherDao{
    public void teach() {
        System.out.println("老师授课中");
    }
}

//TeacherDaoProxy.java
package com.wzc.proxy.staticproxy;

/**
 * 代理对象，静态代理
 */
public class TeacherDaoProxy implements ITeacherDao{
    //目标对象，通过接口来聚合
    private ITeacherDao target;
    //构造器
    public TeacherDaoProxy(ITeacherDao target) {
        this.target = target;
    }
    public void teach() {
        System.out.println("代理开始");
        target.teach();
        System.out.println("代理结束");
    }
}

//Client.java
package com.wzc.proxy.staticproxy;

public class Client {
    public static void main(String[] args) {
        //创建目标对象
        TeacherDao teacherDao = new TeacherDao();
        //创建代理对象，同时将被代理对象传递给代理对象
        TeacherDaoProxy teacherDaoProxy = new TeacherDaoProxy(teacherDao);
        //通过代理对象，调用到被代理对象的方法
        teacherDaoProxy.teach();
    }
}

//执行结果
----------------
代理开始
老师授课中
代理结束
----------------
```

> 优点：在不修改目标对象的功能前提下，通过代理对象对目标功能扩展
>
> 缺点：因为代理对象需要与目标对象实现一样的接口，所以会有很多代理类，一旦接口增加方法，目标对象与代理对象都要维护

#### 代理模式——（动态代理）

```java
//ITeacherDao.java
package com.wzc.proxy.dynamicproxy;

public interface ITeacherDao {
    void teach();
    void sayHello(String name);
}

//TeacherDao.java
package com.wzc.proxy.dynamicproxy;

public class TeacherDao implements ITeacherDao {
    public void teach() {
        System.out.println("老师授课中");
    }

    public void sayHello(String name) {
        System.out.println("Hello "+name);
    }
}

//ProxyFactory.java
package com.wzc.proxy.dynamicproxy;

import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
import java.lang.reflect.Proxy;

public class ProxyFactory {
    //维护一个目标对象
    private Object target;
    //构造器，对target初始化
    public ProxyFactory(Object target) {
        this.target = target;
    }
    //给目标对象生成一个代理对象
    public Object getProxyInstance(){
        /**
         *     @CallerSensitive
         *     public static Object newProxyInstance(ClassLoader loader,
         *                                           Class<?>[] interfaces,
         *                                           InvocationHandler h)
         *     1.ClassLoader loader：指定当前目标对象使用的类加载器，获取类加载器的方法固定
         *     2.Class<?>[] interfaces：目标对象实现的接口类型，使用泛型方法确认类型
         *     3.InvocationHandler h：事件处理，执行目标对象的方法时，会触发事件处理器方法，会把
         *     当前执行的目标对象方法作为参数传入
         */
        return Proxy.newProxyInstance(target.getClass().getClassLoader(),
                target.getClass().getInterfaces(),
                new InvocationHandler() {
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        System.out.println("JDK代理开始");
                        //反射机制调用目标对象方法
                        Object returnValue = method.invoke(target,args);
                        System.out.println("JDK代理提交");
                        return returnValue;
                    }
                });
    }
}

//Client.java
package com.wzc.proxy.dynamicproxy;

public class Client {
    public static void main(String[] args) {
        //创建目标对象
        ITeacherDao target = new TeacherDao();
        //给目标对象，创建代理对象，可以转为ITeacherDao
        ITeacherDao proxyFactory = (ITeacherDao) new ProxyFactory(target).getProxyInstance();
        //proxyInstance=class com.sun.proxy.$Proxy0——>内存中动态生成了代理对象
        System.out.println("proxyInstance="+proxyFactory.getClass());
        //通过代理对象，调用目标对象的方法
        proxyFactory.teach();
        proxyFactory.sayHello("TOM");
    }
}

//运行结果
JDK代理开始
老师授课中
JDK代理提交
JDK代理开始
Hello TOM
JDK代理提交
```

#### 代理模式——（Cglib代理）

```java
//TeacherDao.java
package com.wzc.proxy.cglib;

public class TeacherDao {
    public void teach(){
        System.out.println("老师授课中，我是cglib代理，不需要实现接口");
    }
}

//ProxyFactory.java
package com.wzc.proxy.cglib;

import net.sf.cglib.proxy.Enhancer;
import net.sf.cglib.proxy.MethodInterceptor;
import net.sf.cglib.proxy.MethodProxy;

import java.lang.reflect.Method;

public class ProxyFactory implements MethodInterceptor {
    /*
    维护一个目标对象
     */
    private Object target;
    /*
    构造器，传入一个被代理的对象
     */
    public ProxyFactory(Object target) {
        this.target = target;
    }
    /*
    返回一个代理对象，是target这个对象的代理对象
     */
    public Object getProxyInstance(){
        /*
        1.创建一个工具类
        2.设置父类
        3.设置回调函数
        4.创建子类对象，即代理对象
         */
        Enhancer enhancer = new Enhancer();
        enhancer.setSuperclass(target.getClass());
        enhancer.setCallback(this);
        return enhancer.create();
    }
    /*
    重写intercept方法，会调用目标对象的方法
     */
    public Object intercept(Object o, Method method, Object[] objects, MethodProxy methodProxy) throws Throwable {
        System.out.println("Cglib代理模式~开始");
        Object returnValue = method.invoke(target, objects);
        System.out.println("Cglib代理提交~");
        return returnValue;
    }
}

//Client.java
package com.wzc.proxy.cglib;

public class Client {
    public static void main(String[] args) {
        //创建目标对象
        TeacherDao target = new TeacherDao();
        //获取代理对象，并且将目标对象传递给代理对象
        TeacherDao proxyInstance = (TeacherDao)new ProxyFactory(target).getProxyInstance();
        //执行代理对象的方法，触发intecept方法实现对目标对象的调用
        proxyInstance.teach();
    }
}
------------------------------
实验结果：
Cglib代理模式~开始
老师授课中，我是cglib代理，不需要实现接口
Cglib代理提交~
```

-----

#### 适配器模式——（类适配器）

```java
//Voltage220V.java
package com.wzc.adapter.classadapter;
/*
被适配的类
 */
public class Voltage220V {
    public int output220V(){
        int src = 220;
        System.out.println("电压="+src+"伏");
        return src;
    }
}

//IVoltage5V.java
package com.wzc.adapter.classadapter;
/*
适配接口
 */
public interface IVoltage5V {
    public int output5V();
}

//VoltageAdapter.java
package com.wzc.adapter.classadapter;

/*
适配器类
 */
public class VoltageAdapter extends Voltage220V implements IVoltage5V{
    public int output5V() {
        //获取到220V电压
        int srcV = output220V();
        int dstV = srcV / 44;
        return dstV;
    }
}

//Phone.java
package com.wzc.adapter.classadapter;

public class Phone {
    //充电
    public void charging(IVoltage5V iVoltage5V){
        if (iVoltage5V.output5V() == 5){
            System.out.println("电压为5v，可以充电~");
        }else if (iVoltage5V.output5V() > 5){
            System.out.println("电压太高了~");
        }
    }
}

//Client.java
package com.wzc.adapter.classadapter;

public class Client {
    public static void main(String[] args) {
        System.out.println("===类适配器模式===");
        Phone phone = new Phone();
        phone.charging(new VoltageAdapter());
    }
}
```

#### 适配器模式——（对象适配器）

```java
//Voltage220V.java
package com.wzc.adapter.classadapter;
/*
被适配的类
 */
public class Voltage220V {
    public int output220V(){
        int src = 220;
        System.out.println("电压="+src+"伏");
        return src;
    }
}

//IVoltage5V.java
package com.wzc.adapter.classadapter;
/*
适配接口
 */
public interface IVoltage5V {
    public int output5V();
}

//VoltageAdapter.java
package com.wzc.adapter.objectadapter;

/*
适配器类
 */
public class VoltageAdapter implements IVoltage5V {

    private Voltage220V voltage220V;

    public VoltageAdapter(Voltage220V voltage220V) {
        this.voltage220V = voltage220V;
    }

    public int output5V() {
        int dstV = 0;
        if (null != voltage220V){
            //获取220V电压
            int srcV = voltage220V.output220V();
            System.out.println("使用对象适配器适配~");
            dstV = srcV / 44;
            System.out.println("适配完成，输出电压为："+dstV);
        }
        return dstV;
    }
}


//Phone.java
package com.wzc.adapter.classadapter;

public class Phone {
    //充电
    public void charging(IVoltage5V iVoltage5V){
        if (iVoltage5V.output5V() == 5){
            System.out.println("电压为5v，可以充电~");
        }else if (iVoltage5V.output5V() > 5){
            System.out.println("电压太高了~");
        }
    }
}

//Client.java
package com.wzc.adapter.objectadapter;

public class Client {
    public static void main(String[] args) {
        System.out.println("===对象适配器模式===");
        Phone phone = new Phone();
        phone.charging(new VoltageAdapter(new Voltage220V()));
    }
}
```

#### 适配器模式——（接口适配器）

<font color='green'>SpringMVC框架中的HandlerAdapter使用了适配器模式</font>

<font color='green'>HandlerAdapter的实现子类使得每一种Controller有一种对应的适配器实现类，每种Controller有不同的实现方式</font>

<font color='green'>扩展Controller时，只需要增加一个适配器类就完成了SpringMVC的扩展了</font>

#### 模板方法模式

```java
//SoyaMilk.java
package com.wzc.template;
/*
抽象类，表示豆浆
 */
public abstract class SoyaMilk {
    //模板方法，make，可以使用final，防止子类覆盖
    final void make(){
        select();
        addCondiments();
        soak();
        beat();
    }
    //选材料
    void select(){
        System.out.println("第一步：选择新鲜黄豆");
    }
    //添加材料，抽象方法，子类具体去实现
    abstract void addCondiments();
    //浸泡
    void soak(){
        System.out.println("第三步：黄豆和配料开始浸泡");
    }
    //打豆浆
    void beat(){
        System.out.println("第四步：开始打豆浆");
    }
}

//PeanutSoyaMilk.java
package com.wzc.template;

public class PeanutSoyaMilk extends SoyaMilk {
    void addCondiments() {
        System.out.println("第二步：加入新鲜的花生");
    }
}

//RedBeanSoyaMilk.java
package com.wzc.template;

public class RedBeanSoyaMilk extends SoyaMilk {
    void addCondiments() {
        System.out.println("第二步：加入新鲜的红豆");
    }
}

//Client.java
package com.wzc.template;

public class Client {
    public static void main(String[] args) {
        System.out.println("==制作红豆豆浆==");
        SoyaMilk redBeanSoyaMilk = new RedBeanSoyaMilk();
        redBeanSoyaMilk.make();
        System.out.println();
        System.out.println("==制作花生豆浆==");
        SoyaMilk peanutSoyaMilk = new PeanutSoyaMilk();
        peanutSoyaMilk.make();
    }
}
```

#### 模板方法模式——（钩子方法）

```java
//SoyaMilk.java
package com.wzc.template.improve;
/*
抽象类，表示豆浆
 */
public abstract class SoyaMilk {
    //模板方法，make，可以使用final，防止子类覆盖
    final void make(){
        select();
        if (customrWantCondiments()) {
            addCondiments();
        }
        soak();
        beat();
    }
    //选材料
    void select(){
        System.out.println("第一步：选择新鲜黄豆");
    }
    //添加材料，抽象方法，子类具体去实现
    abstract void addCondiments();
    //浸泡
    void soak(){
        System.out.println("第三步：黄豆和配料开始浸泡");
    }
    //打豆浆
    void beat(){
        System.out.println("第四步：开始打豆浆");
    }
    /*
    钩子方法，决定是否需要添加配料
     */
    boolean customrWantCondiments(){
        return true;
    }
}

//PeanutSoyaMilk.java
package com.wzc.template.improve;
public class PeanutSoyaMilk extends SoyaMilk {
    void addCondiments() {
        System.out.println("第二步：加入新鲜的花生");
    }
}

//RedBeanSoyaMilk.java
package com.wzc.template.improve;
public class RedBeanSoyaMilk extends SoyaMilk {
    void addCondiments() {
        System.out.println("第二步：加入新鲜的红豆");
    }
}

//PuritySoyaMilk.java
package com.wzc.template.improve;
public class PuritySoyaMilk extends SoyaMilk{
    void addCondiments() {

    }

    @Override
    boolean customrWantCondiments() {
        return false;
    }
}

//Client.java
package com.wzc.template.improve;
public class Client {
    public static void main(String[] args) {
        System.out.println("==制作红豆豆浆==");
        SoyaMilk redBeanSoyaMilk = new RedBeanSoyaMilk();
        redBeanSoyaMilk.make();
        System.out.println();
        System.out.println("==制作花生豆浆==");
        SoyaMilk peanutSoyaMilk = new PeanutSoyaMilk();
        peanutSoyaMilk.make();
        System.out.println();
        System.out.println("==制作纯豆浆==");
        SoyaMilk puritySoyaMilk= new PuritySoyaMilk();
        puritySoyaMilk.make();
    }
}
```

#### 装饰者模式

```java
//ShortBlack.java
package com.wzc.decorator;

public class ShortBlack extends Coffee{
    public ShortBlack() {
        setDescription("ShortBlack咖啡");
        setPrice(4.0f);
    }
}

//LongBlack.java
package com.wzc.decorator;

public class LongBlack extends Coffee{
    public LongBlack() {
        setDescription("LongBlack咖啡");
        setPrice(5.0f);
    }
}

//Espresso.java
package com.wzc.decorator;

public class Espresso extends Coffee{
    public Espresso() {
        setDescription("意大利咖啡");
        setPrice(6.0f);
    }
}

//Coffee.java
package com.wzc.decorator;

public class Coffee extends Drink{
    public float cost() {
        return super.getPrice();
    }
}

//Drink.java
package com.wzc.decorator;
public abstract class Drink {
    public String description;
    private float price = 0.0f;

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public float getPrice() {
        return price;
    }

    public void setPrice(float price) {
        this.price = price;
    }
    //计算费用的抽象方法，子类来实现
    public abstract float cost();
}

//Decorator.java
package com.wzc.decorator;

public class Decorator extends Drink{
    private Drink obj;

    public Decorator(Drink obj) {
        this.obj = obj;
    }

    public float cost() {
        /*
        getPrice()自己的价格
         */
        return super.getPrice() + obj.cost();
    }

    @Override
    public String getDescription() {
        //obj.getDescription() 输出被装饰者的信息
        return super.description + " " + super.getPrice() + " && " + obj.getDescription();
    }
}

//Milk.java
package com.wzc.decorator;
/*
具体的Decorator
 */
public class Milk extends Decorator{
    public Milk(Drink obj) {
        super(obj);
        setDescription("牛奶");
        setPrice(2.0f);
    }
}

//Soya.java
package com.wzc.decorator;
/*
具体的Decorator
 */
public class Soya extends Decorator{
    public Soya(Drink obj) {
        super(obj);
        setDescription("豆浆");
        setPrice(1.5f);
    }
}

//Chocolate.java
package com.wzc.decorator;
/*
具体的Decorator
 */
public class Chocolate extends Decorator{
    public Chocolate(Drink obj) {
        super(obj);
        setDescription("巧克力");
        setPrice(3.0f);
    }
}

//Client.java
package com.wzc.decorator;

public class Client {
    public static void main(String[] args) {
        //装饰者模式下订单：2份巧克力+1份牛奶+LongBlack
        Drink longBlack = new LongBlack();
        System.out.println("费用："+longBlack.getPrice());
        System.out.println("描述："+longBlack.getDescription());
        //加入牛奶
        longBlack = new Milk(longBlack);
        System.out.println("longblack加入牛奶后费用："+longBlack.cost());
        System.out.println("描述："+longBlack.getDescription());

        //加入第1份巧克力
        longBlack = new Chocolate(longBlack);
        System.out.println("longblack加入1份牛奶和1份巧克力后费用："+longBlack.cost());
        System.out.println("描述："+longBlack.getDescription());

        //加入第2份巧克力
        longBlack = new Chocolate(longBlack);
        System.out.println("longblack加入1份牛奶和2份巧克力后费用："+longBlack.cost());
        System.out.println("描述："+longBlack.getDescription());
    }
}
============================================
费用：5.0
描述：LongBlack咖啡
longblack加入牛奶后费用：7.0
描述：牛奶 2.0 && LongBlack咖啡
longblack加入1份牛奶和1份巧克力后费用：10.0
描述：巧克力 3.0 && 牛奶 2.0 && LongBlack咖啡
longblack加入1份牛奶和2份巧克力后费用：13.0
描述：巧克力 3.0 && 巧克力 3.0 && 牛奶 2.0 && LongBlack咖啡
```

## 智力题

### 一根质量不均匀的绳子,烧一根要一小时,有若干根这样的绳子,怎样计算出15分钟？

拿1根绳子两头同时点燃,同时把第2根绳子的1头点燃.当第1根绳子燃完的时候就用了30分钟.这时第2根绳子已经燃了30分钟，就还剩下30分钟可以燃.这时才开始计时，再把剩下的绳子两头点燃,15分钟剩下的绳子就烧完了

### 连续的三个大于6的整数，其中两个是质数，证明第三个可以被6整除？

<font color='blue'>证明1：</font>因为大于6， 所以素数一定是奇数， 所以a, c 是奇数，b是偶数。 所以b能被2整除

<font color='blue'>证明2：</font>连续的3个整数， 其中一定有被3整除的， 比如4，5，6. 所以b能被3整除

`能被6整除的数的特征：若一个整数能被2和3整除，则这个数能被6整除`

### 两个人抛硬币来决定谁吃这个苹果，先抛到正面者吃，问先抛者吃到苹果的概率是多少?

设先抛得人吃到苹果概率为`p`，那么后抛的概率为`1-p`。

后抛的概率计算：先抛的没中，概率1/2，现在后抛变先抛，那么他吃到的概率为p，所以总结后抛吃到概率为`（1/2）*p`，结合前面的设，`1-p=（1/2）*p`，求解：`p=2/3`

### 五个洞排一排  狐狸每晚可以移动到相邻的洞里，每天白天可以查一个洞，问最少几次一定能找到狐狸，具体怎么操作？

以**234432**的顺序最少六天，下面来分析一下：

1. 第一次抓第二个，不在二中，则在一三四五中，晚上只能跑到二三四五中，
2. 第二次抓第三个，不在三中，则在二四五中，晚上跑到一三四五中，
3. 第三次抓第四个，不在四中，则在一三五中，晚上跑到二四中，
4. 第四次抓第四个，不在四中，则在二中，晚上跑到一三中，
5. 第五次抓第三个，不在三中，则在一中，晚上跑到二中，
6. 第六次抓第二个，一定能抓到。
7. 所以最多六次就可以抓到

### 一个0，1数组，你最多能将k个0变成1，问能形成的连续1的最大长度？

```java
/**
 * @description:
 *
 * 给定一个由若干 0 和 1 组成的数组 A，我们最多可以将 K 个值从 0 变成 1 
 * 返回仅包含 1 的最长（连续）子数组的长度
 * 
 * 输入：A = [1,1,1,0,0,0,1,1,1,1,0], K = 2
 * 输出：6
 *
 * 解释：
 * [1,1,1,0,0,1,1,1,1,1,1]
 * 粗体数字从 0 翻转到 1，最长的子数组长度为 6。
 */
public class Test {
    public static int max=0;
    public static void main(String[] args) {
        int[] arr = {0,1,1,1,0,0,1,0,1,0,1};
        test(arr, 0, 2);
        System.out.println(max);
    }
    public static void test(int[] array, int index, int k) {
        if (index == array.length || k == 0) {
            int len = 0;
            for (int i = 0; i < array.length; i++) {
                if (array[i] == 1) {
                    len ++;
                    max = Math.max(len, max);
                } else {
                    len = 0;
                }
            }
        }
        //回溯思想 把改变的元素再修改回来，再重新尝试, 结点（index）在改变
        for (int j = 0; j < array.length; j++) {
            if (array[j] == 0) {
                array[j] = 1;
                test(array, index + 1, k - 1);
                array[j] = 0;
            }
        }
    }
}
```

### 50个红球和50个篮球，放入两个箱子，怎么样放置才能使拿到红球的概率最大？

**答案：**两个箱子概率是1/2，选中某个箱子后又有选择的是不是红球的概率，所以最大概率就是一个红球放在一个箱子里，其余的99个球全放到另一个箱子。这样概率=<font color='blue'>0.5+0.5*（49/99）</font>约等于0.75，这样为最大概率。

### 有10瓶药，每瓶有10粒药，其中有一瓶是变质的。好药每颗重1克，变质的药每颗比好药重0.1克，怎样用天秤称一次找出变质的那瓶药？

先将这十瓶药由一到十按顺序排好，或在瓶上贴上数字，然后在一号瓶上拿出一粒药，二号拿两粒，如此类推，十号拿十粒。总共是五十五颗药。再将这些药一次称。多出的量，那个数字就代表哪个瓶，而那瓶药就是变质的药。比如称出的重量是五十五点二，那么第二瓶药就是变质的。

# wzc面经大全之测试开发面试题

### JMeter测试上传文件接口？

### Token、Session、Cookie的区别？

> <font color='red'>**Cookie**</font>由服务器生成，发送给浏览器，浏览器把cookie以kv形式保存到某个目录下的文本文件内，下一次请求同一网站时会把该cookie发送给服务器。由于cookie是存在客户端上的，所以浏览器加入了一些限制确保cookie不会被恶意使用，同时不会占据太多磁盘空间，所以每个域的cookie数量是有限的。

> <font color='red'>**Token**</font>的引入：Token是在客户端频繁向服务端请求数据，服务端频繁的去数据库查询用户名和密码并进行对比，判断用户名和密码正确与否，并作出相应提示，在这样的背景下，Token便应运而生。
>
> Token的定义：Token是服务端生成的一串字符串，以作客户端进行请求的一个令牌，当第一次登录后，服务器生成一个Token便将此Token返回给客户端，以后客户端只需带上这个Token前来请求数据即可，无需再次带上用户名和密码。最简单的token组成:uid(用户唯一的身份标识)、time(当前时间的时间戳)、sign(签名，由token的前几位+盐以哈希算法压缩成一定长的十六进制字符串，可以防止恶意第三方拼接token请求服务器)。
>
> 使用Token的目的：Token的目的是为了减轻服务器的压力，减少频繁的查询数据库，使服务器更加健壮。

> **<font color='red'>session</font>** 从字面上讲，就是会话。这个就类似于你和一个人交谈，你怎么知道当前和你交谈的是张三而不是李四呢？对方肯定有某种特征（长相等）表明他就是张三。
>
> session 也是类似的道理，服务器要知道当前发请求给自己的是谁。为了做这种区分，服务器就要给每个客户端分配不同的“身份标识”，然后客户端每次向服务器发请求的时候，都带上这个“身份标识”，服务器就知道这个请求来自于谁了。至于客户端怎么保存这个“身份标识”，可以有很多种方式，对于浏览器客户端，大家都默认采用 cookie 的方式。
>
> 服务器使用session把用户的信息临时保存在了服务器上，用户离开网站后session会被销毁。这种用户信息存储方式相对cookie来说更安全，可是session有一个缺陷：如果web服务器做了负载均衡，那么下一个操作请求到了另一台服务器的时候session会丢失。

### 微信登录测试

<img src="https://img-blog.csdnimg.cn/20200726155344539.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ1NjA1MjIz,size_16,color_FFFFFF,t_70#pic_center">

### 逻辑覆盖方法中哪种覆盖最高？

覆盖强度由弱到强：

<font color='red'>**语句覆盖：**</font>**语句覆盖是一个比较弱的测试标准，它的含义是：选择足够的测试用例，使得程序中每个语句至少都能被执行一次**

<font color='red'>**判定覆盖：**</font>**程序中的每一个分支至少都通过一次，会忽略每个条件的取值情况，导致遗漏部分测试路径**

<font color='red'>**条件覆盖：**</font>**判定中的每个条件获得各种可能的结果，只能保证每个条件都取到了不同结果，但没有考虑到判定结果，因此有时候条件覆盖并不能保证判定覆盖**

<font color='red'>**判断逻辑覆盖：**</font>**判定中每个条件取到各种可能的值，并使每个判定取到各种可能的结果，并未考虑条件的组合情况**

<font color='red'>**条件组合覆盖：**</font>**每个判定中条件的各种可能组合都至少出现一次，但是组合覆盖的测试用例数量相对来说也是比较多的**

<font color='red'>**路径覆盖：**</font>**程序中每条路径都需要覆盖，但实际上很多时候路径覆盖的可操作性不强**

### 基本路径测试

**定义：**基本路径测试法又称独立路径测试，是在程序控制流图的基础上，通过分析控制结构的环路复杂性，导出基本可执行路径集合，从而设计出相应的测试用例的方法。

所谓基本路径是指程序中至少引进一条新的语句或一个新的条件的任一路径。

#### 步骤

1. 根据程序设计结果导出程序流程图的控制流图；、

   流程图用来描述程序控制结构。可将流程图映射到一个相应的流图(对于菱形框内的复合条件，要拆分成单一条件)。在流图中，每一个圆，称为流图的结点，代表一个或多个语句。一个处理方框序列和一个菱形决测框可被映射为一个结点，流图中的箭头，称为边或连接，代表控制流，类似于流程图中的箭头。一条边必须终止于一个结点，即使该结点并不代表任何语句(例如：if-else-then结构)。由边和结点限定的范围称为区域。计算区域时应包括图外部的范围

2. 计算程序环路复杂度

   环路复杂度是一种为程序逻辑复杂性提供定量测度的软件度量，将该度量用于计算程序的基本的独立路径数目，为确保所有语句至少执行一次的测试数量的上界。独立路径必须包含一条在定义之前不曾用到的边。

3. 导出基本路径集，确定程序的独立路径

   每个圈与圈之间的连线便是一个独立路径，对于单进单出的节点可以使用连线代替。

4. 根据独立路径，设计相应的测试用例

   根据上面的独立路径，去设计输入数据。

### 黑盒白盒的概念，适合运用于什么场景（携程测开）

在黑盒测试中，被测对象的内部结构，运作情况对测试人员是不可见的，测试人员对被测产品的验证主要是根据其规格，验证其与规格的一致性。

最常见的测试有：功能性测试、容量测试、安全性测试、负载测试、恢复性测试、标杆测试、稳定性测试、可靠性测试等。

白盒测试需要你对系统内部的结构和工作原理有一个清楚的了解，并且基于这个知识来设计你的用例。

白盒测试优点：迫使测试人员去仔细的思考软件的实现；可以检测代码中的每条分支和路径；揭示隐藏在代码中的错误；对代码的测试比较彻底；最优化。

白盒测试缺点：昂贵；无法检测代码中遗漏的路径和数据敏感性错误；不验证规格的正确性。

白盒测试技术一般可被分为静态分析和动态分析两类技术。

- 静态分析主要有：控制流分析技术、数据流分析技术、信息流分析技术。
- 动态分析主要有：逻辑覆盖率测试(分支测试、路径测试等)，程序插装等。

----------------------------------

<font color='blue'>黑盒测试不要求考虑程序的内部逻辑和数据处理，不要求测试人员遍历代码阅读程序，只需要明确输入输出规则，确保系统或模块实现了业务需求。</font>

- 建议在对稳定运行的大中型系统进行小规模的功能优化或改造过程中使用黑盒测试方法，只需要明确当前项目的改造点，确认与已有功能的关联性和影响，针对项目改造范围进行测试，非特殊情况无需了解系统或模块的全部处理逻辑。
- 建议复杂度和重要性较低的系统，在时间精力有限的情况下优先选用黑盒测试方法进行测试。测试人员首先明确业务需求，使用等价类划分和边界值分析方法完成测试案例设计，适当结合程序特征、个人经验以及冒烟测试情况等对测试案例进行修订补充，在系统无重大问题或异常的情况下，一般黑盒测试即可满足该类系统测试要求。
- 建议适当考量测试人员或测试团队专业技术能力以及测试阶段，如在系统功能测试已经完成的前提下，业务方执行的业务验收测试可以使用黑盒测试方法，降低了团队组建成本和测试成本，无需要求业务人员对代码和软件逻辑进行充分学习和掌握。

-------

<font color='blue'>白盒测试要求测试人员对代码和程序逻辑有相应了解，对测试人员专业背景或能力有一定要求，建议根据项目需求和测试要求选择测试方法。</font>

**白盒测试法的覆盖标准有逻辑覆盖、循环覆盖和基本路径测试。其中逻辑覆盖包括语句覆盖、判定覆盖、条件覆盖、判定/条件覆盖、条件组合覆盖和路径覆盖。**

- 一般单元测试及集成测试需要使用白盒测试方法，包括代码检查法、静态结构分析法等，相关测试多由开发人员完成，具体视项目团队分工而定。
- 建议针对新建系统或已有系统新增重要模块时使用白盒测试方法，例如逻辑覆盖或基本路径测试法，尤其推荐在有较多校验关系且校验关系间存在嵌套时使用，使用时一般可参考程序代码、详细设计说明书、程序控制流图等相关资料，帮助减少测试人员的分析工作量等。
- 建议对重点系统进行架构优化、对公共函数或程序进行改造、对后台或接口内容进行调整时选用白盒测试方法，一方面关注优化改造后对原有程序的改动大小，一方面关注调用方或消费方是否受影响，新版本程序或系统对旧版本的兼容性，避免关联系统由于改造时测试不充分受到影响。
- 建议关注测试中的集群现象，对于缺陷或问题集中的功能和模块建议及时由黑盒测试方法改为白盒测试，在缺陷管理过程中及时进行小范围的测试方法调整，同时保证测试效率和测试充分性。

### 测试用例包含哪些元素

- **用例编号：**相当于一个人的身份证号、一个用例也有一个英里编号
- **用例名称：**也就是一个人的名字，每一个都有一个名字，用例也有一个自己的名字
- **测试背景：**就是测试环境背景，说明什么项目，测什么，在什么情况背景下去测
- **优先级：**根据自己安排来确定哪一个优先
- **重要级：**根据事情的重要程度来确定，和优先级有一点差别
- **测试数据：**测试的参数数据
- **测试步骤：**也就是测试的一个过程
- **预期结果：**想象的一个可能达到的结果
- **实际结果：**实际测试过程出现的最终结果
- **备注：**强调特殊情况内容
- **前置条件：**测试的前提条件，比如你要测一个登陆界面，你要有一个已注册的账号密码，这才能测

### 测试百度搜索框（高频考题）

#### 功能测试

1. **输入内容**

- 输入不同形式的内容：字符，图片，音频等输入字符，是否有默认的高频相关字符在下拉菜单中显示出来
- 内容为空
- 内容含有特殊字符，如空格等。输入前后的空格是否能够忽略，但不能忽略中间的空格
- 内容含有非法字符
- 反复输入相同的数据，如5次以上，看处理是否正确

2. **搜索长度，边界值测试**

- 内容在指定长度之内；
- 内容在指定长度之外，观察系统能够正确进行截取。
- 只能输入允许的字符串长度。百度最长为38个字

3. **搜索框是否支持快捷键：复制，粘贴等**

4. **是否支持回车进行搜索**

5. **是否可以删除重输**

6. **是否可以在搜索界面继续输入**

7. 链接测试：页面上的链接都可连接至正确的页面　　

8. 搜索历史内容记录，便于查找检索过的内容

#### 性能测试

1. 在网络情况良好的前提下，页面的跳转需要多长时间

2. 在网络情况不好的前提下，页面的跳转需要多少时间

3. 对搜索引擎进行加压测试

4. 搜索页面打开的速度是否满足设计要求　　

5. 搜索出结果消耗的时间，是否满足设计要求

#### UI测试

1. UI显示是否正确

2. 页面布局，页面样式检查

3. 组件，控件位置放置是否合适，

4. 是否支持快捷键

5. Tab键切换焦点顺序正确性

6. 已查看过的结果链接，链接的颜色要灰化处理，和没有点击过的结果链接区分

7. 当结果数量庞大时，页面的分页布局合理

#### 安全性测试

1. SQL注入攻击防范

2. 脚本注入测试

3. 被删除、加密、授权的数据，不允许被查出来的，是否有安全控制设计

4. 敏感内容的检索是禁止的

#### 兼容性测试

1. 不同操作系统平台：Windows系统，MacOS系统

2. 不同浏览器：Firefox，Chrome，IE，及其各个版本

3. 不同移动端：IOS，Android

4. 不同分辨率

#### 易用性测试

1. 对用户是否友好

2. 是否有在线帮助文档

### 微信发红包测试用例

#### 功能测试

**1）发给单个好友**
① 正确的金额+无留言+无表情
② 错误的金额+无留言+无表情
③ 正确的金额+有留言+无表情
④ 错误的金额+有留言+无表情
⑤ 正确的金额+无留言+有表情
⑥ 错误的金额+无留言+有表情
⑦ 正确的金额+有留言+有表情
⑧ 错误的金额+有留言+有表情
**其中，金额（0.01-200）可以测试以下数据**
1）数字：测试0, 0.009, 0.01，0.011, 01， 199.99, 200, 200.01这些边界值
2）中文、英文、特殊字符或者这几种的组合
3）是否支持复制黏贴
4）为空/包含空格
5）金额的增删查改
**留言可以测试以下数据**
1）数字、中文、英文、特殊字符、表情或者他们的组合
2）输入超长文本时，是否会给出相应的限制或提示
3）包含空格
4）是否支持复制黏贴
5）留言的增删查改
**表情可以测试以下数据**
1）选择收藏的表情测试（动图/静图）
2）选择下载的表情测试（动图/静图）
3）录制表情，并添加进行测试
4）表情的增删查改
⑨ 点击塞钱进红包，选择零钱付款，此时需要考虑金额＞零钱，金额＜零钱，金额=零钱三种情况
⑩ 点击塞钱进红包，选择已添加的银行卡付款，此时同样需要考虑金额＞银行卡余额，金额＜银行卡余额，金额=银行卡余额三种情况
⑪ 点击塞钱进红包，选择使用新卡付款，按照流程添加新卡，此时同样需要考虑金额＞新卡余额，金额＜新卡余额，金额=新卡余额三种情况
⑫ 使用指纹确认付款（正确的/不正确的指纹）
⑬ 使用密码确认付款（正确的/不正确的密码 ）
⑭ 发送成功之后，对应的途径会减少相应的金额
⑮ 发送者/接受者可以点击红包查看到红包的具体信息，且金额，留言，表情均能正确显示
⑯ 好友点击红包之后，零钱中将增加相应的金额，再次点击之后，只能查看到红包的信息
⑰ 24小时之内没有领取的红包，将退回原账户，此时原账户的零钱将增加相应金额的金钱。24小时后好友点击红包，显示红包已过期，无法查看到红包的余额
⑱ 右上角的红包记录中，可以查看刚刚发出的红包的金额
⑲ 检测帮助中心中链接是否均可以正常跳转，查看
20 当红包超过24小时之后，则无法查看红包被每个人领取的详细信息
**2）发送群红包（与发给好友的测试点相似，以下仅写出不同的部分）**
① 选择为拼手气红包时，群中每个人收到的金额随机（但加起来为红包的总金额），为普通红包时，群中每个人收到的金额相同
② 红包个数（1-100）：0，1，2，大于群成员人数，小于群成员人数，等于群成员人数，99，100，101，小数，中文、英文、特殊字符、表情或者他们的组合
③ 但红包没有被抢完时，此时首次点击该红包的人可以抢到一定金额的红包，不是首次点击该红包的人只能查看该红包的信息；当红包抢完时，所有人只能查看该红包的信息。
④ 在24小时之内红包的金额被完全抢完，且此时为拼手气红包时，金额最多的人会显示为最佳手气（若有两个人取得红包的最大值时，则只有一个人会显示为最佳手气）；若没有被完全抢完，则没有最佳手气，且余额会退还到原账户
⑤ 群中所有人均可以抢红包（包括自己），每个人最多只有一次抢该红包的机会
⑥ 测试当红包个数使得每个红包分到钱小于0.01，即总金额为0.02，而红包个数为3时的情况

#### 性能测试

1）打开红包的响应时间不能超过三秒，高并发场景下不能超过5秒

2）耗电量

3）消耗流量的多少

4）所占内存等

1）网络兼容性：2g/3g/4g，WiFi，热点，移动/联通/电信

2）无网测试

3）弱网：延时&丢包

#### 安全测试

输入密码是否会被盗取

#### UI测试

1）界面的设计风格是否统一

2）界面中文字是否简洁，没有错别字

3）是否易操作，易学习，易理解

#### 兼容性测试

1）苹果手机和安卓手机

2）苹果手机的不同版本

3）安卓手机不同的机型

4）不同分辨率

### 软件生命周期

需求分析、软件设计、程序编码、软件测试、运行维护

### 测试电梯

#### 功能测试

- 单个功能

```markdown
梯内分楼层键是否正常
电梯内开关门键是否正常
电梯内的报警键是否正常使用
电梯外的上下键是否正常
同时关注显示屏，电梯内外的显示屏显示的电梯层数和运行方向
有障碍物时，电梯门的感应系统有效情况
```

- 模块交互

单个功能测试完成后，再将单个功能组合起来测试，称为集成测试，集成测试可以根据电梯的运行状态来设计测试用例，采用等价类划分的思想。

```markdown
电梯当前状态是上行时，有人在X楼按下上升/下降键，电梯是否会停止
电梯当前状态是下行时，有人在X楼按下上升/下降键，电梯是否会停止
在搭载满员的情况下，如有人在X楼按下上升/下降键，电梯是否会停止
```

#### 接口测试

例如：一栋楼有2部电梯，一部停在2楼，一部停在4楼，有人1楼按电梯，是否2楼的电梯下降到1楼开

```markdown
电梯和大楼层
梯和摄像头
电梯与空调
电梯和对讲机（报警装置）
电梯与显示屏
电梯与其他电梯的协作能力
```

#### 界面测试

```markdown
查看电梯的外观
按钮的图标显示，大小
电梯内部张贴的说明（比如报警装置的说明、称重量等）
```

#### 易用性测试

```markdown
楼层按键高度（小孩和一些身高矮的用户会按键不方便）
电梯是否有地毯、夏天是否有空调、通风条件、照明条件、手机信号是否通畅
电梯是否有扶手，是否有专针对残疾人的扶手等等
```

#### 安全性测试

```markdown
下坠时是否有制动装置
暴力破坏电梯时是否报警，
超重是否报警
超时自动开门
火灾报警后，允许就近停靠
停电情况下电梯是否有应急电源装置
```

#### 兼容性测试

```markdown
电梯的整体和其他设备的兼容性，与大楼的兼容，与海底隧道的兼容等等
不同类型的电压是否兼容
```

#### 性能测试

```markdown
测试电梯负载单人时的运行情况（基准测试）多人时的运行情况（负载测试）一定人数下较长时间的运作（稳定性测试）更长时间运作时的运行情况（疲劳测试）不断增加人数导致电梯报警（拐点压力测试）
```

#### 验收测试

```markdown
大量用户从1楼上电梯，去向不同的楼层。大家都不同的楼层上电梯，一起到一楼。
```

- 

### 微信朋友圈测试用例

#### 功能测试

**朋友圈发送功能**

1）只发送文本

   a、考虑文本长度：1-1500字符（该数据为百度数据）、超出最大字符长度

   b、考虑文本类型：纯中文、纯数字、纯字母、纯字符、纯表情（微信表情/手机自带表情）、混合类型、包含url链接；因为过长纯类型需要换行很容易出现超出边框问题，所以这里先考虑过长纯类型情况

   c、文本是否支持复制粘贴

   d、为空验证 

2）只发送图片

   a、本地相册选择/拍摄

   b、图片数量验证：1-9张图片、超出9张

   c、图片格式验证：常见图片格式jpg、png（以实际微信需求支持的格式为准）、动态gif图片、不支持的图片格式

   d、图片尺寸验证：最大700*800像素(此为百度数据)、超出最大尺寸范围是否压缩

   e、图片大小验证：1-300kb（此为百度数据）、超出300kb

   f、图片的预览验证：点击支持预览大图、多张图片支持左右滑动预览

   g、图片的增删改操作

   h、为空验证

3）只发送视频

   a、本地相册选择/拍摄

   b、视频秒数验证：1-10s，超出10s

   c、视频个数验证：1个，超出1个

   d、视频格式验证：支持的视频格式，例mp4、不支持的视频格式

   e、视频大小验证：苹果400kb以内、Android200-300kb（此为百度数据）、超出规定大小

   f、视频预览增删改操作

   g、为空验证

4）发送文本+图片：输入满足要求的文本、图片进行一次验证

5）发送文本+视频：输入满足要求的文本、视频进行一次验证

6）发送图片+视频：不支持发送

7）朋友圈发送内容是否有限制，例如涉及黄赌毒等敏感字

8）所在位置

   a、不显示位置：发送到朋友圈动态不显示位置

   b、选择对应位置：搜索支持、自动定位、手动编辑

   C、点击取消，返回上一级页面

9）谁可以看

   a、设置公开：所有朋友可见

   b、设置私密（仅自己可见）：自己查看朋友圈-可见、好友查看朋友圈-不可见

   c、设置部分可见（部分朋友可见）：选择的部分好友-可见、不被选择的好友-不可见、是否有人数上限

   d、设置不给谁看（选中的朋友不可见）：不被选中的朋友-可见、被选中的朋友-不可见、是否有人数上限

   e、点击取消，返回发送页面

10）提醒谁看

   a、提醒单人/提醒多人：被提醒的朋友-收到消息提醒、未被提醒-未有消息提醒

   b、是否有人数上限

   c、点击取消，返回发送页面

11）同步QQ空间：默认不同步、同步到QQ空间

12）取消发送朋友圈操作

   a、选择相机，点击取消，返回朋友圈页面

   b、进入朋友圈发送页面，选择文本图片，点击取消

13）朋友圈当天发送次数是否有上限限制

**朋友圈浏览功能**

1）文本查看：

   a、过长文本内容是否隐藏，并支持查看全文

   b、右键选择复制、收藏、翻译

   c、url链接是否支持点击跳转网页

2）图片查看

   a、小图右键支持收藏/编辑

   b、点击支持大图浏览

   c、选择发送给朋友、收藏、保存图片、编辑

   d、多张图片支持左右滑动浏览

3）视频查看

   a、右键视频支持静音播放/搜藏

   b、点击视频播放按键支持播放视频

   c、选择发送给朋友、收藏、保存视频、编辑

4）分享动态浏览：QQ空间/公众号文章/非腾讯产品分享后朋友圈是否正常显示

5）赞：点赞、取消点赞

6）评论

   a、评论长度：评论字数合理长度、评论超过字数上限

   b、评论类型：纯中文、纯数字、纯字母、纯字符、纯表情（微信表情/手机自带表情）、混合类型、包含url链接；

   c、评论是否支持复制粘贴

   d、为空验证

   e、发表评论后删除

   f、评论回复操作

7）删除朋友圈动态

8）更换相册封面

9）刷新是否正常获取新动态

10）上滑是否加载更多

#### 界面/易用性测试

1、技术人员角度：页面布局设计是否跟产品原型图/ui效果图一致

2、但除了考虑1之外，我们同样要考虑到用户使用：功能操作是否简便，页面布局排版风格是否美观合理，提示语相关信息是否易于理解

#### 中断测试

1、主要考虑：a)核心功能 b)当前功能存在实时数据交换，例发朋友圈、浏览朋友圈进行中断，是否容易出现崩溃

2、中断包括：前后台切换、锁屏解锁、断网重连、app切换、来电话/来短信中断、插拔耳机线/数据线

#### 网络测试

1、三大运营商不同网络制式测试

2、网络切换测试：WIFI/4G/3G/2G

3、无网测试：对于缓存在本地的数据，部分朋友圈信息是否支持浏览

4、弱网测试：

   a、延时：页面响应时间是否可接受、不同网络制式是否区分超时时长、出现请求超时，是否给予相应的提示

   b、丢包：有无超时重连机制、如果未响应，是否给予相应提示

   c、页面呈现的完整性验证

#### 兼容性测试

1、Android手机端、苹果手机端、pad版（主流）功能界面显示是否正常

2、各平台朋友圈展示数据是否一致

#### 安全测试

发送朋友圈时，文本输入脚本代码，是否出现异常

#### 性能测试

1、服务器性能测试

   可通过loadrunner/jmeter工具实现，主要关注TPS、响应时间、吞吐量、CPU、内存等

2、app客户端性能测试

   可通过GT工具实现，运行时关注cpu、内存、流量、电量等占用率

3、app压力稳定性测试

   通过monkey工具实现，频繁发送朋友圈，浏览朋友圈请求，是否容易发生崩溃

### 微信朋友圈点赞测试用例

<img src="https://img-blog.csdnimg.cn/20190705185436982.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDM2OTIxMg==,size_16,color_FFFFFF,t_70">

### 微信评论测试用例

#### 功能测试

- 是否可以评论
- 是否可以进行图片或者表情包或者语音评论
- 删除评论
- 多次评论会出现什么情况：是否可以都显示，是否可以按照时间顺序显示
- 是否可以与评论的好友正常回复消息
- 多人评论时的顺序是否按照时间顺序进行排列
- 评论是否显示头像和名称
- 评论之后退出该页面，再次进入朋友圈评论消息是否还存在
- 多用户评论，再次打开朋友圈是是否可以按照顺序看到是谁谁谁赞了我

#### 接口测试

- 评论之后相同好友是否收到提示信息
- 相同好友处的提示信息是否按照时间顺序
- 相同好友处的评论是否显示头像和名称
- 相同好友是否可以相互回复消息，交叉回复消息

#### 兼容测试

- 电脑端和手机端是否都可以进行评论功能
- 不同的移动端是否都可以进行评论功能（包括苹果，安卓）

#### 可用性测试

- 弱网的时候进行评论是什么情况
- 网络断开时是否可以评论
- 评论时有短信或电话进来，能否显示点赞情况
- 用户评论几秒后可以看到评论显示成功，取消同理
- 多用户同时给我评论时，我是否可以全部接收到提示消息

#### 安全性测试

- 评论是否会泄漏微信用户相关信息

### 测试播放视频（指标有哪些）

#### UI测试：

返回键位置是否正确；

视频标题文字、颜色、大小、位置等要素是否正确；

视频播放器页面位置是否正确、宽高比例是否合理、显示内容（默认状态图）是否正确；

课程简介、课程目录栏目位置、比例是否正确；

课程简介中：讲师头像、姓名、课程时间、观看人数、简介等要素是否正确；

开始学习按钮颜色、位置、大小（圆角）等要素是否正确；

收藏按钮位置、大小、颜色等要素是否正确

课程目录中章节名称、文字、下拉按钮位置、大小等要素是否正确；

页面其他要素是否与UI设计稿一致；

#### 功能测试：

返回按钮是否可以点击，是否可以成功返回上一级页面；

判断用户是否登录、是否已购买该课程，未登陆状态、未购买下不可以进入播放界面，提示用户去登录（未注册的用户提示用户先注册）/去购买；

判断当前视频是否为免费，如果为免费所有人都可以看，为付费时需要判断用户是否已经购买；

点击视频播放按钮或者开始学习按钮时视频是否正常播放，暂定时是否可以暂停，再次播放时是否同步上一次暂停的位置播放；

视频中断测试：视频快进、快退是否有卡顿、延时现象

播放时突然来电话或者手机关机等情况下，是否会保存播放进度；

视频播放时切换到后台，视频是否暂停，再次返回视频是否是暂停状态；

视频播放时直接杀死进程，视频播放结束，是否保留播放进度，下次进入是否同步上一次的观看位置/还是重新播放、进度清零；

播放视频A的时候切换到视频B，再次返回视频A是否继续上次进度播放，还是从头开始；

音量大小按钮是否能够使用；

视频最大化（全屏）、最小化是否正常使用，切换状态时视频是否会发生卡顿/延时；

视频当前章节播放完成后切换下一章节是否自动切换，还是需要手动切换（具体根据产品原型来分析）

手机横竖屏切换时播放状态是否会有卡顿、延时、闪退等情况；

#### 兼容性测试：

平台兼容性：Android、Ios、iPad…

系统兼容性：Android4.0—10.0、Ios8.0 – 12；

屏幕分辨率测试：Android需要多注意因为屏幕尺寸存在碎片化，需要考虑视频的适配效果是否OK；

播放器是否与其他类型播放器冲突（需要考虑播放的时候是否和音频等相互冲突）

#### 网络测试：

网络切换测试：WIFI、移动网络；

弱网测试：弱网情况下视频播放是否有卡顿、黑屏、闪退等情况；

无网络状态下进入是否会有相关提示

播放过程中网络切换是否有相应提示；

移动网络状态下播放是否会提示用户当期为非WIFI播放，是否切换；

播放过程中网络终端，播放完已经加载的部分后停止播放，且有相应提示；

#### 易用性测试：

界面是否简洁，一目了然（比如：视频标题、片头、片尾、视频图像等界面）

快捷键是否方便：快进、快退…

菜单栏是否正确、方便使用

图像是否清楚，切换清晰度情况下视频播放是否正常，是否有卡顿、黑屏、闪退等情况

拖拽进度条使用起来是否友好

视频是否具备视频记忆功能/是否保存播放进度；

能否保存已观看的视频列表

### 购物车测试用例

####  功能测试

1.购物车是否可以添加商品

2.购物车的优惠券是否可以使用

3.购物车的计算结果是否正确

4.如果使用购物券购物车里面的价格是否发送改变

5.未登录时购物车是否可以正常显示

6.如果没有登录会不会让你登录之后才可以使用

7.所有的页面链接功能是否正常，是否可以正确跳转到指定页面

8.商品没有勾选时结算按钮是否可以点击

9.购物车页面时用户是否可以取消订单，或者进入订单和客服进行聊天

10.卖家在线时是否显示在线

11.购物车添加的商品是否可以有数量上限

12.购物车点击几件商品时点击结算会不会跳转到支付页面

13.是否可以批量删除商品

14.如果没有在指定时间下单，订单会不会自动失效并在购物车清除该商品信息

15.可否对添加的商品是否可以进行 增加

16.商品信息过长是否可以显示完整

17.商品是否可以进行收藏并推荐相似的商品（宝贝）

18.购物车中的降价商品，库存紧张商品是否成功分类

19.购物车商品降价时，购物车是否显示降价信息

#### 性能测试

20.打开购物车这个页面需要多长时间

21.弱网时是否还可以进行添加商品，计算商品的价格并且可以正常结算

22.无网状态下是否提醒请检测你的网络设置

23.用户过多会不会使购物车服务器崩溃

24.编辑购物车：删除、添加商品需要的时间。

25.在购物车页面选择需要购买的商品进行结算的时候，结算金额可不可以实时显示。

26.清空失效商品需要的时间。

#### 兼容性测试

27.ios:不同型号，不同ios的手机系统的耗电情况，打开速度，安装后是否闪退，卸载

28.安卓：不同品牌，不同型号，不同的安卓系统，手机系统的耗电情况，打开速度，安装后是否闪退，卸载

29.web端的打开速度

#### 界面测试

30.购物车界面是否完善

31.各个功能的设计是否美观 ，大小是否合适

32.页面的功能按钮可以正常显示。

33.商品的最下方显示失效宝贝。

34.页面的最低端显示“你可能喜欢”

35.购物车中如果存在有商品降价、库存不足、限购件数等，在商品详情的下面，会有对应的字体展示

#### 安全性测试

36.用户实名认证后个人信息是否会泄露

37.是否需要绑定手机号

#### 易用性测试

38.是否方便人们操作

39.是否有免密码支付功能

40.是否具有青少年模式

### 如何测试一个矿泉水瓶？

#### 功能测试

对于矿泉水瓶来说，功能测试主要就是测试水瓶的装水、喝水的功能，具体如下：
 1）检查水瓶在装少量水、半瓶水、装满水的情况下是否会漏水；
 2）检查水瓶在装少量水、半瓶水、装满水的情况下能否喝到水；
 3）在瓶盖拧紧不漏水的情况下，分别让成年男性、成年女性和小孩尝试拧开瓶盖，看是否成功；

#### 性能测试

对于矿泉水瓶来说，性能测试主要是测试水瓶的抗摔、抗压、抗高低温等情况，具体如下：
 1）将空瓶、半瓶水、满瓶水分别从不同的高度摔下来，看瓶子是否摔坏；
 2）成年人从各种角度按压空瓶，看瓶子是否漏水或破裂；
 3）将空瓶和半瓶水、满瓶水分别放置于冰箱、室内和太阳光下一段时间，观察瓶子是否漏水，瓶身是否破裂；

#### 安全性测试

对于矿泉水瓶来说，安全性测试主要是测试水瓶使用时是否会伤害到人、是否产生对人体有害物质等，具体如下：
 1）用手去抚摸瓶身的内壁和外壁，是否感觉光滑舒适不刺手；
 2）用矿泉水瓶喝水，并转动瓶口，感受瓶口是否圆滑；
 3）空瓶长时间放置一段时间，看是否产生塑化剂或细菌；
 4）矿泉水瓶分别装满不同液体（水、碳酸饮料、果汁等），放置一段时间，看瓶身是否与液体之间发生化学反应，是否产生有毒物质或细菌；
 5）矿泉水瓶中装入热水（或放入微波炉），观察瓶子是否变形，是否有异味产生

#### 外观测试

对于矿泉水瓶的外观测试——主要是两方面，水瓶的大小、水瓶外观设计，那具体一点来说，我们可以列举出以下一些用例：
 1）瓶子的高度、底座是否符合设计要求；
 2）瓶子的口径是否符合设计要求；
 3）瓶身上的字体颜色、大小是否符合设计要求，是否有错别字；
 4）瓶身上的纹路是否符合设计要求；
 5）瓶身上图标位置、间距是否符合设计要求；
 6）瓶子是否有异味；

#### 易用性测试

1）用手轻拿装满水的瓶子，看是否轻易掉落，是否有防滑措施；

2）矿泉水瓶分别装入不同温度的水，用手感受瓶身温度，看是否会烫手；

3）分别将水瓶放在手中、口袋、包包、车上等不同位置，看是否方便携带

#### 兼容性测试

1）瓶中分别装入碳酸饮料、果汁、咖啡、茶水等液体，方式一段时间后看是否变味；

2）瓶中是否可以装入固体

### 怎么理解测试？你认为什么是测试？

测试是无处不在的，撇开软件，从生活来看比如买回来一个东西，会去检查质量问题，考试交卷前会检查等其实这都是在测试，目的就是为了发现错误，避免影响应用体验。回到程序中，测试是产品上线的最后一道把关，如果测试工作做得到位，就能避免很多的问题，像复工后钉钉系统短崩、12306高峰期买票老进不去，这其实就是性能做的不够好，测试人员在性能测试时也没测出来它的饱和值，所以说，测试在软件中是非常必要的，可以找出软件中存在的问题。

### 软件测试的流程？

**软件测试的流程包括：**

> 1、测试需求分析阶段；
>
> 2、测试计划阶段；
>
> 3、测试设计阶段；
>
> 4、测试执行阶段；
>
> 5、测试评估阶段。

1、测试需求分析阶段：阅读需求，理解需求，主要是对业务的学习，分析需求点，参与需求评审会议。

2、测试计划阶段：主要任务是编写测试计划，参考软件需求规格说明书，项目总体计划，内容包括测试范围（来自需求文档），进度安排，人力物力的分配，整体测试策略的制定。风险评估与规避措施有一个制定。

3、测试设计阶段：主要是编写测试用例，会参考需求文档（原型图），概要设计，详细设计等文档，用例编写完成之后会进行评审。

4、测试执行阶段：搭建环境，执行冒烟测试（预测试），然后进入正式测试，bug管理直到测试结束。

5、测试评估阶段：出测试报告，确认是否可以上线。

### 测试和开发的区别？测试和测开的区别？

**测试和研发：**两者在工作职责、难易程度、技能要求等方面都有所不同。测试主要职责是找出程序中存在的问题，相对开发来说广度大专业度低，技能要求更广泛，像测试手段以及测试工具使用代码走读、业务和架构分析以及用户需求方面都要有所掌握。研发的主要职责是实现产品的功能，相对测试来说广度低专业度高，专业技能要求也更高。工作环境基本类似、在敏捷开发下，两者的压力也差不多。

**测试和测开：**功能性测试主要是手工的去执行写好的测试用例，验证实际输出和预期结果是否一致。而测试开发是把手工要做的活编写成自动化测试脚本，代替手工测试的这个过程。

### 你提交了一个bug，开发不认为这是bug，你该怎样处理这个冲突?在你看来,怎样的bug开发觉得不是bug?

开发认为这不是bug,可能是需求不明确，我和开发产生了歧义，可以找产品经理确认一下需求，然后再决定要不要修改。也有可能是我把bug描述不清，这个时候我会像开发解释我确定它是bug的依据是什么，站在用户的角度去评判看会不会影响使用体验，如果开发依然认为这不是bug，可以发起bug评审，像项目评审同行评审和用户评审。同时也要提升自己的业务能力，尽可能的附上bug相对应的解决方案。

### 产品上市前你发现了bug你会怎么做？会让产品上市吗？为什么？

首先看bug的等级，如果是影响使用的功能性bug，必须得辛苦开发人员及时修改，如果是不影响功能的建议性的bug，时间允许的话尽量完善后在上线，要是时间不允许，可以先上线，因为现在产品迭代更新比较快，可以再下一次的版本中进行修复。

### 测试和研发的生命周期？测试的流程？

研发的生命周期首先是对问题进行定义规划，讨论产品可行性，在进行需求分析，根据需求分析的结果对整个系统进行软件设计，比如数据库设计框架设计，设计完成以后就可以开始进行程序编码了，然后进行软件测试发现bug并加以纠正，最后进行长期的运行维护，主要包括纠错性维护和改进型维护。

测试的生命周期（我觉得流程也是这，不知道认识有偏差没）：先进行需求分析得出测试需求，测试计划阶段根据需求编写测试计划，测试设计主要搭建测试用例框架编写具体的测试用例，测试执行阶段就是拿自己写的测试用例去执行，最后是测试评估编写具体的测试报告。

### 说一下自动化测试和非自动化测试？

自动化测试包括功能自动化、性能自动化、安全自动化。我们平常说的指功能自动化，就是把手工测试用例转化成脚本实现，主要是为了把人从重复的活动中解放出来，主要用于回归测试，出错率低。而非自动化测试就是手工去测试，执行效率慢，量大的时候容易出错，两者不可相互替代，他们是相辅相成的。

### 编写测试报告的主要元素？

应包括测试背景、测试范围、测试环境、测试方法、测试结果说明还有质量或风险评估。

### 编写测试用例的方法？

主要包括白盒测试（逻辑覆盖、循环覆盖、基本路径覆盖）和黑盒测试（等价类、边界值、错误推测法、因果图法、场景法、状态图、随机测试）

### 测试终止的条件是什么？结束的标准？

系统在一定性能下平稳运行72小时，在bug提交平台里不存在一般级别以上的bug,普通bug数量不超过3个，bug的修复率在90%以上，项目经理和测试经理签字通过了这个版本。

### 测试用例的要素？怎样的测试用例是好的测试用例？

测试用例的要素包括测试编号、模块名称、编写人和编写日期、操作说明、输入数据以及预期结果。好的测试用例是一个完备的集体，能够完全覆盖测试要求、等价类的划分也要准确。

### 你认为一个优秀的测试人员应具备什么优点？

我认为一个优秀的测试人员首先应该对测试有很浓厚的兴趣，对待工作有很强的责任感和压力感；思维方面应该不走寻常路，从逆向去发现问题；同时也应该具备一定的开发能力和文字功底，保证写出来的测试用例清晰可行；也应有很好的沟通能力，和周围的同时能很好地交流。

### 一个测试工程师应该具备哪些素质和技能?

　1-掌握基本的测试基础理论

　2-本着找出软件存在的问题的态度进行测试，不要以挑刺的形象出现

　3-可熟练阅读需求规格说明书等文档

　4-以用户的观点看问题

　5-有强烈的质量意识

　6-细心和责任心

　7-良好的有效的沟通方式(与开发人员及客户)

　8-具有以往的测试经验能够及时准确的判断出高危险区在何处

### 说一下敏捷模型？敏捷模型需要开那些会议？

敏捷开发是当下很流行的一种开发模式，主要特点是周期短迭代快，Scrum是当下比较常用的一种方式，它主要包括三个角色，product owner是产品经理，负责整理和讲解use story(用户故事)，制定这一期迭代要完成的任务，scrum master是项目经理，负责召开各种会议，成员在会议里回答任务进度和所遇到的问题，team是研发团队，由不同技能的成员组成，共同完成每一次迭代。

常开的会议包括四个，迭代计划会议主要是讨论这一期迭代应该完成哪些目标、每日例会主要是团队成员回答任务进度还有今天要完成什么、演示会议就是迭代完成后相关人员演示迭代的成果、回顾会议是对本期迭代进行总结并制定改进计划。

### 讲一下你知道的开发模型和测试模型？

开发模型有瀑布模型、螺旋模型、增量迭代、敏捷开发；瀑布模型是线性进行的，适用于需求稳定或者公司已有类似产品的项目，它强调开发的阶段性，缺点是不能适应后期需求的多变性，发现缺陷也比较晚造成修复成本太高；螺旋模型是一个渐进式模型，它适合规模庞大、复杂度高风险高的项目，强调每个开发阶段的质量，因为它引入了非常严格的风险识别，这就需要大量人员和资金的投入，影响项目的进度；增量和迭代目的是减少项目风险；现在大部分公司都用的是敏捷开发模型，主要特点是周期短迭代快，Scrum是当下比较常用的一种方式，它主要包括三个角色，product owner是产品经理，负责整理和讲解use story(用户故事)，制定这一期迭代要完成的任务，scrum master是项目经理；

测试模型有四种,vwhx,常用的有v模型和w模型，v模型以编码为分界点，明确的标注了测试过程中存在的不同测试类型，开发阶段和测试阶段有明确的对应关系；但它仅仅把测试过程放在需求分析、系统设计之后的一个阶段，忽视了测试对需求的分析和验证；w模型由两个v模型组成，代表了开发和测试两条线并行；测试的对象不仅仅是程序，需求设计同样也要测试，有利于尽早全面的发现问题；但需求、设计、编码等活动被视为是串行的，测试和开发活动也保持着一种线性的前后关系，上一阶段完全解除，才可正式开始下一阶段的工作不能够很好的支持迭代的开发模型，无法支持敏捷开发模式；

### 为什么选择测试开发？

首先，我认为的测开是测试和开发工作都在做的。一方面，据我了解，在近几年，国内对软件测试越来越重视，并且从用户角度来说，对于同类产品，可能会更加注重产品的质量和服务，所以我觉得测试的发展前景是非常好的。其次，测试在一个项目开发的过程中是非常重要的一环。测试人员的责任非常大，责任越大成就感就越大。我很喜欢这样的工作。另一方面，测开还有一部分开发工作，无论是自动化脚本还是测试工具或框架，都提高了测试的效率，为质量效率保证工作提供了有力的保障。并且测开的所需技术广度也是很高，所以我认为测开会激发我对这个岗位的热爱和持续学习的态度。（并且来说，我目前具备了一些测开所必备的理论知识和技能并且还在不断地学习中，我认为我可以较快地胜任这个岗位。）

### 怎么理解测试开发？

首先从岗位名字来看，要求测开工程师即要懂测试，又要懂开发。其次这个岗位融合了开发角色和质量意识，要求我们兼具开发人员的技能和测试人员的思维。总的来说，测试开发工程师的定位就是保障产品的质量和提高测试的效率。

### 怎么理解测试？

测试是无处不在的，撇开软件，从生活来看比如买回来一个东西，会去检查质量问题，考试交卷前会检查等其实这都是在测试，目的就是为了发现错误，避免影响应用体验。回到程序中，测试是产品上线的最后一道把关，如果测试工作做得到位，就能避免很多的问题，像复工后钉钉系统短崩、12306高峰期买票老进不去，这其实就是性能做的不够好，测试人员在性能测试时也没测出来它的饱和值，所以说，测试在软件中是非常必要的，可以找出软件中存在的问题。

### 自动化测试目的到底是什么？（携程测开）

- 优化测试速度：可非常快速的运行上万条记录
- 提高准确性、稳定性：可以不为外界因素干扰，准确运行测试用例
- 确定性：能真实快速搭建测试环境，测试数据，重现缺陷
- 提高工作效率：一边运行自动化测试，一边准备测试报告
- 测试环境搭建：可以结合多种编程语言及技术协助搭建测试环境，防止手工测试重复劳动，如批处理技术
- 提高技能：可提高测试人员技能，同时提高对测试的兴趣，防止对手工测试感觉枯燥

### 常用的测试方法？（携程测开）

#### 按照测试设计方法分类

- **黑盒测试（Black Box）**

测试内容：黑盒测试是把测试对象看做一个黑盒子，利用黑盒测试法进行动态测试时，需要测试软件产品已经实现的功能是否符合功能设计要求，不需测试软件产品的内部结构和处理过程。
　　黑盒测试注重于测试软件的功能性需求，也即黑盒测试使软件工程师派生出执行程序所有功能需求的输入条件。黑盒测试并不是白盒测试的替代品，而是用于辅助白盒测试发现其他类型的错误。

- **白盒测试（White Box）**

测试内容：设计者可以看到软件系统的内部结构，并且使用软件的内部知识来指导测试数据及方法的选择。
　　白盒测试通常被认为是单元测试与集成测试，期中有六种测试方法：语句覆盖、判定覆盖、条件覆盖、判定/条件覆盖、条件组合覆盖。

- **灰盒测试（Gray Box）**

测试内容：介于黑盒和白盒之间，是一种综合测试的方法，他将白盒测试和黑盒测试结合在一起，构成一种无缝测试技术。
　　灰盒测试是基于程序运行时的外部表现又结合程序内部逻辑结构来设计测试用例，执行程序并采集程序路径执行信息和外部用户接口结果的测试技术。灰盒测试法旨在验证软件满足外部指标以及软件的所有通道或路径都进行了检验。

#### 按照测试是手动还是自动分类

- **手动测试（Manual Test）**　　

测试内容：测试人员用鼠标去手动测试 （测试GUI），用鼠标各种点点点，手工测试更能容易发现软件的Bug。

- **自动化测试（Automation Test）**

测试内容：用程序测试程序 （测试API），由测试人员根据手工测试的Case来决定自动化测试的Case，再编写程序或者脚本来替代手工做自动化测试

#### 按照测试的目的分类

- **功能测试**
- **非功能测试**

测试内容：一个软件除了基本功能之外，还有很多功能之外的特性，这些叫“Quality of Service requirement”服务质量需求。没有软件的功能，这些特性都无从表现出来，因此，我们要在软件开发的适当阶段-基本功能完成后做这些测试。

- **性能测试**
- **安全性测试**

#### 按照阶段分类（百度测开）

**单元测试**：是指对软件中的最小可测试单元进行检查和验证。桩模块（stud）是指模拟被测模块所调用的模块，驱动模块（driver）是指模拟被测模块的上级模块，驱动模块用来接收测试数据，启动被测模块并输出结果。

**集成测试**：是单元测试的下一阶段，是指将通过测试的单元模块组装成系统或子系统，再进行测试，重点测试不同模块的接口部门。集成测试就是用来检查各个单元模块结合到一起能否协同配合，正常运行。

**系统测试**：指的是将整个软件系统看做一个整体进行测试，包括对功能、性能，以及软件所运行的软硬件环境进行测试。系统测试的主要依据是《系统需求规格说明书》文档。

**验收测试**：指的是在系统测试的后期，以用户测试为主，或有测试人员等质量保障人员共同参与的测试，它也是软件正式交给用户使用的最后一道工序。 验收测试又分为a测试和beta测试，其中a测试指的是由用户、 测试人员、开发人员等共同参与的内部测试，而beta测试指的是内测后的公测，即完全交给最终用户测试。

#### 按照测试策略分类

- Regression Test 回归测试：对一个新的版本，重新运行以往的测试用例，看看新版本和已知的版本相比是否有退化 (regression)
- Ad hoc Test 探索性测试：随机进行的，探索性的测试。
- Sanity Test：粗略的测试， 只需要执行部分的测试用例（比如很多Web网页，确定比较重要以及常用的URL链接是活着的，能正常打开返回数据）

**Regression Test 回归测试**

对软件测试人员来说就是重复测试，所以回归测试最好是自动化的，否则测试人员就要一遍又一遍地重复测试：　

- 开发人员做些小改动，就需要测试人员做回归测试。确保现有的功能没有被破坏
- Bug Fix 也需要回归测试，确保新的代码修复了Fix, 也确保现有的功能没有被破坏
- 项目后期，需要做一个完整回归测试，确保所有的功能都是好的

**Ad hoc Test 探索性测试**
　　平常我最喜欢做随机测试了， 抛开test case. 自己按照自己的思路，随便点点。 如果测试GUI，Ad hoc能发现大量的bug。这个主要是基于测试人员对软件系统的了解以及测试人员自己个人的测试经验积累，差不多行成了一种习惯性的操作

### 什么是高质量软件？

首先，与需求一致，且易于用户使用。

其次，如果一个软件开发程度在70%以上的情况下，加入一个新功能，还需要涉及到大量的文档和代码的修改、有大量的修改提交，那么这个软件架构一定很烂。而好的架构此时应该已经完成大部分底层组件的开发，而且相互独立，加入的大部分新功能基本上是原有组件的功能的组合（不涉及组件内部的修改，而不是在根据新功能，无休止的扩充组件的参数），以及加入新功能特有的独立组件。

> <font color='blue'>具体指标如下：</font>
>
> **功能性：**软件所实现的功能满足用户需求的程度．功能性反映了所开发的软件满足用户称述的或蕴涵的需求的程度，即用户要求的功能是否全部实现了。
> 可靠性：在规定的时间和条件下，软件所能维持其性能水平的程度。可靠性对某些软件是重要的质量要求，它除了反映软件满足用户需求正常运行的程度，且反映了在故障发生时能继续运行的程度。
>
> **易使用性：**对于一个软件，用户学习、操作、准备输入和理解输出时，所做努力的程度。易使用性反映了与用户的友善性，即用户在使用本软件时是否方便。
>
> **效率：**在指定的条件下，用软件实现某种功能所需的计算机资源（包括时间）的有效程度。效率反映了在完成功能要求时，有没有浪费资源，此外"资源";这个术语有比较广泛的含义，它包括了内存、外存的使用，通道能力及处理时间。
>
> **可维修性：**在一个可运行软件中，为了满足用户需求、环境改变或软件错误发生时，进行相应修改所做的努力程度。可维修性反映了在用户需求改变或软件环境发生变更时，对软件系统进行相应修改的容易程度。一个易于维护的软件系统也是一个易理解、易测试和易修改的软件，以便纠正或增加新的功能，或允许在不同软件环境上进行操作。
>
> **可移植性：**从一个计算机系统或环境转移到另一个计算机系统或环境的容易程度。

### 如何保证软件的质量？

1. **质量管理**
   1. 代码质量
   2. 让用户参与UAT测试，保证用户体验（使用质量）
   3. 引入QA，保存过程环节质量
   4. 系统测试工程师保证系统质量满足需求
2. **测试人员人员的质量保证**
   1. 测试策略：质量是多维度的，功能测试、性能测试、兼容性测试等多种测试类型的结合
   2. 用例质量：采用合适的用例方法，如何进行需求分析，用例评审
   3. 执行质量：如何保证执行深度（界面、关联模块、数据库、日志）与广度（系统测试类型）
   4. 缺陷质量：Bug评审，引入合适的Bug流程
   5. 过程质量：合理的软件测试流程，测试过程监控
