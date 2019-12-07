JAVA实验报告
班级：计G191
姓名 : 邓嘉睿
   学号：2019322044
实验目的:
分析学生选课系统
使用GUI窗体和组件设计窗体界面
完成学生选课业务逻辑编程
处理异常



实验过程：
设计思路
设计窗体
打印课表
编辑属性
增删查改


核心代码：
System.out.println("选择需要的查找的方法, 1学号，2姓名");
		int p = in.nextInt();
	if(p==1) {
		//使用学号的方法进行查找
	System.out.println("输入您所需要查找的学生学号");
		String y = in.next();
		int x = search.StuNum(stu,y);
	if(x>=0)
			System.out.println("学号:"+stu[x].number+" 学生:"+stu[x].name+" 专业:"+stu[x].major+" 数学:"+stu[x].math+" 计算机:"+stu[x].computer+" 英语:"+stu[x].english);
		else
	System.out.println("输入的学生不存在");
		}
		if(p==2) {
		//使用姓名的方法进行查找
	System.out.println("输入您所需要查找的学生姓名");
	String thename = in.next();
		int w = search.StuNam(stu,thename);
		if(w>=0)
	System.out.println("学号:"+stu[w].number+" 学生:"+stu[w].name+" 专业:"+stu[w].major+" 数学:"+stu[w].math+" 计算机:"+stu[w].computer+" 英语:"+stu[w].english);
		else
		System.out.println("输入的学生不存在");
	}
	System.out.println("是否需要对单科成绩进行排名 [Y/N] 1 =yes,2=no");
		int op = in.nextInt();
		if(op==1) {
		//单科成绩的排序（输入所需要科目然后直接进行排序）
	Rank rank = new Rank();//创建对象
		System.out.println("输入所需要排序的成绩编号 , 1：数学，2：英语，3：计算机");
	int major = in.nextInt();
		rank.rankscore(stu,major);
	//输出排序后的成绩
		for(int i = 0;i < stu.length;i++) {
		System.out.println("学号:"+stu[i].number+" 学生:"+stu[i].name+" 专业:"+stu[i].major+" 数学:"+stu[i].math+" 计算机:"+stu[i].computer+" 英语:"+stu[i].english);
		}
	}
		else {
		System.out.println("结束，退出系统");
	}
	}







运行截图：




编程感想总结：
通过这次实验，我意识到了自己在JAVA方面学习的不足和对于新的知识接受效率的缺陷。对于代码方面的知识让我焦头烂额，通过网络资料和课本JAVA语言程序设计，我学到了很多以前不知道的东西。有两种方法可以做到：
1 用制表符\t实现对齐。
制表符\t输出的时候，会移动输出光标，实现对齐效果。所以可以在输出的对应位置，增加\t来实现对齐。
要求每行相同列输出占用空间差别不可以太大。

2 在格式字符中加入占用宽度控制数字。
C语言使用printf输出时，每个控制字符均可以写成
%nC的形式，如%10d, %12f, %8c, %16s等等。
其效果就是输出对应变量时占用n个字符的宽度。不足部分左侧补空格。通过这种方式，可以实现右对齐效果。
如果要实现做对齐效果，只需要在宽度字符前加-符号即可，如%-8s，就是把字符串输出，占8位宽度，右侧补空格。
