# 设置静态链接库

##1.下载静态链接库的二进制版本

例如 目标平台为 win x86 
则应该下载 win 32 

##2.将下载的文件解压

在解决方案目录下，即和项目同目录下新建Dependences文件夹
并在其中新建 库名称文件夹例如GLFW

将 解压的文件中 的 include 与 lib -vc20XX（选择合适的版本）使用vs2019开发则使用lib-vc2019，
没有对应版本则选择最高版本。

##3.属性设置
1.在 项目属性 c/c++ 常规 包含目录 添加 $(SolutionDir)Dependences\GLFW\include 

2.在 项目属性 链接器 常规 附加库目录 添加 $(SolutionDir)Dependences\GLFW\lib-vc2019

3.在项目属性 链接器 输入 附加依赖项 添加 $(SolutionDir)Dependences\GLFW\lib-vc2019\glfw3.lib
##4.说明
$(SolutionDir) 为一个宏 等于 解决方案的实际位置
Dependences 为自定义的依赖项根目录
GLFW 为 一个自定义的库名称
include 为 GLFW库 下的包含目录，含有头文件若干
lib-vc2019 为 GLFW 库的一个vs2019 版本，包含静态或动态链接库
glfw3.lib 为静态库 具体使用 见GLFW的文档