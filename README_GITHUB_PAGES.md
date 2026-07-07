# AirGap Scan Accumulator V4 GitHub Pages 操作手册

## 1. 目标

本工具用于“内网电脑向外网环境传输文本信息”。

本版使用：

```text
单个超大二维码
NanoScan 网页扫码累加
缺片补扫
手动粘贴兜底
```

## 2. 仓库结构

把压缩包内容完整上传到一个 GitHub 仓库根目录：

```text
airgap-scan-receiver/
├── .nojekyll
├── index.html
├── sender_scan_v4.html
├── receiver_nanoscan_v4.html
├── README.md
└── README_GITHUB_PAGES.md
```

## 3. GitHub Pages 部署步骤

### 3.1 新建仓库

建议仓库名：

```text
airgap-scan-receiver
```

### 3.2 上传文件

网页方式：

```text
Add file → Upload files → 拖入所有文件 → Commit changes
```

命令行方式：

```bash
git init
git add .
git commit -m "init airgap scan accumulator"
git branch -M main
git remote add origin https://github.com/<your-user>/airgap-scan-receiver.git
git push -u origin main
```

### 3.3 开启 GitHub Pages

进入仓库：

```text
Settings → Pages
```

选择：

```text
Source: Deploy from a branch
Branch: main
Folder: /root
Save
```

几分钟后访问：

```text
https://<your-user>.github.io/airgap-scan-receiver/
```

接收端：

```text
https://<your-user>.github.io/airgap-scan-receiver/receiver_nanoscan_v4.html
```

发送端备份：

```text
https://<your-user>.github.io/airgap-scan-receiver/sender_scan_v4.html
```

## 4. 使用流程

### 4.1 内网发送端

在内网电脑打开本地文件：

```text
sender_scan_v4.html
```

操作：

```text
1. 粘贴要传输的文本
2. 点击“生成分片”
3. 点击“大屏模式/退出”
4. 点击“自动播放”
```

推荐参数：

```text
每片字节：300
纠错：Q
QR 像素：14
留白：8
播放间隔：2200ms
```

### 4.2 外网接收端

手机打开 GitHub Pages 上的：

```text
receiver_nanoscan_v4.html
```

操作：

```text
1. 点击“加载 NanoScan”
2. 点击“开始扫码累加”
3. 允许摄像头权限
4. 让蓝色框覆盖发送端超大二维码
5. 接收端扫到新分片后自动累加
6. 等待发送端切下一片
7. 收齐后自动输出原文
```

### 4.3 缺片补扫

如果第一轮没收齐，接收端会显示缺失分片，例如：

```text
3, 8, 19, 42
```

操作：

```text
1. 接收端点击“复制缺片”
2. 把缺片列表输入发送端的“缺片播放列表”
3. 发送端点击“只播放缺片”
4. 再次扫码累加
```

### 4.4 手动粘贴兜底

如果网页扫码仍不稳定，可以用微信或其他扫码器识别单个二维码，复制识别结果：

```text
QRZ2|xxxxxx
```

粘贴到接收端“手动补充”，一行一个，然后点击“导入手动内容”。

## 5. 推荐参数

| 场景 | 每片字节 | 纠错 | QR 像素 | 留白 | 播放间隔 |
|---|---:|---|---:|---:|---:|
| 默认 | 300 | Q | 14 | 8 | 2200ms |
| 最稳 | 220～250 | H/Q | 16～18 | 10 | 2500ms |
| 速度优先 | 350～450 | M/Q | 12～14 | 8 | 1800～2200ms |

接收端建议：

| 参数 | 推荐值 |
|---|---|
| FPS | 5 |
| 分辨率 | 720×720 |
| 缩放 | 1.5 |
| 成功暂停 | 1000ms |

## 6. 常见问题

### 6.1 接收端打不开摄像头

检查：

```text
1. 是否 HTTPS
2. 是否允许摄像头权限
3. GitHub Pages 是否发布完成
4. 是否用手机浏览器打开
```

### 6.2 NanoScan 加载失败

可能原因：

```text
1. 手机网络访问不了 CDN
2. 浏览器不支持 ESM 动态 import
3. 公司网络拦截 GitHub/CDN
```

可以刷新重试，或用“手动补充”模式兜底。

### 6.3 第一轮扫不全

正常，使用缺片补扫：

```text
复制缺片 → 发送端只播放缺片 → 继续扫
```

## 7. 安全说明

- 仓库和 GitHub Pages 页面是公开可访问的。
- 不要把待传输文本写入仓库文件。
- 文本内容只在浏览器本地压缩、编码、扫码、还原。
- 接收端进度保存在当前浏览器 localStorage 中。
- 不建议用它传输密码、密钥、证书等高敏感信息。
