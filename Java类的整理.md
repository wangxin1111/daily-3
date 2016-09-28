#Java类的整理

=================================

* ArrayList

  * ArrayList实现了长度可变的数组，在内存中分配连续的空间，是一个可动态维护长度的集合。

* Arrays

  * 包含用来操作数组（比如排序和搜索）的各种方法。此类还包含一个允许将数组作为列表来查看的静态工厂.

* Boolean

  * Boolean是基本数据类型的包装类，Boolean类在对象中包装了一个基本类型boolean的值。

* Byte

  * Byte是基本数据类型的包装类，Byte类在对象中包装了一个基本类型byte的值。

* Character

  * 用一个char类型的量生成一个Character对象

* Calendar

  * 该类是一个抽象类， 可以使用GregorianCalendar类将其实例化，也可以通过getInstannce()方法来创建对象，可以将时间精确到毫秒值。在处理日期和时间时,系统推荐使用Calendar，其功能比Date类强大很多,也比Date复杂。

* Class

  * Class类的实例表示正在运行的Java应用程序的类和接口，没有公共构造方法

* Clone

  * ​

* Collection

  * 存储一组不唯一，无序的对象

* Double

  * Double是基本数据类型的包装类，Double类在对象中包装了一个基本类型double的值。

* Date

  * 位于java.util包中，用一个long类型的值来表示一个指定的时刻。

* DateFormat

  * 是一个抽象类,位于java.text包中,表示日期的格式化类,可以将一个日期按照指定的风格进行格式化.

* Error

  * 通常出现重大问题如：运行的类不存在或者内存溢出等；不编写针对代码对其处理。

* Exception

  * 在运行时函数出现的一些情况，可以通过try、catch、finally。

* Float

  * Float是基本数据类型的包装类，Float类在对象中包装了一个基本类型float的值。

* HashMap

  * 无序存放的，是新的操作类，key不允许重复。

* HashSet

  * HashSet是Set接口的一个子类，主要的特点是：里面不能存放重复元素，而且是采用散列的存储方式，所以是没有顺序的。

* HashTable

  * 无序存放的，是旧的操作类，key不允许重复。

* Integer

  * Integer是基本数据类型的包装类，Integer类在对象中包装了一个基本类型int的值。每个Integer类型的对象包含一个int类型的字段。

* Iterator

  * 迭代器

* List

  * 可以进行双向输出，通过索引获取对象，存储一组不唯一，有序（插入顺序）的对象

* Long

  * Long是基本数据类型的包装类，Long类在对象中包装了一个基本类型long的值。

* LinkedList

  * LinkedList采用链表存储方式，在集合任何位置（头部、中间、尾部）添加、获取、删除对象。

* LinkedHushMap

  * ​

* Map

  * 动态可维护长度，可通过关键字检索，存储一组键值对象，提供key到value的映射 

* Math

  * Math类表示的是数学的计算操作。

* Matcher

  * Matcher类主要是执行规范，验证一个字符串是否符合其规范。

* Number

  * Number (Java 2 Platform SE 6)


    抽象类Number是 BigDecimal、BigInteger、Byte、Double、Float、Integer、Long 和 Short 类的超类。 Number的子类必须提供将表示的数值转换为 byte、double、float、int、long 和 short 的方法。 

* Object

  * 类Object是类层次结构的根类

* Pattern

  * Pattern类的主要作用是进行正则规范（如之前的“[0-9]”就属于正则规范）的编写

* Random

  * Random类中实现的随机算法是伪随机，也就是有规则的随机，它可以产生int、long、float、double等类型的随机数。

* String

  * String类位于java.lang包中，具有丰富的方法  计算字符串的长度、比较字符串、连接字符串、提取  字符串

* Short

  * Short是基本数据类型的包装类，Short类在对象中包装了一个基本类型short的值。

* Set

  * 不能加入重复的元素，存储一组唯一，无序的对象。

* StringBuffer

  * String增强版，类似于String的字符串缓冲区

* StringBuilder

  * String增强版，类似于String的字符串缓冲区

* System

  * 位于java.lang包中，代表系统，系统级的很多属性和控制方法都放置在该类的内部。该类的构造方法是private的,无法实例化该类，其内部的成员变量和方法都是静态的

* Scanner

  * 
    Scanner`使用分隔符模式将其输入分解为标记，默认情况下该分隔符模式与空白匹配。然后可以使用不同的 next 方法将得到的标记转换为不同类型的值。 

* SimpleDateFormat

  * 是一个以国别敏感的方式格式化和分析数据的具体类.主要功能是完成日期显示格式的转换。

* Thread

  * 专门用来创建线程的类

* TreeSet

  * 对输入的数据进行有序排列

* TreeMap

  * 可以排序的Map集合，按集合中的key排序，key不允许重复。

* Vector

  * Vector类属于一个挽救的子类，是List子类

* Void

  * 
    Void 类是一个不可实例化的占位符类，它持有对表示 Java 关键字 void 的 Class 对象的引用。 