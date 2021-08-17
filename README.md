## 说明

此工程中用于记录 slam 的相关程序，程序在学习 slam 中产生。

## 运行环境

程序由 c++ 编写，cmake 编译，程序使用了多个模块:Eigen、Sophus、g2o、fbow、pangolin、opencv，这些模块可以在 github 中找到，自行安装。

## 编译

在根目录下创建 build 文件夹，进入该文件夹，执行：
```shell
../cmake .
make
```
执行完毕后，根目录下会生成 `bin`、`lib` 文件夹，其中，bin 下面是相应的二进制可执行文件， lib 下是生成的 .so 动态库。

## 文件夹说明

|文件夹|说明|
|--|--|
|src|存放自己实现的一些 .cpp 源文件(每添加一个 cpp，都要在该目录下的 CMakeList.txt 中配置)|
|include|存放自己的一些 .h 头文件|
|test|存放测试函数(每添加一个 cpp，都要在该目录下的 CMakeList.txt 中配置)|
|app|存放最终生成的 .cpp 应用程序(每添加一个 cpp，都要在该目录下的 CMakeList.txt 中配置)|
|config|存放配置文件|
|cmake|存放cmake配置文件，用于查找相关模块|
|data|存放数据，视频数据或图片数据|

