1. 使用Visual Studio 2019编译生成zlib 1.2.11版本
   1). 从zlib官网 "http://zlib.net/"
       下载最新版本的zlib "http://zlib.net/zlib-1.2.11.tar.gz"
       解压，展开到系统盘（也可自定义目录）。
   2). 在编译前，首先开启VS2019的Command Prompt (64bit)
   3). 生成64位库，则进入到zlib-1.2.11contrib\masmx64目录 "zlib-1.2.11\contrib\masmx64"，执行bld_ml64.bat
   这一步运行bld_ml64批处理文件，里面调用ml命令编译gvmat64.asm和inffasx64.asm，生成gvmat64.obj和inffasx64.obj。这两个文件在zlibvc中用到。
   (注意ml64.exe在vs2010的"Microsoft Visual Studio 10.0/VC/bin"下面找不到。我们需要使用"Microsoft Visual Studio 10.0/VC/bin/amd64/"
   下面的ml64.exe。这里可以简单将其复制到"Microsoft Visual Studio 10.0/VC/bin"下面。)
   
   4). zlib的vs sln解决方案文件可以在如下路径中找到：zlib-1.2.11/contrib/vstudio/vc14/zlibvc.sln，打开
   5). 在工具栏中将“解决方案平台”改为“x64”，编译即可
   
  此时，会报错，错误如下：
1>  The system cannot find the path specified.
1>  'bld_ml64.bat' is not recognized as an internal or external command,
1>  operable program or batch file.
1>C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140\Microsoft.CppCommon.targets(123,5): error MSB3073: The command "cd ..\..\contrib\masmx64
1>C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140\Microsoft.CppCommon.targets(123,5): error MSB3073: bld_ml64.bat
1>C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140\Microsoft.CppCommon.targets(123,5): error MSB3073: :VCEnd" exited with code 9009.
========== Build: 0 succeeded, 1 failed, 0 up-to-date, 0 skipped ==========
  或者如图所示
 
![image](https://github.com/AaronCheng820/Some-software-installation-guiding/blob/master/image/111.png)
 
  
  此时，右键点击zlibvc，在弹出菜单中选择属性(Properties)属性>>生成事件(Build Event)>>预先生成事件(Pre-Build Event)>>命令行(Command Line)中有错误提示所示的命令行。
此时点击下拉按钮>>编辑(Edit)>>删除内容>>用下述内容替换(若路径不是本文路径，需要对路径进行相应修改)
D: 
cd D:\zlib-1.2.11\zlib-1.2.11\contrib\masmx64 
bld_ml64.bat
