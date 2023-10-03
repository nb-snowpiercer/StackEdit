
# 第一章 Java简介

### 主要内容

1.  Java的起源与发展
    
2.  Java平台与开发环境
    
3.  Java程序的基本结构
    
4.  Java文档风格与注释
    

## Java起源与发展

-   最初是由美国Sun Microsystems公司的James Gosling等人开发。
    
-   语言最初取名为Oak
    
-   Java在1995年5月23日正式发布
    
-   Java随着互联网的迅猛发展而发展，逐渐成为主要的网络编程语言。
    
-   Java在TIOBE世界编程语言排行榜中一直处于前列。
    

## Java语言的变化趋势

1、Java平台有三大版本，分别代表Java的三个应用领域。

-   Java标准版（Java Standard Edition，Java SE）
    
-   Java企业版（Java Enterprise Edition，Java EE）
    
-   Java微型版（Java Micro Edition，Java ME）
    

## Java程序的基本结构

```
/*  
多行注释,第一个Java程序  
*/  
public class HelloWorld   //一行注释，类名  
     {   
         public static void main(String[] args){  
              System.out.println("Hello,World!");    
         }  
     }  
/**  
文档注释  
*/
```

## 练习题

1.  编写程序，打印输出你的姓名和年龄。
    
```
   /*  
   输入姓名和年龄，并打印出姓名和年龄  
   */  
     
   public class Test1  
   {  
       public static void main(String[] args)  
       {  
        Scanner sc = new Scanner(System.in);  
        String name = sc.next();  
        int age = sc.nextInt();  
           System.out.print(name+"\n");  
           System.out.print(age);  
       }  
   }
```
2.  编写程序，使用以下公式计算并显示半径为5.5的圆面积和周长。
    

$$  
area = \pi \times radius ^2 \\ perimeter = 2 \times \pi \times radius  
$$

  
```
/*  
计算圆的面积和圆周长度。  
*/  
import java.lang.Math;  
import java.util.Scanner;  
​  
public class Test2  
{  
    public static void main(String[] args)  
    {  
        double r = 5.5;  
        double area = Math.PI* r*r;  
        double perimeter = 2*Math.PI*r;  
        System.out.print(area);  
        System.out.print(perimeter);  
    }  
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzU1OTIxMzEsMTUzMzMzNTEyMV19
-->