# yunzai-plugin-bili

Yunzai Bot 的 B 站链接自动解析插件。

## 功能

- 自动解析 B 站视频链接（`bilibili.com/video/BVxxx`、`b23.tv` 短链）
- 自动解析 B 站专栏 / 图文动态（`read/cvxxx`、`opus`）
- 支持 QQ 分享卡片（图文卡片、小程序卡片）触发解析
- 视频支持时长限制、自动下载合并音视频发送
- 专栏支持正文长度限制、图片数量限制

## 安装

在 Yunzai 根目录执行：

```bash
git clone <本仓库地址> plugins/yunzai-plugin-bili
```

或直接把本目录放进 `plugins/` 下，然后安装依赖：

```bash
pnpm install
```

## 配置

首次运行会在 `config/bili.yaml` 生成配置模板，也可手动创建：

```yaml
# B 站 Cookie，登录后从浏览器复制，用于获取更高画质和避免风控
cookie: ""

# 视频最大时长（秒），超过只发送预览和链接
max_duration: 600

# 是否解析专栏
parse_article: true

# 专栏正文最大字符数
max_chars: 2000

# 专栏最多附带图片数
max_images: 3

# 请求超时（毫秒）
timeout: 15000
```

## 依赖

- [axios](https://github.com/axios/axios)（Yunzai 通常已内置）
- [ffmpeg](https://ffmpeg.org/)（用于视频音轨合并，需系统安装并加入 PATH）

## 使用

直接在群里发送 B 站链接或分享卡片即可自动解析，无需任何指令。

## 许可

MIT
