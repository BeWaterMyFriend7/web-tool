# AirGap Scan Accumulator V4.3

这版回退到 `receiver_nanoscan_v4.html` 的扫描核心，因为它实际识别效果最好；只做低风险优化：

1. 发送端默认分片大小改为 `1000`，上限 `2000`。
2. 发送端默认播放间隔改为 `600ms`。
3. 接收端冷却默认改为 `500ms`，略短于发送端播放间隔。
4. 接收端不再每个分片立刻同步写 localStorage，改为 500ms 延迟写入，减少主线程抖动。
5. 接收端日志最多保留 30 条。
6. 接收端停止摄像头时额外清理 video track 和 camera 容器。

## 文件

```text
index.html
sender_scan_v4_3.html
receiver_nanoscan_v4_3.html
README.md
README_GITHUB_PAGES.md
.nojekyll
```

## 建议参数

发送端：

```text
每片字节：1000
播放间隔：600ms
纠错：Q
留白：8
```

接收端：

```text
识别 FPS：5
分辨率：720×720
缩放：1.5
成功暂停：500ms
```

如果 1000 不稳，先降到 800；如果稳定，再试 1200～1600。
