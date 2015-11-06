Windows Install Diskpart
========================
操作流程

+ 启动windows安装程序

+ 启动命令行 Shift+F10

+ X:Source> Diskpart

+ DISKPART> select disk 0

+ DISKPART> create partition primary size=30720

+ DISKPART> create partition primary size=102400

+ DISKPART> list partition

+ DISKPART> select partition 1

+ DISKPART> active

简写命令

+ 启动windows安装程序

+ 启动命令行 Shift+F10

+ X:Source> Diskpart

+ DISKPART> sel disk 0

+ DISKPART> create part primary size=30720

+ DISKPART> create part primary size=102400

+ DISKPART> list part

+ DISKPART> sel part 1

+ DISKPART> active
