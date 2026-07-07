# GitHub Pages 操作手册 - V4.3

## 1. 上传文件

把以下文件放到 GitHub 仓库根目录：

```text
.nojekyll
index.html
sender_scan_v4_3.html
receiver_nanoscan_v4_3.html
README.md
README_GITHUB_PAGES.md
```

## 2. 开启 GitHub Pages

进入仓库：

```text
Settings → Pages
```

选择：

```text
Deploy from a branch
main / root
```

## 3. 使用

发送端：

```text
sender_scan_v4_3.html
```

接收端：

```text
receiver_nanoscan_v4_3.html
```

## 4. 推荐节奏

```text
发送端播放间隔：600ms
接收端成功暂停：500ms
```

接收端比发送端短一点，可以提前恢复识别，等待下一张二维码。

## 5. 说明

V4.3 保留 V4 接收端的 NanoScan 连续扫描方式，不再使用后续版本的“扫到即停相机/重启相机”策略，因为那会导致不跟手和准确率下降。
