1、配置path

export PATH=$PATH:mkl安装目录/bin

2、配置环境变量

export C_INCLUDE_PATH=javahome/include

3、icc *.c -mkl -openmp -shared -fpic -o libHiMatMkl-linux-x86_64.so 
