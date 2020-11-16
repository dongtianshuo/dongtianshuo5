# 计191董天硕2019311016
# 实验目的
1.掌握字符串String及其方法的使用。  
2.掌握文件的读取/写入方法。  
3.掌握异常处理结构。  
# 实验要求
1.设计学生类；  
2.采用交互式方式实例化某学生；  
3.设计程序完成上述的业务逻辑处理，并且把“古诗处理后的输出”结果存储到学生基本信息所在的文本文件A中。  
  在某课上,学生要提交实验结果，该结果存储在一个文本文件A中。  
    文件A包括两部分内容：  
    一是学生的基本信息；  
    二是学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法，实现如下功能：  

  1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”  
  2.允许提供输入参数，统计古诗中某个字或词出现的次数  
  3.输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A  
  4.考虑操作中可能出现的异常，在程序中设计异常处理程序  
# 实验过程
### Student学生类
1.在Student类中我定义了4个变量：String类型班级c，String类型名字name，int类型学号number，String类型性别gender；  
2.使用set（）方法方便返回对于的值，使用toString（）方法,返回相关对象的信息输出；  
### Test主类
1.
# 核心代码
```
BufferedReader in = new BufferedReader(new FileReader("E:\\B.txt"));
String str = in.readLine();
```
```
String regex = "(.{7})";
str = str.replaceAll(regex,"$1，");
StringBuffer sb = new StringBuffer(str);
for (int i =15;i<289;i=i+17) {
    sb.replace(i, i + 1, "。\n");
}
```
```
Scanner h = new Scanner(System.in);
String h1 = h.nextLine();
int a=0;
for (int i = 0; i < str.length(); i++) {
    if(Objects.equals(ai[i], h1)){
        a++;
    }
}
```
```
Scanner r = new Scanner(System.in);
String r1 = r.nextLine();
int count = 0;
int index = 0;
while ((index = str.indexOf(r1, index)) != -1) {
    index = index + r1.length();
    count++;
}
```
# 结果截图
![实验结果截图](https://github.com/dongtianshuo/dongtianshuo5/blob/main/FK4NX2YL%24VZSMZFUQ%7BESSD9.png)
# 实验总结
此次实验我进一步了解异常的使用方法，并在程序中根据输入情况做异常处理；基本掌握了字符串String及其方法的使用、掌握文件的读取/写入方法；进一步掌握并使用Object根类的toString（）方法,应用在相关对象的信息输出中。
