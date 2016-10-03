- ##Description

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
		
			    <div align= center>![](https://github.com/Izumisakai/ES2016_14353096/blob/master/image/1.png)</div>

- ##Experimental experience
