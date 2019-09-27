Limbo: require LIMBO_DIR environment variable to the path where Limbo is installed. OpenMPL is based on Limbo library.

Some components depend on external libraries, such as

    CMake: CMake version 3.7.0 or later is required to build the library.
    Boost: managed by CMake FindBoost.
    Lemon: integrated as a third party package.
    Gurobi: require GUROBI_HOME environment variable to the path where Gurobi is installed.
    Flex: managed by CMake FindFlex.
    Zlib: managed by CMake [FindZLIB] (https://cmake.org/cmake/help/v3.13/module/FindZLIB.html).

Users need to make sure they are properly installed and the corresponding settings are configured.

1. flex zlib lemon can be installed using apt
    zlib安装时名称问题：apt-get install zlib1g-dev
2. when installed cmake you can refer to https://www.linuxidc.com/Linux/2018-09/154165.htm
3. when installed gurobi you can refer to https://blog.csdn.net/u013036495/article/details/86362026
4. when installed boost you can refer to https://blog.csdn.net/guoyunfei20/article/details/76013892 and https://www.cnblogs.com/taolusi/p/9244554.html
    安装boost过程中，./bootstrap.sh --with-libraries=all
    安装过称中缺少lpsolve(apt-get install liblpsolve55-dev)、coin（apt-get install coinor/coinor-libcbc-dev/coinor-libcoinutils-dev/libcoin-dev）
    
    make过称中会出现"parser_class_mame" "parser"问题，需要将/home/cheng/my_software/Limbo-master/limbo/parsers目录下所有.yy文件中的"parser_class_name"的
    引号去掉
    
sudo make install之后需添加limbo安装路径到环境变量至.bashrc(export LIMBO_DIR=*****)


