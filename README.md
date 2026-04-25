# Koishi Registry Aggregator (Aggregator)

本项目用于同步并分发 Koishi 官方插件市场（Registry）的数据，主要面向国内用户提供高速、稳定的镜像访问。

## 🌟 特性

- **自动重定向跟踪**：自动获取 Koishi 官方最新的 `index.json` 地址（官方采用带哈希的 URL 进行分发）。
- **国内分发优化**：通过 Gitee 和多种 CDN 镜像，解决国内访问 GitHub 或官方 Registry 缓慢的问题。
- **自动缓存刷新**：集成 jsDelivr 等 CDN 的自动缓存刷新机制。
- **定时更新**：通过 GitHub Actions 自动保持数据最新。

## 📦 镜像地址

您可以直接在 Koishi 的设置中使用以下地址作为插件市场源：

| 镜像源 | 链接 | 更新及时性 | 推荐场景 |
| :--- | :--- | :--- | :--- |
| **Gitee 镜像 (推荐)** | `https://gitee.com/shangxueink/koishi-registry-aggregator/raw/gh-pages/market.json` | ⭐⭐⭐⭐ | 国内用户首选 |
| **JSDMirror CDN** | `https://cdn.jsdmirror.com/gh/shangxueink/koishi-registry-aggregator@gh-pages/market.json` | ⭐⭐⭐ | 极其稳定 |
| **jsDelivr CDN** | `https://cdn.jsdelivr.net/gh/shangxueink/koishi-registry-aggregator@gh-pages/market.json` | ⭐⭐ | 备用方案 |
| **GitHub Pages** | `https://shangxueink.github.io/koishi-registry-aggregator/market.json` | ⭐⭐⭐⭐⭐ | 海外/开发环境 |

## ⚙️ 工作原理

1. **探测**：程序访问 `https://registry.koishi.chat/`。
2. **重定向**：跟随官方的 302 重定向，获取形如 `index.[hash].json` 的真实数据地址。
3. **拉取**：下载最新的插件市场 JSON 数据。
4. **分发**：将数据保存为 `market.json` 并通过 GitHub Actions 推送到各分发渠道。
5. **刷新**：触发 CDN 缓存刷新接口。

## 🛠️ 开发与贡献

如果您想本地运行或改进本项目：

```bash
# 运行同步程序
go run main.go
```

## 🙏 鸣谢

- [Koishi](https://koishi.chat/) - 强大的跨平台机器人框架。
- [Koishi Registry](https://registry.koishi.chat/) - 官方插件市场。

## 📝 许可证

本项目遵循 [MIT](LICENSE) 许可证。
