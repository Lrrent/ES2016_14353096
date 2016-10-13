- ##实验截图

	- ####dot截图
	
		- #####example1
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/dot1.png =100x)
			
		- #####example2
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/dot2.png =100)
			
	- ####结果截图
	
		- #####example1
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/image1.png)
			
		- #####example2
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/image2.png)
			
- ##实验内容（代码更改）

	- ####example1
		根据文档提供的内容，我们只需要修改在square.c中的内容，并且明显里面的i=i&#42;i是控制平方的，所以如果我们想要实现三次方只需要改成i=i&#42;i&#42;i
		
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/image3.png)
		
	- ####example2
		可以看到迭代次数是由一个叫做N的变量所决定的，并且这个变量的赋值是在代码开头，如果我们想要实现迭代两次，只需要将其值从3改到2便能实现
		
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/image4.png)
			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/image5.png)
		
- ##实验感想
	这次的实验主要是让我们认识DOL中的example是怎么工作的，每一个EXAMPLE包含多个进程：生产者、消费者以及各种处理模块，这次实验中只用到了平方模块，这几个进程的关系可以从example.xml（模块连接方式定义文件）清楚的看出来，并且也能在运行完后的dot图中看到。实验内容是比较简单的，首先是因为有提示，其次各个进程的功能都非常明显，所以只需要从涉及到相关功能的进程中入手，另外代码比较简单，所以很容易就能看出来应该怎么改。总的来说这次实验是一次认识dol的实验，难度较低。
