
项目地址：https://github.com/esnet/iperf

启动为服务端  iperf3 -s 
  间隔1秒  iperf3 -s -i 1
  -p 指定端口

客户端测速 iperf3 -c 对端ip地址 -i 1 -t 40 -b 1000M 
-i间隔时间  -t 次数 -b 速率 -R 反转  也就是测试上行和下行
iperf3 -c 192.168.20.5 -i 1 -t 40 -b 1000M -R
iperf3 -c 192.168.20.5 -i 1 -t 40 -b 1000M 


测试udp  iperf3 -u -c 192.168.20.5 -i 1 -t 40 -b 1000M 
