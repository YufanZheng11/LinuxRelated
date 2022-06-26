# Linux

[Linux 命令大全](https://www.runoob.com/linux/linux-command-manual.html)

## Linux 文件系统和文件操作

- **/dev** - 存放 device 文件
- **/bin** - 存放可执行的文件
- **/sbin** - 存放 root 权限可执行的文件
- **/var** - 可变的数据文件
  - **/var/log/**
- **/usr**
  - **/usr/bin/**

### file - 检查文件类型

```bash
file path_to_filename

文件的类型分类

- c: 设备文件
- b: 块文件，磁盘等
- l: 软链接
- d: 目录
- f/-: 普通文件
- p: 管道文件
- s: 套接文件
```

### ls - 检查目录里的文件信息

```bash
ls 常用参数

-a 显示所有文件，包含隐藏文件
-A 显示所有文件，包含隐藏文件，但不包含.及..
-l 显示为long format(长格式)，列出文件的类型、权限、链接数、owner、group、大 小，时间，名字
-d 不展开目录，只显示目录自身，一般与-l配合使用以显示目录自身的属性信息(只显示当前目录的内容)
-1 数字1，成列显示内容
-S 以文件大小排序显示，默认从大到小 -r后，从小到大
-U 按存放顺序排序显示
-X 按扩展名的首字母来排序
-t 按mtime排序(先显示时间最近的)
-ul 按atime排序(先显示时间最近的)
-ct 按ctime排序(先显示时间最近的)
```

### mkdir - 创建一个目录

```bash
mkdir dirname
mkdir -p dirname/subdir/filename
```

### touch - 创建文件

- 文件名区分大小写
- 文件不能包含特殊符号
- 文件名最多255个字符

```bash
touch filename_not_exist        # 如果文件不存在，创建文件
touch filename_exist            # 如果文件存在，则修改文件的时间戳
```

人为的改变特定的时间戳

```bash
touch -a filename -t "202202021212"   # change access file time to 202202021212
touch -m filename -t "202202021212"   # change modified file time to 202202021212
touch -d filename -t "202202021212"   # change both access/modified file time to 202202021212
```

### rm - 删除文件/ 目录

```bash
rm filename
rm -f filename
rm -r dirname
rm -rf dirname
```

### stat - 获得文件的详细信息

```bash
stat filename
```

可以看到文件的访问，创建，修改时间等信息

### cat - 看小文件的内容

```bash
cat [-AbeEnstTuv] [--help] [--version] fileName

-n 或 --number：由 1 开始对所有输出的行数编号。
-b 或 --number-nonblank：和 -n 相似，只不过对于空白行不编号。
-s 或 --squeeze-blank：当遇到有连续两行以上的空白行，就代换为一行的空白行。
-v 或 --show-nonprinting：使用 ^ 和 M- 符号，除了 LFD 和 TAB 之外。
-E 或 --show-ends : 在每行结束处显示 $。
-T 或 --show-tabs: 将 TAB 字符显示为 ^I。
-A, --show-all：等价于 -vET。
-e：等价于"-vE"选项；
-t：等价于"-vT"选项；
```

### tac - 看小文件的内容（最后一行在最上面，第一行在最下面，刚好和 cat 相反）

```bash
tac small_filename
-h 显示行号
```

### less - 查看大文件

```bash
less filename

空格 ： 一页一页翻
回车 ： 一行一行翻
上下 ： page up down
/xxx ： 搜索 xxx 回车
        按住 n 找到下一个搜索的店
q   ： 退出
```

### more - 查看大文件

一般使用 less，比较好用， 功能更多

```bash
more filename
```

### head - 查看前几行文件

```bash
head filename       # show top 10 lines
head -n filename    # show top n lines
```

### tail - 查看前几行文件

```bash
tail filename       # show last 10 lines
tail -n filename    # show last n lines
tail -f filename    # 动态的查看文件的最后部分
```

### ldd - 查看二进制的文件

```bash
ldd /usr/bin/mkdir
```

### cp - 拷贝文件

```bash
cp [options] source dest

-a：此选项通常在复制目录时使用，它保留链接、文件属性，并复制目录下的所有内容。其作用等于dpR参数组合。
-d：复制时保留链接。这里所说的链接相当于 Windows 系统中的快捷方式。
-f：覆盖已经存在的目标文件而不给出提示。
-i：与 -f 选项相反，在覆盖目标文件之前给出提示，要求用户确认是否覆盖，回答 y 时目标文件将被覆盖。
-p：除复制文件的内容外，还把修改时间和访问权限也复制到新文件中。
-r：若给出的源文件是一个目录文件，此时将复制该目录下所有的子目录和文件。
-l：不复制文件，只是生成链接文件。
```
