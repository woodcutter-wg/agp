cd /sys/devices/system/cpu
# 查看核心
stress --cpu 4
# 4个CPU核心设置满载状态


free -h
              total        used        free      shared  buff/cache   available
Mem:           1.9G        101M        1.7G        8.5M        121M        1.7G
Swap:          4.0G          0B        4.0G
# 总内存2G，我们设置的告警阈值为内存使用率为%75则告警，2048*%75=1536M
# 表示运行3个进程，每个进程分配500M内存
stress --vm 3 --vm-bytes 500M --vm-keep
stress: info: [1032] dispatching hogs: 0 cpu, 0 io, 3 vm, 0 hdd
