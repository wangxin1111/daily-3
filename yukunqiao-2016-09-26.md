# 2016-09-26工作日报
====================

* Random类中实现的随机算法是伪随机，也就是有规则的随机，它可以产生int、long、float、double等类型的随机数。
* Random对象的生成
  * public  random():该构造方法使用一个和当前系统时间对应的相对时间有关的数字作为种子数，然后使用这个种子数构造Random对象。
  * public random(long seed):该构造方法可以通过制定一个种子数进行创建。
* Random方法说明：
  * public int nextInt(int n)
    * 取出不大于n的整数
  * public float nextFloat()
    * 取出小数
  * public double nextDouble(double d)
    * 生成一个随机的double值，介于[0,1.0]之间
* Arrays类简介:
  * 此类包含用来操作数组（比如排序和搜索）的各种方法。此类还包含一个允许将数组作为列表来查看的静态工厂.
* Arrays排序语法：
  * 方法：Arrays.sort(<数组名>)；
  * sort()是Arrays类的一个排序方法，默认为升序。
* System类
  * 位于java.lang包中，代表系统，系统级的很多属性和控制方法都放置在该类的内部
  * 该类的构造方法是private的,无法实例化该类，其内部的成员变量和方法都是静态的
* Date类
  * 位于java.util包中，用一个long类型的值来表示一个指定的时刻。
* Date类的两个构造方法：
  * public Date() :无参构造器，使用系统当前时间的毫秒数来创建Date对象，它调用了java.lang.System类的currentTimeMillis()来取得系统的当前时间的毫秒值。
  * public Date(long date) :根据给定的毫秒数来创建一个与之对应的Date对象，这个毫秒数决定了被创建对象的年、月、日、时、分、秒属性的值。
* Date方法:
  * public  void setTime(long time):设置毫秒数值
  * public  long getTime():表示返回Date对象的long值
* Calendar类
  * 该类是一个抽象类， 可以使用GregorianCalendar类将其实例化，也可以通过getInstannce()方法来创建对象，可以将时间精确到毫秒值。
  * 在处理日期和时间时,系统推荐使用Calendar，其功能比Date类强大很多,也比Date复杂。
* Calendar方法的介绍:
  * public  final void set(int year,int month,int date)：此方法用来设置时间的值(*月份的值为实际的月份减1)
  * public final Date getTime():该方法将Calebdar类型的对象转化为Date类对象
* DateFormat类:
  * 是一个抽象类,位于java.text包中,表示日期的格式化类,可以将一个日期按照指定的风格进行格式化.
* ​


* 代码

 import java.lang.Math;

   public class ApiMath {

      public static void main(String[] args){  

         double i = Math.E;
         double j = Math.PI;  
         
         double index1 = Math.abs(3.0);      
         float index2 = Math.abs(3);      
         int index3 = Math.abs(3);      
         long index4 = Math.abs(3); 
         
         double index1 = Math.cos(0.99);
         double index2 = Math.cosh(0.99);
         double index3 = Math.sin(0.99);
         double index4 = Math.sinh(0.99);
         double index5 = Math.tan(0.99);
         double index6 = Math.tanh(0.99);
         double index = Math.acos(1.1);//参数为NaN或者绝对值大于1，结果为NaN
         double index1 = Math.acos(0.1);
         double index2 = Math.asin(1.1);
         double index3 = Math.asin(0.1);
         double index4 = Math.atan(1.1);
         double index5 = Math.atan(0.1);
         double index6 = Math.atan2(0.9,0.5);
         /*如果任一参数为 NaN，那么结果为 NaN。
         如果第一个参数为正 0，第二个参数为正数；
             或者第一个参数为正的有限值，第二个参数为正无穷大，那么结果为正 0。
         如果第一个参数为负 0，第二个参数为正数；
             或者第一个参数为负的有限值，第二个参数为正无穷大，那么结果为负 0。
         如果第一个参数为正 0，第二个参数为负数；
             或者第一个参数为正的有限值，第二个参数为负无穷大，那么结果为最接近 pi 的 double 值。
         如果第一个参数为负 0，第二个参数为负数；
             或者第一个参数为负的有限值，第二个参数为负无穷大，那么结果为最接近 pi 的 double 值。
         如果第一个参数为正数，第二个参数为正 0 或负 0；
             或者第一个参数为正无穷大，第二个参数为有限值，那么结果为最接近 pi/2 的 double 值。
         如果第一个参数为负数，第二个参数为正 0 或负 0；
             或者第一个参数为负无穷大，第二个参数为有限值，那么结果为最接近 -pi/2 的 double 值。
         如果两个参数都为正无穷大，那么结果为最接近 pi/4 的 double 值。
         如果第一个参数为正无穷大，第二个参数为负无穷大，那么结果为最接近 3*pi/4 的 double 值。
         如果第一个参数为负无穷大，第二个参数为正无穷大，那么结果为最接近 -pi/4 的 double 值。
         如果两个参数都为负无穷大，那么结果为最接近 -3*pi/4 的 double 值。*/
         
         double index1 = Math.cbrt(1.11);//立方根
         double index2 = Math.cbrt(-1.11);
         
         double index = Math.ceil(2.542);
            //返回最小的（最接近负无穷大）double 值，该值大于等于参数，并等于某个整数
         double index1 = Math.floor(2.542);
            //返回最大的（最接近正无穷大）double 值，该值小于等于参数，并等于某个整数。
            
         float index1 = Math.copySign(43,-144);
         double index2 = Math.copySign(43.00,144.00);
         
         double index1 = Math.exp(1.2);
         double index2 = Math.expm1(1.2);
         
         int index1 = Math.getExponent(0);
         int index2 = Math.getExponent(3);
         
         double index = Math.hypot(1.1,4.4);//返回 sqrt(x2 +y2)
         
         double index = Math.IEEEremainder(1.02,1.01);// f1 - f2 × n

  }

 }

3.未完成的工作

* Random类，Arrays类，System类，Date类，Calendar类，StringBuffer类
    的API练习
* 8种基本数据类型对应类的API练习

4.未完成的原因

* ​

5.遇到的问题及解决方法

* Math.getExponent
