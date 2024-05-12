# Windows、MacOS 和 Linux 如何查找并停止占用端口的服务？


## Windows

```bash
# windows 查看占用端口的进程
netstat -ano|findstr <端口号>
# windows 停止进程
taskkill /f /t /im <进程id>
```

## MacOS 或 Linux

```bash
# 查看占用端口的进程
lsof -i:<port>
# 停止进程
kill <pid>
```

