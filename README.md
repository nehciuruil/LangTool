# LangTool - Windows CLI 编程语言安装工具
LangTool 是一款专为 Windows 10/11 64 位系统设计的命令行（CLI）工具，旨在**一键安装主流编程语言**并自动配置系统 PATH 环境变量，无需手动下载、解压、配置，彻底简化开发者的环境搭建流程。

## 🌟 功能特性
### 核心功能
- **多语言支持**：一键安装 Python、Java (JDK)、Node.js、Go、Rust、PHP、Ruby、.NET SDK、Perl、Lua 共 10 种主流编程语言。
- **灵活版本选择**：支持安装指定版本（如 `langtool install python 3.12.1`）或最新稳定版（`langtool install java latest`）。
- **自动配置环境**：安装后自动将编程语言可执行路径添加到**系统级 PATH**，无需手动修改注册表。
- **完整 CLI 命令集**：支持安装、卸载、版本查询、已安装语言检查等全生命周期管理。
- **友好的权限提示**：权限不足时给出清晰的中文指引，避免程序崩溃。
- **断点续传下载**：大文件下载中断后可继续，无需重新下载。

### 工具特性
- 纯命令行交互，无图形界面，轻量高效。
- 打包为独立安装包，安装时自动将工具自身添加到系统 PATH，全局可用。
- 64 位 Windows 专属，适配 Win10/11 所有主流版本。

## 📥 安装步骤
### 通过安装包安装（推荐）
1. 下载最新版安装包 `langtool_setup_64bit.exe`；
2. 双击安装包，按提示完成安装（自动获取管理员权限）；
3. **重启所有命令行终端（CMD/PowerShell）**，输入 `langtool --help` 验证安装：
   ```bash
   langtool --help
   ```
   若输出帮助信息，说明工具已全局可用。

### 核心命令列表
| 命令 | 说明 | 示例 |
|------|------|------|
| `install <语言> [版本]` | 安装指定语言（默认最新版） | `langtool install python 3.12.1`、`langtool install java latest` |
| `uninstall <语言> [版本]` | 卸载指定语言（不填版本则卸载所有版本） | `langtool uninstall nodejs`、`langtool uninstall go 1.21.6` |
| `list` | 列出所有支持的编程语言 | `langtool list` |
| `check` | 检查已安装的语言及版本 | `langtool check` |
| `version` | 查看工具自身版本 | `langtool version` |
| `--help` | 查看所有命令的帮助信息 | `langtool --help`、`langtool install --help` |

### 常用示例
```bash
# 安装最新版 Node.js
langtool install nodejs latest

# 安装指定版本的 Java (JDK 17.0.9)
langtool install java 17.0.9

# 检查已安装的所有语言
langtool check

# 卸载所有版本的 Rust
langtool uninstall rust

# 查看工具版本
langtool version
```

## ❌ 常见问题
### 1. 运行命令提示「拒绝访问（WinError 5）」
- **原因**：未以管理员身份运行 CMD/PowerShell，无法修改系统级目录（如 `C:\Program Files`）。
- **解决方案**：右键 CMD/PowerShell → 「以管理员身份运行」，再执行命令。

### 2. 下载速度慢/下载失败
- **原因**：部分编程语言的下载源为国外服务器，网络波动导致。
- **解决方案**：
  1. 检查网络连接，重试下载命令。

## ⚠️ 注意事项
1. **系统要求**：仅支持 Windows 10/11 64 位系统，32 位系统不兼容。
2. **管理员权限**：安装/卸载语言时必须以管理员身份运行命令行，否则无法操作系统目录和 PATH。
3. **PATH 生效**：修改 PATH 后需重启终端才能完全生效，若仍不生效可手动检查系统环境变量。
4. **安装目录**：默认安装到 `C:\Program Files`（系统级目录），如需修改可编辑 `langtool.py` 中的 `LANG_CONFIG` 里的 `install_dir`。
5. **版本兼容性**：部分语言的旧版本可能不支持 64 位 Windows，建议优先安装最新稳定版。

## 📞 反馈与贡献
若遇到 Bug 或有功能建议，可通过以下方式反馈：
- 提交 Issue；
- 邮件反馈（nehciuruil@126.com）。
