# ansible_for_aliyun
本项目记录如何使用ansible在阿里云上安装node exporter,nginx等操作。
第一步：在inventory文件中添加相应的ECS实例IP地址
第二步：检查yml文件，在文件中写入远程主机名，要执行的操作等信息
第三步：在ansible控制主机（linux系统）上运行这两条命令：
$ ssh-agent bash
$ ssh-add ~/.ssh/id_rsa  //将ssh private key文件加入ssh agent，这样ansible就可以使用ssh key来登陆远程主机
第四步：在当前路径添加ansible.cfg文件，并写入配置
第五步：ansible all -m ping //测试inventory中所有主机的连通性
第六步：ansible-playbook -i inventory install_nginx.yml //在远程主机上安装nginx，并设置开机启动