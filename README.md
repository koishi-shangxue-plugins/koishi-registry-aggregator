## Koishi Registry Sync

本项目已从**多镜像源整合**转变为**单一镜像源同步分发**，

专门同步 [koishi-actions/registry](https://github.com/koishi-actions/registry) 的插件市场数据并分发内容。

> 仓库地址： https://github.com/shangxueink/koishi-registry-aggregator
> 
> 镜像仓库地址： https://gitee.com/shangxueink/koishi-registry-aggregator

## 📦 使用方法

### 访问

| 镜像源                                                                                                            | 更新及时性            | 访问稳定性 | 推荐场景         |
| ----------------------------------------------------------------------------------------------------------------- | --------------------- | ---------- | ---------------- |
| [Gitee 镜像](https://gitee.com/shangxueink/koishi-registry-aggregator/raw/gh-pages/market.json)                   | ⭐⭐⭐⭐ 延迟同步        | ⭐⭐⭐⭐ 较佳 | 国内用户首选     |
| [JSDMirror CDN](https://cdn.jsdmirror.com/gh/shangxueink/koishi-registry-aggregator@gh-pages/market.json)         | ⭐⭐ 延迟更新（几小时） | ⭐⭐⭐⭐⭐ 极佳 | 国内用户稳定访问 |
| [jsDelivr CDN](https://cdn.jsdelivr.net/gh/shangxueink/koishi-registry-aggregator@gh-pages/market.json)           | ⭐⭐ 延迟更新（几小时） | ⭐⭐⭐⭐ 良好  | 通用备用方案     |
| [GitHub Pages](https://shangxueink.github.io/koishi-registry-aggregator/market.json)                              | ⭐⭐⭐⭐⭐ 实时同步        | ⭐⭐⭐ 一般   | 开发测试使用     |
| [GitHub Raw](https://github.com/shangxueink/koishi-registry-aggregator/raw/refs/heads/gh-pages/market.json)       | ⭐⭐⭐⭐⭐ 实时同步        | ⭐⭐⭐ 一般   | GitHub环境使用   |
| [GitHub Releases](https://github.com/shangxueink/koishi-registry-aggregator/releases/download/latest/market.json) | ⭐⭐⭐⭐⭐ 实时同步        | ⭐⭐⭐ 一般   | Releases专用     |

## ⚙️ 工作原理

1. **定时同步**：通过 GitHub Actions 每5分钟从 Q78KG 镜像源获取最新数据
2. **CDN加速**：自动刷新 jsDelivr CDN 缓存，确保全球访问速度
3. **双平台分发**：同步部署到 GitHub Pages 和 Gitee 仓库

## 🙏 鸣谢

特别感谢 [koishi-actions](https://github.com/koishi-actions) 提供稳定可靠的 Koishi 插件市场源。
特别感谢 [Q78KG (Hoshino-Yumetsuki)](https://github.com/Hoshino-Yumetsuki/koishi-registry) 提供稳定可靠的 Koishi 插件市场镜像源。

## 📝 许可证

MIT
