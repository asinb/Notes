使用jenkins进行代码的部署操作

系统是centos8

官方的文档：https://pkg.jenkins.io/redhat-stable/

```bash
  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
  sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key


  yum install epel-release # repository that provides 'daemonize'
  yum install java-11-openjdk-devel
  yum install jenkins
```

防火墙

查看

```bash
[root@instance-0ad81fki ~]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: eth0
  sources: 
  services: cockpit dhcpv6-client ssh
  ports: 20/tcp 21/tcp 22/tcp 80/tcp 8888/tcp 39000-40000/tcp 888/tcp 8080/tcp 8080/udp
  protocols: 
  forward: no
  masquerade: no
  forward-ports: 
  source-ports: 
  icmp-blocks: 
  rich rules: 
```

开放

```bash
复制代码
1、开启防火墙 
systemctl start firewalld

2、开放指定端口
      firewall-cmd --zone=public --add-port=8080/tcp --permanent
 命令含义：
--zone #作用域
--add-port=8080/tcp  #添加端口，格式为：端口/通讯协议
--permanent  #永久生效，没有此参数重启后失效

3、重启防火墙
      firewall-cmd --reload

4、查看端口号
netstat -ntlp   //查看当前所有tcp端口·

netstat -ntulp |grep 8080   //查看所有8080端口使用情况·
```

* 停止 service jenkins stop
* 开始 service jenkins start
* 重启 service jenkins restart

7.卸载
 卸载jenkins：rpm -e jenkins
 删除缓存文件: find / -iname jenkins | xargs -n 1000 rm -rf

查看jenkins的位置
rpm -ql jenkins