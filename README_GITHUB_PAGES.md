# AirGap Scan Accumulator V4.2.2 GitHub Pages 操作手册

## 部署

上传全部文件到 GitHub 仓库根目录，开启 GitHub Pages：

```text
Settings → Pages → Deploy from a branch → main / root
```

## 页面

发送端：

```text
sender_scan_v4_2_2.html
```

接收端：

```text
receiver_nanoscan_v4_2_2_auto.html
```

## 推荐参数

发送端：

```text
每片字节：1200
最大：2000
纠错：Q
QR 像素：16
留白：8
播放间隔：4000ms
```

接收端：

```text
模式：自动单片循环
跟随发送端自动轮播：勾选
重启延迟：600ms
FPS：1
分辨率：480
缩放：1.0
```

## 使用流程

```text
1. 发送端生成分片并自动播放
2. 接收端点击“加载 NanoScan”
3. 接收端点击“开始自动接收”
4. 接收端扫到一片后会自动释放摄像头并自动重开
5. 收齐后自动还原文本
```

如果仍卡顿：

```text
发送端播放间隔调到 5000ms
接收端重启延迟调到 1200ms
分辨率保持 480 或降到 360
```
