创建CMakeLists.txt：

    cmake_minimum_required(VERSION 3.10)
    project(chapter)
    add_executable(3-6 3-6.cpp)
    add_executable(3-7 3-7.cpp) #多行

cmake_minimum_required(VERSION 3.10)：这一行指定了所需的CMake的最低版本。  
project(3-6)：这一行定义了项目的名称。  
add_executable(3-6 3-6.cpp)：这一行指定了生成可执行文件的命令。将源文件与可执行文件进行关联。在这个例子中，它将名为"3-6.cpp"的源文件与可执行文件"3-6"进行关联。  


配置项目：  
（告诉CMake在当前目录下查找CMakeLists.txt文件，并将构建结果放在一个名为"build"的目录中）

    cmake -S . -B build



构建项目：  
（使用CMake生成的构建系统来构建项目。它将进入"build"目录并执行构建操作）

    cmake  --build build  
    
    
运行：  

    ./build/3-6  
    

更改cmake 地址时 删掉build文件重新运行  
