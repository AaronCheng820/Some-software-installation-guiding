在windows下安装flex和bison：
这两天为了项目而要学习一下编译原理中要用到得两个工具，flex和bison。这两个软件是可以在windows下运行和编译得，之前也在网上查了不少资料，终于昨天下载了下来。今天来安装，装完了不知道要怎么运行，于是又上网查找了很多资料，才发现这两个工具都是命令行软件，要运行就得在MS-DOS环境下输入命令。
  
下载得网址:
http://gnuwin32.sourceforge.net/packages/flex.htm
http://gnuwin32.sourceforge.net/packages/bison.htm
 
   最偷懒得方法就是直接下载 Complete package, except sources
   这是一个完整得安装包，包含了所有得内容，之前我还把其他zip文件一个一个都下载了，当时还没想明白呢。
   然后跟windows一般软件得安装方法一样，直接点击setup.exe文件，next到底就装好了。全都安装好以后还要设置一下环境变量path。（到现在还没搞明白这个path呢）
   打开右键我得电脑→属性→內容→高级→环境变量→系统变量→path→编辑
加入;C:\Program Files\GnuWin32\bin;
记得前后要加分号，接著打开命令提示字元cmd
键入
flex -V
bison -V   
这样就能看到正确得信息就表示安装成功了！！
PS：这里得V一定得大写，一开始我以为DOS不分大小写，所以就输入了v，结果没反应，后来尝试大写V，终于出来信息了，好开心阿在windows下安装flex和bison。


(另外)安装完毕后执行
>bison–help
Usage: bison [OPTION]... FILE
Generate LALR(1) and GLR parsers.



