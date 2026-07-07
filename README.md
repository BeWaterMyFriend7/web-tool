# AirGap Scan Accumulator V4.2.2 - Auto Loop Single Scan

## 本版修正

你说得对：发送端是自动轮播，接收端不应该每片都手动触发。V4.2.2 改为默认“自动单片循环”。

流程：

```text
点击一次“开始自动接收”
→ NanoScan 扫当前分片
→ 扫到新分片后立刻 stopScan + 停止 video tracks + 清空预览容器
→ 等待 600ms
→ 自动重新打开摄像头继续扫下一片
→ 直到收齐或用户点击“停止摄像头”
```

## 关键改动

1. 接收端默认勾选“跟随发送端自动轮播”。
2. 接收端按钮改为“开始自动接收”，不需要每片手动点。
3. 停止按钮会取消自动重启定时器，避免停止后又自动打开摄像头。
4. 发送端分片大小真正提升到 2000，上限不再被脚本内部 800 限制。
5. 发送端默认每片字节 1200，播放间隔 4000ms，更适合接收端 stop/restart 模式。

## 文件

- index.html
- sender_scan_v4_2_2.html
- receiver_nanoscan_v4_2_2_auto.html
- README.md
- README_GITHUB_PAGES.md
- .nojekyll
