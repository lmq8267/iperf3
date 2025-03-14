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

### 帮助信息：

```
iperf3 -h
用法: iperf3 [-s|-c 主机] [选项]
       iperf3 [-h|--help] [-v|--version]

服务器或客户端:
  -p, --port      #         监听/连接的服务器端口
  -f, --format   [kmgtKMGT] 结果显示格式: Kbits, Mbits, Gbits, Tbits
  -i, --interval  #         生成吞吐量报告的时间间隔（秒）
  -I, --pidfile file        将进程 ID 写入文件
  -F, --file name           发送/接收指定文件
  -A, --affinity n[,m]      设置 CPU 亲和性，绑定进程到核心 n
                             （可选: 客户端可指定 m 作为服务器端核心号）
  -B, --bind <主机>[%<设备>] 绑定到指定地址的网络接口
                            （可选: <设备> 等效于 `--bind-dev <设备>`）
  --bind-dev <设备>         绑定到指定网络接口 (使用 SO_BINDTODEVICE)
  -V, --verbose             输出更详细的信息
  -J, --json                以 JSON 格式输出
  --json-stream             以行分隔的 JSON 格式输出
  --logfile f               将输出发送到日志文件
  --forceflush              强制在每个时间间隔刷新输出
  --timestamps<=格式>       在每行输出前添加时间戳
                            （可选: "=" 和 strftime(3) 兼容的格式字符串）
  --rcv-timeout #           数据接收超时（默认 120000 毫秒）
  --snd-timeout #           TCP 数据未确认超时（单位: 毫秒，默认为系统设置）
  -d, --debug[=#]           输出调试信息
                            （可选: "=" 设置调试级别 1-4，默认 4 - 全部消息）
  -v, --version             显示版本信息并退出
  -h, --help                显示本帮助信息并退出

服务器专用:
  -s, --server              以服务器模式运行
  -D, --daemon              以守护进程模式运行服务器
  -1, --one-off             处理一个客户端连接后退出
  --server-bitrate-limit #[KMG][/#]   设置服务器的总比特率限制（默认 0 = 无限制）
                            （可选: 斜杠后跟秒数，用于平均总数据速率，默认 5 秒）
  --idle-timeout #          如果服务器空闲 # 秒则重启（默认: 不超时）

客户端专用:
  -c, --client <主机>[%<设备>] 以客户端模式运行，连接到 <主机>
                              （可选: <设备> 等效于 `--bind-dev <设备>`）
  -u, --udp                 使用 UDP 而非 TCP
  --connect-timeout #       控制连接建立超时（毫秒）
  -b, --bitrate #[KMG][/#]  目标比特率（单位: bit/sec，0 表示不限速）
                            （UDP 默认 1 Mbit/sec，TCP 默认不限速）
                            （可选: 斜杠后跟数据包数，用于突发模式）
  --pacing-timer #[KMG]     服务器定时器节奏，单位: 微秒（默认 1000）
                            （已废弃，仅用于兼容旧版本服务器）
  -t, --time      #         发送数据的持续时间（秒）（默认 10 秒）
  -n, --bytes     #[KMG]    发送指定字节数（替代 -t 选项）
  -k, --blockcount #[KMG]   发送指定数据块数（替代 -t 或 -n 选项）
  -l, --length    #[KMG]    读/写缓冲区长度
                            （默认: TCP 128 KB, UDP 1460 或动态调整）
  --cport         <端口>    绑定客户端特定端口（适用于 TCP 和 UDP，默认: 临时端口）
  -P, --parallel  #         并行运行的客户端流数
  -R, --reverse             反向模式（服务器发送，客户端接收）
  --bidir                   双向模式（客户端和服务器同时发送和接收数据）
  -w, --window    #[KMG]    设置发送/接收缓冲区大小
                            （间接设置 TCP 窗口大小）
  -C, --congestion <算法>   设置 TCP 拥塞控制算法（仅适用于 Linux 和 FreeBSD）
  -M, --set-mss   #         设置 TCP/SCTP 最大段大小（MTU - 40 字节）
  -N, --no-delay            禁用 Nagle 算法（启用 TCP/SCTP 低延迟模式）
  -4, --version4            仅使用 IPv4
  -6, --version6            仅使用 IPv6
  -S, --tos N               设置 IP 服务类型（0-255）
                            （支持十进制、八进制和十六进制，如 52, 064, 0x34）
  --dscp N or --dscp val    设置 IP DSCP 值（0-63 或符号表示）
                            （支持十进制、八进制和十六进制，参见 --tos）
  -L, --flowlabel N         设置 IPv6 流标签（仅 Linux 支持）
  -Z, --zerocopy            使用“零拷贝”方式发送数据
  -O, --omit N              预热测试 N 秒，忽略预热期间的统计信息
  -T, --title str           在每行输出前添加自定义前缀
  --extra-data str          在客户端和服务器 JSON 输出中包含额外数据
  --get-server-output       获取服务器端的测试结果
  --udp-counters-64bit      使用 64 位计数器统计 UDP 测试数据包
  --repeating-payload       使用重复模式填充数据，而非随机填充（类似 iperf2）
  --dont-fragment           设置 IPv4 不分片（Don't Fragment）标志

[KMG] 选项支持 K/M/G 后缀，分别代表千/兆/吉比特或字节。

```
