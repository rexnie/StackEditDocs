uboot支持把目标文件放在另一个目录，和源代码分开放

-fno-builtin: 不是以__builtin_开头的函数不作为内置函数

-ffreestanding: 指定程序编译时在freestanding环境(没有标准库，程序不必从main开始执行)，这个在uboot的编译时特别有用

-nostdinc: 只在-I 指定目录寻找头文件，不在标准系统目录找头文件

-isystem dir_name: 指定在dir_name下找头文件，所以找头文件的顺序是，先在-I指定的目录，再在-isystem指定的目录，最后在标准系统找(如没加-nostdinc的话)

mini6410_sd_config_ram256:unconfig
...
这个配置会传递给mkconfig的参数是
BOARD_NAME=mini6410
ARCH=arm
CPU=s3c64xx
BOARD=mini6410
VENDOR=samsung
SOC=s3c6410
SD
ram256

ELF文件中包含符号表，汇编等信息
Bin文件将ELF文件中代码段，数据段，以及一些自定义的段抽出来，做成的一个image. 在没有OS时，只能运行bin文件。
由于有OS的存在，OS会将ELF解析出代码段，数据段，最终系统仍然以bin文件运行，由于ELF文件的信息更全，所以可用来做调试等用途

gcc -g $(CFLAG) -c boot.S   ==>boot.S编译为boot.o
ld -g -Bstatic -T LDFILE -Ttext 0x12345600 --start-group -Map boot.map -o boot.elf  ==>生产elf文件
objdump -Obinary boot.elf boot.bin ==>boot.elf转化为boot.bin

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbODEwODE3MjMyLC04NTgxNTA4MzZdfQ==
-->