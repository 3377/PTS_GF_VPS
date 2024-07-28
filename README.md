# 探针一键安装脚本[纯Docker]
## Install
```
bash <(curl -Ls https://raw.githubusercontent.com/Sm1rkBoy/monitor_config/main/install.sh)
```
脚本已集成哪吒探针的安装!

# 视频教程
## Docker搭建Grafana+Prometheus+Exporters企业级探针监控教程
[视频教程](https://www.youtube.com/watch?v=9QSw0G4jPqY)

## Docker搭建哪吒探针教程
[视频教程](https://www.youtube.com/watch?v=20MFvJoro2k)
# 操作步骤
1. 创建一个新面板,添加可视化
2. 创建一个变量,正则表达式填`^(?!MJJ's VPS).*`
 - fping_rtt_sum{job="$vpsname",instance="61.190.1.197"}/fping_rtt_count#平均延迟=总耗时/成功发包数
 - fping_rtt_sum{job="$vpsname",instance="36.34.22.19"}/fping_rtt_count#平均延迟=总耗时/成功发包数
 - fping_rtt_sum{job="$vpsname",instance="112.29.198.100"}/fping_rtt_count#平均延迟=总耗时/成功发包数
3. 修改标题为ping,然后时间选second保存

# 创建loss表
1. fping_lost_count{job="$vpsname",instance="61.190.1.197"}/fping_sent_count{job="$vpsname",instance="61.190.1.197"}  #丢包率=丢包数/总发包数
2. fping_lost_count{job="$vpsname",instance="36.34.22.19"}/fping_sent_count{job="$vpsname",instance="36.34.22.19"}  #丢包率=丢包数/总发包数
3. fping_lost_count{job="$vpsname",instance="112.29.198.100"}/fping_sent_count{job="$vpsname",instance="112.29.198.100"}  #丢包率=丢包数/总发包数
