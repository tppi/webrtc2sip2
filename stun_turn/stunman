1. Install stunserver on CentOS/Ubuntu
yum -y install gcc
yum -y install make
yum -y install boost-devel # For Boost
yum -y install openssl-devel # For OpenSSL
wget  http://www.stunprotocol.org/stunserver-1.2.3.tgz
tar zxvf stunserver-1.2.3.tgz
cd stunserver
make

apt-get install g++  
apt-get install make  
apt-get install libboost-dev # For Boost  
apt-get install libssl-dev # For OpenSSL  
wget http://www.stunprotocol.org/stunserver-1.2.13.tgz
tar -zxvf stunserver-1.2.13.tgz
make

./stunserver
netstat -ap | grep 3478
udp        0      0 *:3478                  *:*                                 3658/stunserver
sudo ./stunclient 127.0.0.1 3478
Binding test: success  
Local address: 127.0.0.1:41348  
Mapped address: 127.0.0.1:41348

2. sipml5 ICE Servers:
[{url:'stun:8.134.18.182:3478'}]


3. Install coturn on CentOS/Ubuntu
# 安装coturn
yum install coturn / apt-get install coturn
# 启动coturn
turnserver -o -a -f -v --mobility -m 10 --max-bps=1024000 --min-port=16384 --max-port=32768 --user=test:test123 -r test  
(开放端口与freeswitch/conf/autoload_configs/switch.conf.xml配置保持同步,允许通过的比特流速率1M=1024×1024不能太小)
# 停止coturn
ps aux | grep turnserver
found process id，example：2059
kill 2059

4. sipml5 ICE Servers:
[{url:'stun:8.134.18.182:3478'}]
[{url:'stun:8.134.18.182:3478'},{url:'turn:8.134.18.182:3478', username:'test', credential:'test123'}]

