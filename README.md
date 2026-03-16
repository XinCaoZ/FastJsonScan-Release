# FastJsonScan

> Fastjson 漏洞扫描工具 - 现代化图形界面

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-2.0.0-green.svg)](package.json)
[![Platform](https://img.shields.io/badge/platform-Electron-lightgrey.svg)](electron/)

## ✨ 特性

- 🎯 **漏洞扫描** - 自动检测 Fastjson 版本及可用利用链
- 💣 **多种 Gadget** - 支持 1.2.24, 1.2.47, 1.2.68, 1.2.80 等多版本
- 🔥 **JNDI RCE** - 支持 RMI, LDAP 等多种 JNDI 协议
- 🐚 **内存马** - 支持多种内存 Webshell 生成
- 📊 **依赖探测** - 自动扫描项目依赖的 Fastjson 版本
- 🎨 **现代 UI** - 基于 Electron + Vue3 的跨平台桌面应用
- 📝 **实时日志** - 实时查看扫描和利用过程
- 🔄 **历史记录** - 保存请求历史，方便复用

## 📖 功能说明

### 漏洞利用

支持多种 Fastjson 反序列化利用链：

#### Fastjson 1.2.24
- TemplatesImpl
- BCEL
- Spring Echo
- JdbcRowSetImpl

#### Fastjson 1.2.47
- BCEL
- TemplatesImpl
- Spring Echo
- C3P0
- H2
- JNDI DataSource Factory

#### Fastjson 1.2.68+
- 新版本特性利用

### JNDI 攻击

支持以下 JNDI 协议：

| 协议 | 说明 |
|------|------|
| RMI | Java RMI 服务 |
| LDAP | 轻量级目录访问协议 |
| DNS | DNSLog 探测 |

### 内存马

支持生成多种内存 Webshell：

- Antsword 兼容
- Behinder 兼容
- Godzilla 兼容
- 自定义内存马

## 🛠️ 使用方法

### 1. 扫描目标

在 **请求编辑器** 中配置：
- 目标 URL
- HTTP 方法
- 请求头
- 请求体

### 2. 探测版本

点击 **版本探测** 按钮，自动识别 Fastjson 版本。

### 3. 选择 Gadget

根据版本选择合适的利用链：
- TemplatesImpl
- BCEL
- JNDI DataSource
- ...

### 4. 配置 JNDI

配置 JNDI 服务器：
- 协议类型（RMI/LDAP）
- 服务器地址
- 端口

### 5. 生成并发送

点击 **生成 Payload**，然后发送到目标。

### 6. 查看结果

在 **响应查看器** 和 **日志面板** 中查看结果。

## 📂 项目结构

```
FastJsonScan/
├── backend/              # Java 后端
│   ├── src/main/java/
│   │   ├── payload/     # Payload 生成
│   │   ├── service/     # 业务逻辑
│   │   └── utils/       # 工具类
│   └── pom.xml          # Maven 配置
├── frontend/             # Vue3 前端
│   └── src/
│       ├── components/    # Vue 组件
│       ├── stores/        # 状态管理
│       └── types/        # TypeScript 类型
├── electron/             # Electron 主进程
├── resources/            # 资源文件
└── scripts/             # 构建脚本
```

## 🔧 配置

在 **设置面板** 中可以配置：

- 默认 JNDI 服务器地址
- DNSLog 服务器
- 超时时间
- 代理设置
- 日志级别

## 📝 常见问题

### Q: 扫描超时怎么办？

A: 在设置中增加超时时间，或使用代理。

### Q: JNDI 回连失败？

A: 确保你的服务器可以从目标访问，检查防火墙设置。

### Q: Payload 无法触发？

A: 检查目标是否使用了 WAF 或防护设备，尝试修改 User-Agent 或使用代理。

## ⚠️ 免责声明

本项目仅供安全研究和授权测试使用。未经授权对系统进行扫描或利用是违法行为。使用本工具造成的任何后果由使用者自行承担。

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

[MIT License](LICENSE)

## 🔗 相关资源

- [Fastjson 官方文档](https://github.com/alibaba/fastjson)
- [Fastjson 漏洞分析](https://github.com/threedr3am/learnjavabug)
- [JNDI 注入详解](https://www.anquanke.com/post/id/211328)

## 🌟 Star History

如果这个项目对你有帮助，请给个 Star ⭐

---

**Author:** XinCaoZ
