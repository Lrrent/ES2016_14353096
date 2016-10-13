- ##Description
	The distributed operation layer (DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform. The DOL consists of basically three parts:
	
	- DOL Application Programming Interface: The DOL defines a set of computation and communication routines that enable the programming of distributed, parallel applications for the SHAPES platform. Using these routines, application programmers can write programs without having detailed knowledge about the underlying architecture. In fact, these routines are subject to further refinement in the hardware dependent software (HdS) layer.
		
	- DOL Functional Simulation: To provide programmers a possibility to test their applications, a functional simulation framework has been developed. Besides functional verification of applications, this framework is used to obtain performance parameters at the application level.
		
	- DOL Mapping Optimization: The goal of the DOL mapping optimization is to compute a set of optimal mappings of an application onto the SHAPES architecture platform. In a first step, XML based specification formats have been defined that allow to describe the application and the architecture at an abstract level. Still, all the information necessary to obtain accurate performance estimates is contained.
		
- ##How to install

	- ###配置环境
		- 开始的时候先为安装DOL配置必要的环境，在linux环境下的命令行中输入以下指令
	
		```
			$sudo apt-get update
			$sudo apt-get install ant
			$sudo apt-get install openjdk-7-jdk
			$sudo apt-get install unzip
		```
	- ###解压文件
		- 用mkdir新建一个文件夹dol文件夹存放文件

				$mkdir dol
		- 解压压缩包中的dolethz.zip与systemc

				$unzip dol_ethz.zip d dol
				$tar -zxvf systemc-2.3.1.tgz

	- ###编译systemc
		- 解压后进入systemc-2.3.1的目录下

				$cd systemc-2.3.1
		- 新建一个临时文件夹objdir

				$mkdir objdir
		- 进入该文件夹objdir

				$cd objdir
		- 运行configure(能根据系统的环境设置一下参数，用于编译)

				$../configure CXX=g++ --disable-async-updates
		- 运行结果如下

			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/4.png)
		- 编译

				$sudo make install
		- 先后执行如下指令

				$cd ..        
				$ls
		- 编译完后文件目录如下

			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/5.png)
		- 记录当前路径

				$pwd

	- ###编译dol
		- 打开dol文件夹中的build_zip.xml,找到如下这段话，将YYY改成上述pwd的路径

				<property name="systemc.inc" value="YYY/include"/>
				<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
		-然后是编译

				$ant -f build_zip.xml all
		- 若成功会显示build successful

			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/3.png)
		- 接着可以进入build/bin/mian路径下试试运行第一个例子

				$cd build/bin/main
		- 然后运行第一个例子

				$ant -f runexample.xml -Dnumber=1
		- 成功结果如图

			![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/1.png)

- ##Experimental experience

	第一次实验要求配置dol的环境，步骤在ta提供的ppt中已经有详尽的介绍，只需要按照步骤一步步来就能完成。
	
	其中最后编译dol的时候出现了一些错误，提示说jdk的版本太低，然后在终端中输入$ sudo apt-get install openjdk-7-jdk，提示找不到资源，于是尝试了一下openjdk8，发现可行并且编译成功。

