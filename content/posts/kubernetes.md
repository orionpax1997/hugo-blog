---
title: "Kubernetes"
date: 2025-04-30T13:39:18+08:00
tags: ["Support"]
---

## 简介

Kubernetes 也称为 K8s，是用于自动部署、扩缩和管理容器化应用程序的开源系统。

{{< card "https://kubernetes.io/zh-cn/" >}}

## 应用场景

### 问题定位

```bash
# 查看所有 Pod 的信息
kubectl get pod -A -o wide
# 查看 Pod 详情
kubectl describe pod <NAME_PREFIX> [-n namespace]
# 流式查看日志
kubectl logs <POD_NAME> [-c container] -f [-n namespace]
# 进入 Pod 内部查看
kubectl exec -it <POD_NAME> [-c container] [-n namespace] -- sh
```
