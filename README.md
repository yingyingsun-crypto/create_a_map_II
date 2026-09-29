# DC Park // 04%

一个面向“手机只剩 4% 电量、需要快速找到公园与基础设施”的华盛顿特区公园地图。

在线版本：<https://dc-park-04-terminal.esun6037.chatgpt.site/>

## 功能

- 显示 DC Department of Parks and Recreation（DPR）公园边界。
- 显示 National Park Service（NPS）公园与纪念地点。
- 搜索公园、地址、区域和地点类型。
- 筛选记录中的人类饮用水设施；湖泊、池塘和河流不计入饮用水。
- 经用户授权后，在浏览器中显示当前位置并寻找最近的 DPR 公园。
- 提供 Google Maps 导航链接。
- 为 Rock Creek Park 显示已核实的 NPS 简介、开放时间、游客中心、饮用水和卫生间信息。
- 对没有可靠数据的手机充电位置明确标记为“未核实”。

## 本地运行

这是一个没有构建步骤的静态网站。不要直接双击 `index.html`，因为浏览器可能阻止本地 GeoJSON 请求。请在仓库根目录启动静态服务器：

```bash
python3 -m http.server 8000 --directory dist
```

然后打开 <http://localhost:8000>。

定位功能通常要求 HTTPS，`localhost` 是浏览器普遍允许的本地开发例外。

## GitHub Pages

仓库包含 `.github/workflows/pages.yml`。推送到 `main` 分支后：

1. 打开 GitHub 仓库的 **Settings → Pages**。
2. 在 **Build and deployment** 中选择 **GitHub Actions**。
3. 运行或重新运行 `Deploy static site to GitHub Pages` workflow。

工作流会直接发布 `dist/`，不需要 Node.js、npm 或 API 密钥。

## 项目结构

```text
.
├── .github/workflows/pages.yml   # GitHub Pages 发布
├── dist/
│   ├── index.html                # 网站界面与交互逻辑
│   ├── data/
│   │   ├── parks.geojson         # DC DPR 公园边界快照
│   │   ├── nps.json              # NPS 公园地点快照
│   │   └── nps-facilities.json   # 已核实的 NPS 设施补充信息
│   └── vendor/leaflet/           # 本地保存的 Leaflet 运行文件
├── DATA_SOURCES.md               # 数据来源、范围与限制
└── README.md
```

## 隐私与限制

- 定位只在用户点击定位按钮后请求，并在浏览器中处理；网站代码不会保存或上传位置。
- 饮水数量来自公开数据快照，不保证饮水设施当前可用。
- NPS 点位不等同于完整公园边界。
- 网站没有可靠的公共手机充电数据库，因此不会将推测位置显示为已确认充电点。
- 数据来源与更新时间见 [DATA_SOURCES.md](DATA_SOURCES.md)。

## 技术

Vanilla HTML、CSS、JavaScript、Leaflet、OpenStreetMap 图块和浏览器 Geolocation API。

## 授权提示

本仓库暂未附带开源许可证。在将代码作为开源项目发布前，请根据你的课程或项目要求选择许可证（例如 MIT）。第三方代码、地图和数据仍受各自条款与署名要求约束。
