
1、	下载并安装VSCode
下载地址：https://code.visualstudio.com/
 

2、	下载cmake
下载地址：https://cmake.org/download/
 
解压重命名为cmake,放到D盘根目录下
 
3、	下载K210的toolchain和openocd
下载地址：https://kendryte.com/downloads/
 
下载完成后，解压放到D盘根目录下。
 
4、	设置环境变量
 
5、	下载K210的最新SDK和demo package
下载地址：https://github.com/kendryte/kendryte-standalone-sdk
          https://github.com/kendryte/kendryte-standalone-demo

 
 
6、	创建新目录，取名“HELLO_WORLD”,拷贝K210的SDK到目录下。
 

 
打开src文件夹，删除hello_word
 
拷贝K210的demo 例程gpio_led文件夹中的main.c到HELLO_WORLD工程src文件夹内。
 
 

7、	打开VSCode
 
添加文件夹到VSCode中，选择刚才建立的HELLO_WORLD,点击“Add”
 
成功添加工程后的界面
 
选择工程根目录下的CMakeList.txt文件，添加如下代码。
#set project name
set(PROJ "HELLO_WORLD")
#set toolchain path
set(TOOLCHAIN "D:/kendryte-toolchain/bin")
 
修改如下位置
add_source_files(src/${PROJ}/*.c src/${PROJ}/*.s src/${PROJ}/*.S src/${PROJ}/*.cpp)
改为
add_source_files(src/*.c src/*.s src/*.S src/*.cpp)
保存
 
 
按键盘ctrl+shift+~,下方出现命令终端，
输入命令 mkdir build 回车，cd build 回车
 
输入 cmake .. –G “Unix Makefiles”回车
 
在根目录下build文件中，makefile文件已创建。
继续输入命令 mingw32-make,回车

