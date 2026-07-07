# AirGap Scan Accumulator V4.1 GitHub Pages 操作手册

## 1. 部署

把全部文件上传到 GitHub 仓库根目录：

```text
.nojekyll
index.html
sender_scan_v4_1.html
receiver_nanoscan_v4_1.html
README.md
README_GITHUB_PAGES.md
```

进入：

```text
Settings → Pages
```

选择：

```text
Deploy from a branch
main / root
```

## 2. 发送端使用

内网电脑打开：

```text
sender_scan_v4_1.html
```

推荐默认参数：

```text
每片字节：280
纠错：Q
QR 像素：16
留白：8
播放间隔：2500ms
```

## 3. 接收端使用

手机打开 GitHub Pages 上的：

```text
receiver_nanoscan_v4_1.html
```

操作：

```text
1. 点击“加载 NanoScan”
2. 点击“开始扫码累加”
3. 允许摄像头权限
4. 让发送端二维码进入 NanoScan 自带扫描区域
```

V4.1 去掉了我们自己的蓝色定位框，避免两套扫描框冲突；识别框和标记由 NanoScan 自己处理。

## 4. 卡顿时的建议

保持默认：

```text
FPS：2
分辨率：480×480
缩放：1.0
成功暂停：1500ms
```

如果识别慢，可以逐步调高：

```text
FPS：3 或 5
分辨率：640×640 或 720×720
缩放：1.2 或 1.5
```

## 5. 缺片补扫

接收端点击“复制缺片”，把缺片列表粘贴到发送端“缺片播放列表”，再点击“只播放缺片”。
