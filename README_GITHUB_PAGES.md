# AirGap Scan Accumulator V4.2.4 GitHub Pages 操作手册

## 1. 部署

把全部文件上传到 GitHub 仓库根目录：

```text
.nojekyll
index.html
sender_scan_v4_2_4.html
receiver_nanoscan_v4_2_4_fast.html
README.md
README_GITHUB_PAGES.md
```

进入 GitHub 仓库：

```text
Settings → Pages → Deploy from a branch → main / root
```

访问：

```text
https://<your-user>.github.io/<repo>/
```

## 2. 推荐主流程

发送端打开：

```text
sender_scan_v4_2_4.html
```

使用默认参数：

```text
每片字节：1200
播放间隔：600ms
```

接收端打开：

```text
receiver_nanoscan_v4_2_4_fast.html
```

使用默认参数：

```text
模式：跟手优先：相机常开低频识别
FPS：1
分辨率：360
接收冷却：500ms
```

核心节奏：

```text
发送端每 600ms 切一张
接收端扫到后冷却 500ms
接收端比发送端早约 800ms 恢复识别
```

这样接收端可以提前准备扫下一片，交互会比完全一致更顺。

## 3. 仍然卡顿时

优先保持：

```text
跟手优先
FPS=1
分辨率=360
```

再调整：

```text
发送端播放间隔 3000 → 3500ms
接收端接收冷却 500 → 700ms
```

## 4. 漏扫时

调整：

```text
接收端接收冷却 500 → 400ms
发送端每片字节 1200 → 900
发送端播放间隔 3000 → 3500ms
```

## 5. 停止摄像头

点击：

```text
停止摄像头
```

V4.2.4 会：

```text
调用 NanoScan stopScan
停止 video.srcObject tracks
停止 getUserMedia 捕获到的所有 streams
清空 camera 容器
取消自动定时器
```
