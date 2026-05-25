# DAY0 - 2026-05-19 ~ 2026-05-22（环境搭建）

> 实际用了 3 天完成环境搭建（中间穿插其他任务），原计划一天。

## 装了什么

| 工具 | 安装路径 | 版本 |
|------|---------|------|
| JDK 17 | D:\Java\jdk-17\ | Temurin 17.0.19 |
| IntelliJ IDEA | D:\IntelliJ IDEA Community Edition 2024.3.5 | 2024.3.5 CE |
| Git | D:\Git\ | 2.54.0 |
| MySQL | C:\Program Files\MySQL\MySQL Server 8.4\ | 8.4.9 |
| DBeaver | D:\DBeaver\ | 26.0.5 CE |
| Apifox | D:\Apifox\ | 2.8.30 |
| Obsidian | D:\Obsidian\ | 1.12.7 |

## 遇到的问题

1. **原系统有 OpenJDK 24，卸载后装了 JDK 17**——旧版本占 C 盘约 198MB，已清理
2. **MySQL CLI PATH 未配**——已加入系统 PATH，cmd 可直连
3. **Git 已装但还没配 GitHub 账号**——去 github.com 注册，然后在终端配：
   ```
   git config --global user.name "你的名字"
   git config --global user.email "你的邮箱"
   ```

## 环境验证

```
java -version    → openjdk version "17.0.19" ✅
mysql --version  → mysql  Ver 8.4.9 ✅
git --version    → git version 2.54.0 ✅
```
