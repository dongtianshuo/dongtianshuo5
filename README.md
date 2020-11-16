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
2.使用set（）方法方便返回对应的值，使用toString（）方法,返回相关对象的信息输出；  
### Test主类
1.我先使用Scanner方法来进行交互输入，并且设置了一个Student对象i1；  
2.用户依次输入的班级，姓名，学号，性别，然后通过set（）将用户依次输入的班级，姓名，学号，性别存入到i1中，以便将学生信息存入文本文件中；  
3.我使用了BufferedReader方法进行文本文件B.txt的读入BufferedReader in = new BufferedReader(new FileReader("E:\\B.txt"));然后创建了一个String类型的str并且使用readLine方法将文本文件B.txt中的内容储存到str当中，这样得到一个字符串；  
4.在进行标点符号的添加中，我首先使用replaceAll方法每隔7个字符加入一个“，”号str = str.replaceAll(regex,"$1，");，然后使用replace方法将每隔第15位的“，”转变为“。”；并且回车将古诗词对其；  
5.在进行字符串的输出时，我使用FileWriter方法将字符串和学生信息输入到A.txt中，使用flush()方法将字符串输出，使用valueOf方法返回字符串处理后的值和学生的信息；  
6.然后进行查询系统，首先我运用了for（）循环进行循环查询系统，在for（）循环中运用了switch（）方法进行判断用户查询字，词或者选择结束，我设定为1为查询字，2为查询词，3为结束；用户选择查询字时首先用户输入一个String字符，然后运用for（）循环进行字符串中的字符和用户输入的字符是否一致，在这里我运用final 类 Objects中的equals进行判断，并且设置一个int类的变量a，并且初始值设为0，每当查到一致时，a的值会加一，循环整个字符串后输出a的值；  
7.在进行词的查询时，首先让用户输入一个想要查询的词，然后通过indexOf（）方法进行在字符串中某一字符串的查找查找过程与查找字的类似，并且设置一个int变量count，并且初始值设为0，每当查到一致时，count的值会加一，循环整个字符串后输出count的值；用户输入3后会退出查询系统；    
8.在进行异常处理结构中，我在交互式输入学生信息后面加入了一个try（）
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
此次实验我进一步了解异常的使用方法，进一步掌握并使用Object根类的toString（）方法,应用在相关对象的信息输出中并在程序中根据输入情况做异常处理；基本掌握了字符串String及其方法的使用、掌握文件的读取/写入方法；
