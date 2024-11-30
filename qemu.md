# QEMU

> https://www.cnblogs.com/xiaomanblog/articles/18248205



获取内核代码并解压

```
wget https://mirrors.aliyun.com/linux-kernel/v5.x/linux-5.4.tar.xz

wget https://mirrors.aliyun.com/linux-kernel/v6.x/linux-6.0.9.tar.xz
```

```
tar xvf linux-5.4.tar.xz

tar xvf linux-6.0.9.tar.xz
```

配置.config

```

```

```
sudo apt install make
sudo apt install make-guile
sudo apt-get install flex
sudo apt-get install ncurses-dev
sudo apt-get install bison
```



```
make CROSS_COMPILE=aarch64-linux-gnu- ARCH=arm64 O=build menuconfig -j4
```



```
make CROSS_COMPILE=aarch64-linux-gnu- ARCH=arm64 O=build INSTALL_PATH=build/arch/$ARCH/boot -j4

build/arch/arm64/boot/Image
```





```
tar xvf u-boot-2024.07.tar.bz2

tar xvf linux-6.9.7.tar.xz

cd linux-6.9.7

E:\os_course\qemu

CONFIG_CC_OPTIMIZE_FOR_SIZE

CONFIG_PROFILE_ALL_BRANCHES
```



\



```
{
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Linux-6.0.9",
            "type": "cppdbg",
            "request": "launch", 
            "program": "~/100ask_imx6ull-qemu/linux-4.9.88/vmlinux",//vmlinux路径
            "args": [],//启动参数,如果需要记录日志可以自己增加参数。因为gdbsever已经有了参数，这里可以不用设置
            "stopAtEntry": true,//会自动停在main,不需要则设置为false
            "cwd": "${workspaceRoot}",
            "environment": [],
            "externalConsole": true,
            "MIMode": "gdb", //运行模式
            "logging": {
                "moduleLoad": false,
                "engineLogging": false,
                "trace": false
            },
            "setupCommands": [ //命令
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
            ],
            "miDebuggerPath":"arm-linux-gnueabihf-gdb",//工具链gdb
            "miDebuggerServerAddress":"127.0.0.1:1234"//远程端口

        }
    ]
}
```

