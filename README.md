# iperf3 云编译
<p align="center">
<a href="https://hits.seeyoufarm.com"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Flmq8267%2Fiperf3&count_bg=%2395C10D&title_bg=%23555555&icon=github.svg&icon_color=%238DC409&title=%E8%AE%BF%E9%97%AE%E6%95%B0&edge_flat=false"/></a>
<a href="https://github.com/lmq8267/iperf3/releases"><img src="https://img.shields.io/github/downloads/lmq8267/iperf3/total"></a>
<a href="https://github.com/lmq8267/iperf3/graphs/contributors"><img src="https://img.shields.io/github/contributors-anon/lmq8267/iperf3"></a>
<a href="https://github.com/lmq8267/iperf3/releases/"><img src="https://img.shields.io/github/release/lmq8267/iperf3"></a>
<a href="https://github.com/lmq8267/iperf3/issues"><img src="https://img.shields.io/github/issues-raw/lmq8267/iperf3"></a>
<a href="https://github.com/lmq8267/iperf3/discussions"><img src="https://img.shields.io/github/discussions/lmq8267/iperf3"></a>
<a href="GitHub repo size"><img src="https://img.shields.io/github/repo-size/lmq8267/iperf3?color=red&style=flat-square"></a>
<a href="https://github.com/lmq8267/iperf3/actions?query=workflow%3ABuild"><img src="https://img.shields.io/github/actions/workflow/status/lmq8267/iperf3/build-iperf3.yml?branch=main" alt="Build status"></a>


项目地址：https://github.com/esnet/iperf


启动为服务端  iperf3 -s

  间隔1秒  iperf3 -s -i 1
  
  -p 指定端口

  

客户端测速 iperf3 -c 对端ip地址 -i 1 -t 40 -b 1000M 

-i间隔时间  -t 次数 -b 速率 -R 反转  也就是测试上行和下行

iperf3 -c 192.168.20.5 -i 1 -t 40 -b 1000M -R

iperf3 -c 192.168.20.5 -i 1 -t 40 -b 1000M 


测试udp  iperf3 -u -c 192.168.20.5 -i 1 -t 40 -b 1000M 
