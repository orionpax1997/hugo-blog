---
title: "Java 内存泄漏的定位"
date: 2023-08-17T15:47:29+08:00
tags: ["Essay"]
---

```bash
# 1. 查看相应端口的 Java 进程的 PID
lsof -i:<port>
# 2. 占用内存前 20 的 class 倒叙查看
jmap -histo:live <port> | head  -n  20
# 3. 上一步猜不出具体问题的话，导出 dump
jmap -dump:format=b,file=dump.hprof <port>
# 4. 使用 IDEA Profiler 打开 dump 看一眼 Biggest Objects 解决问题
```
