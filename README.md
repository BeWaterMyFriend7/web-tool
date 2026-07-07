# AirGap Scan Accumulator V4 - GitHub Pages 版

这是“单个超大二维码 + NanoScan 网页扫码累加”的版本。

## 文件

```text
index.html
sender_scan_v4.html
receiver_nanoscan_v4.html
README.md
README_GITHUB_PAGES.md
.nojekyll
```

## 核心流程

```text
内网发送端：文本 → LZW/none 压缩 → QRZ2 分片 → 单个超大二维码慢速播放
外网接收端：NanoScan 扫码 → 解析 QRZ2 → CRC 校验 → 累加分片 → 缺片提示 → 收齐还原
```

## 推荐参数

```text
每片字节：250～350
纠错级别：Q
QR 像素：14～18
留白：8
播放间隔：2000～2500ms
接收端 FPS：5
接收端分辨率：720×720
接收端缩放：1.5
```

## 注意

- `sender_scan_v4.html` 可以本地双击打开，不依赖外部库。
- `receiver_nanoscan_v4.html` 需要 HTTPS 和联网加载 NanoScan。
- GitHub Pages 页面是公网可访问的，仓库中不要放敏感数据；传输文本只在浏览器本地处理，不上传到 GitHub。
