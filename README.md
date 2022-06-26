# Linux

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
```

文件的类型分类

- c: 设备文件
- b: 块文件，磁盘等
- l: 软链接
- d: 目录
- f/-: 普通文件
- p: 管道文件
- s: 套接文件

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
```

```bash
mkdir -p dirname/subdir/filename
```

### touch - 创建文件

- 文件名区分大小写
- 文件不能包含特殊符号
- 文件名最多255个字符

```bash
touch filename
```

- 如果文件不存在，创建文件
- 如果文件存在，则修改文件的时间戳

```bash
touch -a filename -t "202202021212"   # change access file time to 202202021212
touch -m filename -t "202202021212"   # change modified file time to 202202021212
touch -d filename -t "202202021212"   # change both access/modified file time to 202202021212
```

### rm - 删除文件/ 目录

```bash
rm filename
```

```bash
rm -r dirname
```

### stat - 获得文件的详细信息

```bash
stat filename
```

可以看到文件的访问，创建，修改时间等信息

### cat - 看文件的内容

```bash
cat filename
```
