---
title: "Linux 的使用"
date: 2024-08-19T14:28:25+08:00
draft: true
tags: ["Support"]
---

## 使用场景

### 磁盘扩容

{{< card "https://juejin.cn/post/7389924114867683366" >}}

### 磁盘分配，把 home 的空间转移一部分给 root

{{< card "https://587v5.com/post/linux-ci-pan-fen-pei-%20ba-home-de-kong-jian-zhuan-yi-yi-bu-fen-gei-root.html" >}}

#### OpenRule 操作系统磁盘转移流程

```bash
# 先查看挂载情况
df -h
# 备份 /home 目录
tar -czvf home.tar.gz home/
mv home.tar.gz /tmp
# 取消挂载 /home
umount /home
# 删除逻辑卷
lvremove /dev/openeuler/home
# 扩展 / 空间
lvextend -L +800G /dev/openeuler/root
# 刷新生效
resize2fs /dev/mapper/openeuler-root
# 重新创建 home 逻辑卷
lvcreate -l 100%FREE -n /dev/openeuler/home
# 创建文件系统
mkfs.ext4 /dev/mapper/openeuler-home
# 挂载 /home
mount /dev/mapper/openeuler-home /home
# 恢复备份数据
tar -xzvf /tmp/home.tag.gz -C /home
```

