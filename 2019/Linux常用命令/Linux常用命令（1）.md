1. stat命令用于查看文件的具体存储信息和时间等信息
	1. stat anaconda-ks.cfg
2. cut命令用于按”**列**“提取文本字符
	1. cut -d: -fl /etc/passwd
3. diff命令用于比较多个文本文件的差异
	1. diff --brief/-c diff_A.txt diff_B.txt
4. dd命令用于安装指定大小和个数的数据块来复制文件或转换文件
	1. dd if=/dev/zero of=560_file count=1 bs=56M
5. file命令用于查看文件的类型
	1. file anaconda-ks.cfg
6. grep -b 将可执行文件（binary）当中文本文件（text）来搜索， -c 仅显示找到的行数， -i 忽略大小写， -n显示行号， -v反向选择
	1. grep /sbin/nologin /etc/password
7. find命令用于按照指定条件来查找文件
	1. -name   匹配名称
	2. -perm   匹配权限
	3. -user   匹配所有者
	4. -group  匹配所有组




