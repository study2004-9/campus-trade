# DAY0 - 2026-05-19 ~ 2026-05-25（环境搭建）

> 实际用了 5 天完成完整环境搭建（含 GitHub SSH 配置），原计划一天。

## 装了什么

| 工具 | 安装路径 | 版本 |
|------|----------|------|
| JDK 17 | D:\Java\jdk-17\ | Temurin 17.0.19 |
| IntelliJ IDEA | D:\IntelliJ IDEA Community Edition 2024.3.5 | 2024.3.5 CE |
| Git | D:\Git\ | 2.54.0 |
| MySQL | C:\Program Files\MySQL\MySQL Server 8.4\ | 8.4.9 |
| DBeaver | D:\DBeaver\ | 26.0.5 CE |
| Apifox | D:\Apifox\ | 2.8.30 |
| Obsidian | D:\Obsidian\ | 1.12.7 |

## 环境验证

```
java -version    → openjdk version "17.0.19" ✅
mysql --version  → mysql  Ver 8.4.9 ✅
git --version    → git version 2.54.0 ✅
```

## 遇到的问题与解决

### 1. 旧 OpenJDK 24 冲突
- C 盘装了 OpenJDK 24，卸载后安装 JDK 17
- 旧版本占 C 盘约 198MB，已清理

### 2. MySQL CLI PATH 未配
- MySQL Server 8.4 安装后命令行无法直接使用
- 已将 MySQL bin 目录加入系统 PATH，cmd/PowerShell 可直连

### 3. GitHub 国内访问问题
- HTTPS 方式经常超时（ERR_CONNECTION_TIMED_OUT）
- 尝试修改 hosts 文件指向可用 IP，但 IP 几小时内就会被封
- **最终方案：SSH over port 443**（走 ssh.github.com），绕过 SNI 封锁，稳定可用

### 4. Git 与 GitHub 配置
- 用户名：`study2004-9`
- 邮箱：`2015496449@qq.com`
- SSH 密钥：ed25519，已上传 GitHub
- 远程仓库：`git@github.com:study2004-9/campus-trade.git`
- 连接方式：SSH（443 端口），不依赖 HTTPS

### 5. 上下文压缩踩坑
- Obsidian 安装包实际已下载完成（282MB），压缩后丢失上下文导致重复下载
- SSH 公钥在压缩时被替换为错误值，需删除旧 key 重新上传
- **对策**：每次从压缩恢复后，先 `ls` / 读文件确认实际状态，不凭记忆操作

## 项目结构

```
D:\projects\campus-trade\
├── DAY0.md              ← 环境搭建日志
├── screenshots/         ← 截图（如有）
└── src/
    └── main/
        ├── java/        ← Java 源代码
        └── resources/   ← 配置文件
```

## 关键决策

| 决策 | 选择 | 理由 |
|------|------|------|
| 笔记工具 | Obsidian | 本地 Markdown、免费、不占 C 盘 |
| MySQL 客户端 | DBeaver | 免费、功能全、已装好 |
| API 测试 | Apifox | 替代 Postman，国内访问快 |
| GitHub 连接 | SSH over 443 | 绕过墙，稳定 |
| OOP 复习策略 | 边写项目边查，不重头学 | 比重新看视频有效 |
