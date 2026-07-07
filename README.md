# AirGap Scan Accumulator V4.1 - Smooth NanoScan

## 文件

```text
index.html
sender_scan_v4_1.html
receiver_nanoscan_v4_1.html
README.md
README_GITHUB_PAGES.md
.nojekyll
```

## V4.1 优化点

1. 接收端删除自定义蓝色扫描框，改用 NanoScan 自带 `frame` / `marker`。
2. 顶部进度和提示移到相机画面外，不覆盖中心区域。
3. 接收端默认降低扫码强度：`fps=2`、`resolution=480×480`、`zoom=1.0`、`trick=false`。
4. 日志限制最多 50 条，减少 DOM 压力。
5. 发送端默认更稳：每片 280、纠错 Q、QR 像素 16、留白 8、播放间隔 2500ms。
