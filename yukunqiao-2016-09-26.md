# 2016-09-26工作日报
====================

*学习内容：

  * (1)常用类——Math类，Random类，Arrays类，System类，Date类，Calendar类
   *       ——String类，StringBuffer类
   
   *(2)API——对以上类参照API中的构造方法和方法构造方法，进行代码的练习以及方法的理解


1.已完成的工作内容

 * 常用类——Math类，Random类，Arrays类，System类，Date类，Calendar类，String类，StringBuffer类
    的基本掌握
    
  * String类在22号已进行练习

2.工作成果

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

 * 
  
5.遇到的问题及解决方法

 * Math.getExponent
