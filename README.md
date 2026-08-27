# 我的旅游剧本

一个可直接打开、也适合部署到 GitHub Pages 的科技感中国旅游地图网页。

## 功能

- 打开页面后先显示“欢迎来到我的旅游剧本”，停留约 2 秒后以烟雾效果消散。
- 随后展示动态科技感中国地图，包含粒子、连线、流光与霓虹效果。
- 地图包含有照片城市和无照片城市两类标记。
- 点击有照片城市后，可全屏查看该城市的照片，并支持左右切换。
- 点击无照片城市后，显示“城市名 + 已到达 · 照片待补充”信息卡。
- 电脑端和移动端均已适配。

## 本地打开

直接双击 `index.html` 即可打开，无需安装依赖或启动服务器。

如需用本地服务器预览，可在本目录执行：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000/`。

## 部署到 GitHub Pages

1. 把这个目录推送到 GitHub 仓库。
2. 打开仓库的 `Settings` → `Pages`。
3. 在 `Source` 中选择分支（例如 `main`）和根目录 `/`。
4. 保存后访问 GitHub 提供的 Pages 地址即可。

网页全部使用相对路径，放在子目录或 Pages 默认地址下都能正常工作。

## 目录结构

```text
.
├── index.html
├── README.md
├── THIRD_PARTY_NOTICES.md
└── assets
    ├── echarts.min.js
    ├── china-map.js
    ├── cities-data.js
    ├── lxgw-wenkai-500.woff2
    └── photos
        ├── 北京
        ├── 上海
        └── ...
```

## 修改城市或照片

编辑 `assets/cities-data.js` 中的 `window.TRAVEL_DATA.cities` 即可：

- `name`：城市名称。
- `lng`、`lat`：城市坐标。
- `hasPhotos`：是否有照片。
- `photos`：该城市照片的相对路径列表。

照片放在 `assets/photos/<城市名>/` 下，并在 `cities-data.js` 中填写对应路径。
