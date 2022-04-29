```sh
gcc main.c # 编译c
gcc -c main.c # 生成中间文件 [filename].o
gcc -shared -o add.dll add.c # 生成动态链接库
    -Ldir # 添加库查找目录
    -Idir # 添加头文件查找目录
    -lfilename #添加库文件
    -Wl,--add-stdcall-alias # windows dll添加标准调用前缀
```