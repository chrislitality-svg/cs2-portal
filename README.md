# CS2 管家

一个纯静态的 Counter-Strike 2 小工具门户页面（单文件 `index.html`），聚合展示 CS2 官方新闻等信息。数据来自 Steam 公开 API（`api.steampowered.com`），**无后端、无需登录、不采集任何数据**。

![License](https://img.shields.io/github/license/chrislitality-svg/cs2-portal) ![Language](https://img.shields.io/github/languages/top/chrislitality-svg/cs2-portal) ![Last Commit](https://img.shields.io/github/last-commit/chrislitality-svg/cs2-portal)

## 主要功能

- **CS2 官方动态**：调用 Steam 公开接口 `ISteamNews/GetNewsForApp`（appid 730）拉取最近 6 条新闻，接口失败时自动回落到页面内置的兜底新闻。
- **工具入口卡片**：「我的租赁」（饰品租赁到期提醒）与「3D 战术沙盘」（three.js 道具点位规划）两张入口卡，链接到同域部署的另外两个页面（`/cs2/zl/`、`/cs2/zs/`，这两个页面不在本仓库内）。
- **纯前端视觉**：卡片鼠标跟随 3D 倾斜、滚动进场动画（尊重系统「减少动态效果」设置）、移动端自适应布局。

## 技术栈

单文件 HTML + CSS + 原生 JavaScript，零依赖、无框架、无构建步骤。

## 目录结构

```
index.html   全部页面（样式、脚本内联）
LICENSE      MIT
```

## 快速开始 / 部署

```bash
# 方式一：浏览器直接打开
open index.html

# 方式二：部署到任意静态服务器或 GitHub Pages
# 把仓库放到 Web 根目录即可，无任何服务端要求
```

注意：页面中的工具入口卡使用绝对路径 `/cs2/zl/`、`/cs2/zs/`，需要对应的租赁管理与战术沙盘页面部署在同一域名下才会生效；单独打开 `index.html` 时这两个链接不可用（新闻功能不受影响）。

## 配置

无需配置，没有环境变量。如需调整新闻条数或摘要长度，修改 `index.html` 中请求 URL 的 `count` 与 `maxlength` 参数即可。

## 许可

[MIT](LICENSE)
