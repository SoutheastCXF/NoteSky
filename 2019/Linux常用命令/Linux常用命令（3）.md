1. 常见的网卡绑定驱动有三种模式   **负载均衡，网卡设置**
	1. mode0：平时两块网卡均工作，且自动备援，但需要在于服务器本地网卡相连的交换机设备上进行端口聚合来支持绑定技术
	2. mode1：平时只有一块网卡工作，在它故障后自动替换为另外的网卡
	3. mode6：平时两块网卡均工作，且自动备援，无须交换机设备提供辅助支持
2. nmcli centos7的默认网络管理客户端，其作用：
	1. 可以一键快速切换网络环境
	2. 支持网络环境添加
	3. 支持Linux网卡绑定技术
3.远程传输命令，scp: scp (security copy) 是一个基于SSH协议在网络之间进行安全传输的命令，其格式为 scp [参数] 本地文件 远程账号@远程IP地址：远程目录
4. 不间断会话服务：screen是一款能够实现多窗口远程控制的开源服务程序，为了解决网络异常中断或为了同时控制多个远程端口而设计的程序


**SELINUX**
semanage命令用于管理SELINUX的策略
1. semanage fcontext -a -t httpd_sys_content_t dir -> 向新的网站数据目录中添加一条SELINUX安全上下文
2. restorecon命令将设置好的SELINUX安全上下文立即生效，加上-Rv参数对指定的目录进行递归操作
3. getsebool命令查询并过滤所有与HTTP协议相关的安全策略。其中off为禁止状态，on为运行状态
4. htpasswd -c /etc/httpd/passwd leo ->为leo用户生成一个密码，类似CSDN的博客
5. semanage port -a -t http_port_t -p tcp 6111，在selinux中添加一个能被http_port_t服务程序访问到的端口
6. 利用apache的httpd服务，我们可以配置基于IP地址，基于端口，基于主机域名三种方式对网站上的资源进行控制
