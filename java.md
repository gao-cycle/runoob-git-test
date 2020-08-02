# java

### 1.基础

![image-20200729201057853](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729201057853.png)

![image-20200729201221816](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729201221816.png)

![image-20200729201239481](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729201239481.png)

1.java的public只能有一个，而且只能是和文件名一样

2.System.out.println("") 先输出后换行

3.System.out.print("")  没有换行！！

System.out.println=('\

### 2.cmd运行

先切换到对应目录

然后javac hello.java

java hello (不要加后缀名)！！！

### 3.命名规范

![image-20200730100539673](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730100539673.png)

1.包名：多单词组成，所有字母小写

2.类名，接口名：多单词组成时，单词的首字母大写

3.变量名，方法名：多单词时，第一个单词的首字母小写，第二个首字母大写

4.![image-20200729201919337](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729201919337.png)

5.

```java
public static void main(String []args)
{
	//这里不能掉用，因为作用域不同
}
public void method(){
 int myClass=1;
}
```

### 4.数据类型

![image-20200729203447770](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729203447770.png)

byte是8位，可以表示256个数

用long表示 结果必须带一个l或者L

例如

long l1=12313412412412l；



float表示的范围比long还大

float结尾要以f或者F结尾

### 5.负数的表示及强制转换

原码：将一个整数，转换成二进制，就是其原码。如单字节的5的原码为：0000 0101；-5的原码为1000 0101。

反码：正数的反码就是其原码；负数的反码是将原码中，除符号位以外，每一位取反。如单字节的5的反码为：0000 0101；-5的反码为1111 1010。

补码：正数的补码就是其原码；负数的反码+1就是补码。如单字节的5的补码为：0000 0101；-5的原码为1111 1011。

 

在计算机中，正数是直接用原码表示的，如单字节5，在计算机中就表示为：0000 0101。负数用补码表示，如单字节-5，在计算机中表示为1111 1011。

![image-20200729212640899](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729212640899.png)

byte、short、char 两两相加会变成int~~！！！！！



![image-20200729213015358](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729213015358.png)



![image-20200729213224171](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729213224171.png)

long，float后面要加l、f的 但可能过小转化为int

整形默认int 浮点型默认double 不能再转为float！！！



![image-20200729213617394](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729213617394.png)

![image-20200729214014789](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729214014789.png)

如果存在双引号，那么+就是string连接

如果全都是单引号加起来，那就是char相加，自动转化为int类型，以ascal码的形式

![image-20200729214719791](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729214719791.png)

有双引号是连接 千万别再ascall码计算了！！！



下面是string的强化转化

![image-20200729214847365](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729214847365.png)

### 6.出现乱码

![image-20200729211632730](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729211632730.png)

试试这个 utf-8可以存储和读取不同，用用ansi试试

### 7.进制问题

二进制以ob或oB开头

八进制 以0开头，满8进1，最大7

十六进制 0-9 A-F 以ox或oX



![image-20200729220254548](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200729220254548.png)

二进制转八进制、十六进制

二进制-》八进制 从后面开始每三位二进制换成八进制的最后一位，以此类推

转16进制 ：则四位一组

### 8.逻辑运算符

![image-20200730101744280](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730101744280.png)

&和&&都是只有全true，则true。否则一错就错

|和||是全false才false，有一个true则对

逻辑异或 ，a和b相异时，结果为true

&&和||好处是可以只通过左边来判断最终结果，但&和|不管怎么样左右边都要算，效率可能低



x++==2 先运算再自增！！

### 9.位运算

左运算符：![image-20200730102439981](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730102439981.png)

所以<<左移一位，就乘2；

![image-20200730102558835](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730102558835.png)

这个小括号很关键，因为左移符和+优先级一样了

![image-20200730102827334](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730102827334.png)

左移右边补0

右移左边补0，如果原本是负数，那么左边最高位补1

![image-20200730103101061](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730103101061.png)

![image-20200730103244969](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730103244969.png)

&有错则错 |有对则对
^两个不一样那就是true

##### 利用位运算交换两值

![image-20200730103656547](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730103656547.png)

![image-20200730103810994](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730103810994.png)

看好这个k 很关键

先用n1和n2异或以后当作k

然后n2就等于k和n1的异或

n1等于k和n2的异或！！

### 10.运算符的优先级

![image-20200730104521484](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730104521484.png)

记住擅长用（）就行了！！！

### 11.巧用位运算符 将二进制转换16进制

![image-20200730112227118](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730112227118.png)

因为15是 1111 末尾 很巧用

![image-20200730112304349](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730112304349.png)

第一个是转为2进制 第二个是16进制

### 12 使用Scanner读取

![image-20200730112552832](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730112552832.png)

![image-20200730112914713](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730112914713.png)

### 13.质数算法

1.long start = System.currentTimeMillis()

2. Math.sqrt(i)

```java
/*
   求质数的优化方案
   */
  package first_1;
  
  public class primeNumberTest1 {
      public static void main(String[] args) {
          
          boolean isFlag = true;//标识i是否被j除尽，一旦除尽，修改其值
         int count = 0;//记录质数的个数
         
         //获取当前时间距离1970-01-01 00:00:00的毫秒数
         long start = System.currentTimeMillis();
         
         for (int i = 2; i <= 100000; i++) {//遍历100000以内的自然数
             
             //优化二：对本身是质数的自然数是有效的。
             //for (int j = 2; j < i; j++) {//j:被i去除
             for (int j = 2; j <= Math.sqrt(i); j++) {//j:被i去除
                if (i % j == 0) {
                     isFlag = false;                    
                     break;//优化一：只对本身非质数的自然数是有效的。
                 }
             }
             if (isFlag == true) {//i被j除尽
                 System.out.println(i);
                 count++;
             }
             //重置isFlag
             isFlag = true;
         }
         
         //获取当前时间距离1970-01-01 00:00:00的毫秒数
         long end = System.currentTimeMillis();
         System.out.println("质数的个数为：" + count);
         System.out.println("所花费的时间为："  + (end - start));//17110 - 优化一：1546 - 优化二：103
     }
 
 }
```

![image-20200730151436865](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730151436865.png)

### 14.项目一家庭收支解析

```java
public class FamilyAccount {
	public static void main(String[] args) {
        String details = "收支\t账户金额\t收支金额\t说    明\n";
        int balance = 10000;

        boolean loopFlag = true;
        do {
		    System.out.println("\n-----------------家庭收支记账软件-----------------\n");
            System.out.println("                   1 收支明细");
            System.out.println("                   2 登记收入");
            System.out.println("                   3 登记支出");
            System.out.println("                   4 退    出\n");
            System.out.print("                   请选择(1-4)：");
            
            char key = Utility.readMenuSelection();
            System.out.println();
            switch (key) {
                case '1':
                    System.out.println("-----------------当前收支明细记录-----------------");
                    System.out.println(details);
                    System.out.println("--------------------------------------------------");
                    break;
                case '2':
                    System.out.print("本次收入金额：");
                    int amount1 = Utility.readNumber();
                    System.out.print("本次收入说明：");
                    String desc1 = Utility.readString();

                    balance += amount1;
                    details += "收入\t" + balance + "\t\t" +
                               amount1 + "\t\t" + desc1 + "\n";
                    System.out.println("---------------------登记完成---------------------");
                    break;
                case '3':
                    System.out.print("本次支出金额：");
                    int amount2 = Utility.readNumber();
                    System.out.print("本次支出说明：");
                    String desc2 = Utility.readString();

                    balance -= amount2;
                    details += "支出\t" + balance + "\t\t" +
                               amount2 + "\t\t" + desc2 + "\n";
                    System.out.println("---------------------登记完成---------------------");
                    break;
                case '4':
                    System.out.print("确认是否退出(Y/N)：");
                    char yn = Utility.readConfirmSelection();
                    if (yn == 'Y') loopFlag = false;
                    break;
            }
        } while (loopFlag);
	}    
}

```



```java
import java.util.Scanner;
/**
Utility工具类：
将不同的功能封装为方法，就是可以直接通过调用方法使用它的功能，而无需考虑具体的功能实现细节。
*/
public class Utility {
    private static Scanner scanner = new Scanner(System.in);
    /**
	用于界面菜单的选择。该方法读取键盘，如果用户键入’1’-’4’中的任意字符，则方法返回。返回值为用户键入字符。
	*/
	public static char readMenuSelection() {
        char c;
        for (; ; ) {
            //读入
            String str = readKeyBoard(1);
            c = str.charAt(0);
            if (c != '1' && c != '2' && c != '3' && c != '4') {
                System.out.print("选择错误，请重新输入：");
            } else break;
        }
        return c;
    }
	/**
	用于收入和支出金额的输入。该方法从键盘读取一个不超过4位长度的整数，并将其作为方法的返回值。
	*/
    public static int readNumber() {
        int n;
        for (; ; ) {
            读入4位数
            String str = readKeyBoard(4);
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }
	/**
	用于收入和支出说明的输入。该方法从键盘读取一个不超过8位长度的字符串，并将其作为方法的返回值。
	*/
    public static String readString() {
        String str = readKeyBoard(8);
        return str;
    }
	
	/**
	用于确认选择的输入。该方法从键盘读取‘Y’或’N’，并将其作为方法的返回值。
	*/
    public static char readConfirmSelection() {
        char c;
        for (; ; ) {
            //toupperCase转化为大写元素
            String str = readKeyBoard(1).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入：");
            }
        }
        return c;
    }
	
	
    private static String readKeyBoard(int limit) {
        String line = "";

        while (scanner.hasNext()) {
            line = scanner.nextLine(); //读入字符串，可以有空格
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入长度（不大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }

        return line;
    }
}

```

### 15.java的输入流

```java
import java.util.*;
public class ScannerKeyBoardTest
{
    public static void main(String[] args)
    {
        System.out.println("请输入若干单词，以空格作为分隔");
        Scanner sc = new Scanner(System.in);
        while(!sc.hasNext("#"))  //匹配#返回true,然后取非运算。即以#为结束符号
        {
            System.out.println("键盘输入的内容是："

                + sc.next()); //跟scanf一样，以空格或回车分割
        }
        System.out.println("会执行的");
    }
}
```

### 16.eclipse的使用 =补全（自己改）

![image-20200730163129265](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730163129265.png)

先new一个 包 再class 右键run运行

### 17.package

![image-20200730200705310](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730200705310.png)

![image-20200730200717072](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730200717072.png)

### 18.数组

```java
int []ids;
//静态初始化
ids=new int[]{1,2,3,4};
或 ids=new int[5];


//动态初始化
String[] names=new String[5];

int[][] arr1=new int[][]{{1,2,3},{4,6,7}}
arr1.length=2 是行数
arr1[0].length=3 ***
    for(int i=0;i<arr4.length;i++)
    {
        for(int j=0;j<arr4[i].lenght;j++)
            -------
	}
String[][] arr3=new String[3][];
int[] arr5[]={{1,2,3},{4,3,5}}
```

### 19.数组元素初始值

![image-20200730201739718](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730201739718.png)

```java
package com.atguigu.context;

public class ArrayTest {

	public static void main(String[] args) {
		int[] arr=new int[5];
		for(int i=0;i<arr.length;i++)
		{
			System.out.println(arr[i]);
		}
			
		
	}
}

```

### 20.栈和堆内存

![image-20200730203420038](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200730203420038.png)

栈中存放局部变量，和对应的地址

这里把内容发到堆内存中，把地址付给栈中

### 21.二维数组-杨辉三角

```java
package com.atguigu.context;

public class YangHuiText {
	public static void main(String[] args) {
		int [][]yangHui=new int[10][];
		for(int i=0;i<yangHui.length;i++)
		{
			yangHui[i]=new int[i+1];
			yangHui[i][0]=yangHui[i][i]=1;
			if(i>1)
			{
				for(int j=1;j<yangHui[i].length-1;j++)
				{
					yangHui[i][j]=yangHui[i-1][j-1]+yangHui[i-1][j];
				}
			}
		}
		
		for(int i=0;i<yangHui.length;i++)
		{
			for(int j=0;j<yangHui[i].length;j++)
			{
				System.out.print(yangHui[i][j]);
				System.out.print("  ");
			}
			System.out.println("");
		}
	}
}

```

### 22.数组随机数（和js一样）

###### （in）(Math.random()*(max-min+1)+min);

```java
package com.atguigu.context;

public class ArrayText {
	public static void main(String[] args) {
		int [] arr =new int[10];
		for(int i=0;i<arr.length;i++)
		{
			arr[i]=(int)(Math.random()*(99-10+1)+10);
		}
		
		for(int i=0;i<arr.length;i++)
		{
			System.out.print(arr[i]+"\t");;
		}
		System.out.println();
		
		int maxValue=arr[0];
		for(int i=1;i<arr.length;i++) {
			if(maxValue<arr[i])
			{
				maxValue=arr[i];
			}
		}
		System.out.println("最大值："+maxValue);
	}
}

```

### 23.数组的反转

```java
String[] arr1=new String[arr.length];
for(int i=0;i<arr.length;i++)
{
String temp=arr[i];
arr[i]=arr[arr.length-i-1];
arr[arr.length-i-1]=temp;
}
```

### 24.线性查找

dest.equals(arr[i])!!!!!!!!

```java
String dest="bb";
for(int i=0;i<arr.length;i++){
if(dest.equals(arr[i])){
System.out.println()
break;
}
}
```

### 25.二分法查找

````java
package com.atguigu.context;

public class FindTwo {
public static void main(String[] args) {
	int [] arr=new int[] {1,2,3,4,5,6,7,8,9,10};
	int dest=5;
	int head=0;
	int end=arr.length-1;
	boolean isFlag=true;
	while(head<=end)
	{
		int middle=(head+end)/2;
		
		if(dest==arr[middle]) {
			System.out.println("找到了"+middle);
			isFlag=false;
			break;
		}else if(arr[middle]>dest)
		{
			end=middle-1;
		}
		else {
			head=middle+1;
		}
	}
	if(isFlag) {
		System.out.println("没有找到");
	}
}
}

````

### 26.冒泡排序

```java
int [] arr=new int[]{43,32,42,4324,31231,12};

for(int i=0;i<arr.length-1;i++)
{
for(int j=0;j<arr.length-1-i;j++)
{
---------
}
}
```

### 27.java中的Arrays数组类

```java
package com.atguigu.context;

import java.lang.reflect.Array;
import java.util.Arrays;

public class ArraysTest {
	public static void main(String[] args) {
		//1.boolean equals(int []a,int [] b )
		int []arr1=new int[] {1,2,3,4};
		int []arr2=new int[] {1,2,3,4};
		boolean isEquals=Arrays.equals(arr1, arr2);
		System.out.println(isEquals);
		
		//2.String toSring(int []a) 输出数组信息
		System.out.println(Arrays.toString(arr1));
		
		//3.void fill 把内容逐一填充到数组中
		Arrays.fill(arr1, 2);
		
		//4.void sort 快排
		Arrays.sort(arr2);
		System.out.println(Arrays.toString(arr2));
		
		//5.二分查找 （必须是有序的！！)
		int []arr3=new int[] {1,3,4,5,6};
		int index=Arrays.binarySearch(arr3, 3);
	}
}

```

### 28.数组异常

![image-20200731143409643](C:\Users\86137\AppData\Roaming\Typora\typora-user-images\image-20200731143409643.png)