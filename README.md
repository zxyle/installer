# installer

## 介绍
日常开发过程中，经常需要安装一些软件，比如：mysql、redis、nginx、php、java、nodejs、docker、
docker-compose、git、svn、maven、jenkins、zabbix、kafka、zookeeper、elasticsearch、kibana、logstash、nginx等软件，
这些软件的安装过程都是一样的，都是下载安装包，解压，配置环境变量，配置启动脚本，修改配置文件，启动服务，这些过程都是重复的，而且每次安装都需要手动操作，
很麻烦，所以写了一些自动化安装脚本，可以自动化安装这些软件，只需要一条命令就可以安装，非常方便。

## 使用方法
### 1. 控制机安装ansible
```
pip install -r requirements.txt
```

### 2. 修改hosts文件
修改项目根目录下的hosts文件，将需要安装的机器的ip地址写入到hosts文件中，如下：
```
[all]
192.168.1.2
192.168.1.3
```

### 3. 配置免密登录
```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.2
```

### 4. 执行安装命令
```bash
ansible-playbook -i hosts install_xxx.yml
```