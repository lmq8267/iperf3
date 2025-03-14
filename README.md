# iperf3 云编译
<p align="center">
  <img alt="GitHub Created At" src="https://img.shields.io/github/created-at/lmq8267/iperf3?logo=github&label=%E5%88%9B%E5%BB%BA%E6%97%A5%E6%9C%9F">
<a href="https://hits.seeyoufarm.com"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Flmq8267%2Fiperf3&count_bg=%2395C10D&title_bg=%23555555&icon=github.svg&icon_color=%238DC409&title=%E8%AE%BF%E9%97%AE%E6%95%B0&edge_flat=false"/></a>
<a href="https://github.com/lmq8267/iperf3/releases"><img src="https://img.shields.io/github/downloads/lmq8267/iperf3/total?logo=github&label=%E4%B8%8B%E8%BD%BD%E9%87%8F"></a>
<a href="https://github.com/lmq8267/iperf3/graphs/contributors"><img src="https://img.shields.io/github/contributors-anon/lmq8267/iperf3?logo=github&label=%E8%B4%A1%E7%8C%AE%E8%80%85"></a>
<a href="https://github.com/lmq8267/iperf3/releases/"><img src="https://img.shields.io/github/release/lmq8267/iperf3?logo=github&label=%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC"></a>
<a href="https://github.com/lmq8267/iperf3/issues"><img src="https://img.shields.io/github/issues-raw/lmq8267/iperf3?logo=github&label=%E9%97%AE%E9%A2%98"></a>
<a href="https://github.com/lmq8267/iperf3/discussions"><img src="https://img.shields.io/github/discussions/lmq8267/iperf3?logo=github&label=%E8%AE%A8%E8%AE%BA"></a>
<a href="GitHub repo size"><img src="https://img.shields.io/github/repo-size/lmq8267/iperf3?logo=github&label=%E4%BB%93%E5%BA%93%E5%A4%A7%E5%B0%8F"></a>
<a href="https://github.com/lmq8267/iperf3/actions?query=workflow%3ABuild"><img src="https://img.shields.io/github/actions/workflow/status/lmq8267/iperf3/build-iperf3.yml?branch=main&logo=github&label=%E6%9E%84%E5%BB%BA%E7%8A%B6%E6%80%81" alt="Build status"></a>


项目地址：https://github.com/esnet/iperf


### 作为服务端：

```
# 启动 iperf3 服务器，监听默认端口 5201
iperf3 -s

# 启动服务器并指定监听端口
iperf3 -s -p 5000

# 以守护进程模式运行服务器
iperf3 -s -D

# 服务器处理一个客户端连接后自动退出
iperf3 -s -1

# 限制服务器的总带宽，例如限制为 100Mbit/s
iperf3 -s --server-bitrate-limit 100M

# 指定服务器监听的 IP 地址（适用于多网卡）
iperf3 -s -B 192.168.1.1

# 设置服务器端 CPU 绑定到特定核心，例如绑定到核心 2
iperf3 -s -A 2

# 以 JSON 格式输出测速结果
iperf3 -s -J

# 服务器端以 JSON 流模式输出数据
iperf3 -s --json-stream

# 服务器日志输出到指定文件
iperf3 -s --logfile /var/log/iperf3.log

# 在每个报告间隔强制刷新输出
iperf3 -s --forceflush

# 服务器空闲指定时间后自动重启（例如 300 秒）
iperf3 -s --idle-timeout 300

```

### 作为客户端：

```
# 连接 iperf3 服务器进行测速（默认 TCP 模式）
iperf3 -c 192.168.1.1

# 连接服务器并指定端口
iperf3 -c 192.168.1.1 -p 5000

# 使用 UDP 模式进行测速
iperf3 -c 192.168.1.1 -u

# 设置 UDP 目标带宽（例如 50Mbit/s）
iperf3 -c 192.168.1.1 -u -b 50M

# 设定测速时间（例如 30 秒）
iperf3 -c 192.168.1.1 -t 30

# 设定要发送的总数据量（例如 100MB）
iperf3 -c 192.168.1.1 -n 100M

# 设定要发送的块数（例如 10000 块）
iperf3 -c 192.168.1.1 -k 10000

# 并行多个连接进行测速（例如 5 个）
iperf3 -c 192.168.1.1 -P 5

# 反向模式（服务器向客户端发送数据）
iperf3 -c 192.168.1.1 -R

# 双向模式（服务器和客户端同时发送和接收数据）
iperf3 -c 192.168.1.1 --bidir

# 设置 TCP 窗口大小（例如 512KB）
iperf3 -c 192.168.1.1 -w 512K

# 指定 TCP 拥塞控制算法（Linux & FreeBSD）
iperf3 -c 192.168.1.1 -C cubic

# 设置最大 TCP 段大小（MSS，例如 1460 字节）
iperf3 -c 192.168.1.1 -M 1460

# 禁用 Nagle 算法（适用于小数据包低延迟传输）
iperf3 -c 192.168.1.1 -N

# 强制使用 IPv4 进行测速
iperf3 -c 192.168.1.1 -4

# 强制使用 IPv6 进行测速
iperf3 -c 192.168.1.1 -6

# 设置 IP 服务类型（ToS 值，例如 64）
iperf3 -c 192.168.1.1 -S 64

# 指定 IPv6 Flow Label（仅支持 Linux）
iperf3 -c 192.168.1.1 -L 100

# 使用零拷贝（Zero-Copy）方式发送数据
iperf3 -c 192.168.1.1 -Z

# 在测试前进行预热，忽略前 N 秒的数据（例如 5 秒）
iperf3 -c 192.168.1.1 -O 5

# 设置每行输出的标题（用于日志标识）
iperf3 -c 192.168.1.1 -T "测试1"

# 以 JSON 格式输出测速结果
iperf3 -c 192.168.1.1 -J

# 让客户端获取服务器端的测速结果
iperf3 -c 192.168.1.1 --get-server-output

# 在 UDP 测试中使用 64-bit 计数器
iperf3 -c 192.168.1.1 --udp-counters-64bit

# 使用固定模式的 payload 数据（而不是随机数据）
iperf3 -c 192.168.1.1 --repeating-payload

# 设置 IPv4 数据包不分片
iperf3 -c 192.168.1.1 --dont-fragment

```
