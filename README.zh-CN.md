# Xperia Watermark For Zeiss

[日本語](README.md) | [English](README.en.md) | **简体中文** | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/version-1.0-brightgreen)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**一款给搭载蔡司（ZEISS）镜头的 Xperia 拍摄的照片，加上 Xperia × ZEISS 标志和拍摄信息水印的 Android 应用。**

从照片的 EXIF 中读取机型、焦距、光圈、快门速度、ISO 和拍摄时间，在照片下方加上带有标志和拍摄信息的横条后保存。
只支持 **蔡司 Xperia 拍摄的照片**（其他机型的照片不会出现在列表中）。

> 想要不限蔡司、所有 Xperia 都能用的版本 → [Xperia All Watermark](https://github.com/Connectan/Xperia-All-Watermark)

---

## ⚠️ 必读（来自作者）

- 这里发布的 APK 是 **v1.0（正式版）**。包名改成了 `com.connectan.xperiawatermark.zeiss`，并且是正式（release）版本，不再是调试版本。
- Test Beta 3（包名 `com.example`）的包名和签名都不同，无法覆盖更新。装了 Test Beta 3 的话，请 **先卸载** 再安装 v1.0。
- 作者已经把 Xperia 卖掉了，**没有真机可以测试了**。所以之后会不会更新还没定（其实基本不会了）。
- 不过 **完全没有 bug，可以正常使用**（作者在 Test Beta 3 时已在真机上确认；v1.0 只改了包名和签名，内容完全相同）。放心用吧。

---

## 下载

👉 **[从 Releases 下载 APK](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)**

文件名：`XperiaWatermarkForZeiss_v1.0.apk`（约 20 MB）
SHA-256：`bf27ae5e4213ba6d2950033f721773c0476f0d0b467b7f476002890671daff2a`

---

## 功能

| 功能 | 说明 |
|---|---|
| 自动查找 Xperia 照片 | 扫描设备中的照片，根据 EXIF 中的厂商（Sony）和机型，只列出 **蔡司 Xperia 拍摄的照片** |
| 添加水印 | 在照片下方加上画有 Xperia 标志、蔡司标志、机型和拍摄信息的横条，另存为新图片（原照片保持不变） |
| 2 种背景样式 | 可选 **Pure White（白）** 和 **Cyan Gradient（青）** |
| 显示拍摄时间 | 在右下角显示拍摄日期和时间。关闭后会隐藏日期，让相机信息更醒目 |
| 批量处理 | 多选或“全选”后一次性保存。也可以只把未处理的照片一起处理 |
| 处理状态一目了然 | 已保存的照片会标上“白 済”“青 済”（済＝已完成）。也可以再次保存 |
| 可选保存位置 | 可选 **内部存储** 或 **SD 卡**（没有 SD 卡时保存到内部存储） |

### 水印包含的信息

| 项目 | 示例 |
|---|---|
| 标志 | Xperia 标志 ＋ 蔡司标志 |
| 机型 | Xperia 1 V |
| 焦距 | 24mm |
| 光圈 | F1.9 |
| 快门速度 | 1/125s |
| ISO | ISO 100 |
| 拍摄时间（可开关） | 2024.05.01 12:34 |

※ 示例数值仅供参考，实际会直接使用照片 EXIF 中的数值。

---

## 支持的机型

以下是应用内判定列表中的机型（全部为搭载蔡司镜头的机型）。

| 机型 | docomo | au | SoftBank |
|---|---|---|---|
| Xperia 1 II | SO-51A | SOG01 | — |
| Xperia 5 II | SO-52A | SOG02 | A002SO |
| Xperia 1 III | SO-51B | SOG03 | A101SO |
| Xperia 5 III | SO-53B | SOG05 | A103SO |
| Xperia 1 IV | SO-51C | SOG06 | A201SO |
| Xperia 5 IV | SO-54C | SOG09 | A204SO |
| Xperia 1 V | SO-51D | SOG10 | A301SO |
| Xperia 5 V | SO-53D | SOG12 | — |
| Xperia 1 VI | SO-51E | SOG13 | A401SO |
| Xperia 1 VII | SO-51F | SOG15 | A501SO |
| Xperia 1 VIII | SO-51G | SOG17 | A601SO |

- 无锁版、海外版只要照片 EXIF 中的机型能被判定为上述机型，也可以使用。
- **不支持没有蔡司镜头的 Xperia（如 10 系列）以及其他厂商的照片。**
- 判断依据不是“装在哪台手机上”，而是 **“照片是哪台机型拍的”**。所以只要照片是蔡司 Xperia 拍的，在其他 Android 手机上也能加水印。

---

## 使用方法

1. 打开应用，**允许** 访问照片
2. 显示“Scanning storage for Xperia photos...”之后，支持的照片会出现在列表里
3. 点选想加水印的照片（也有“全选”）
4. 选择 **水印背景样式**：Pure White（白）／ Cyan Gradient（青）
5. 打开或关闭 **拍摄时间显示**
6. 选择 **水印图片的保存位置**：内部存储／SD 卡
7. 点“为选中的 ○ 张保存水印”，就会保存加了水印的图片

※ 应用界面为日语，上面部分按钮名称为翻译。

保存过的照片会标上“白 済”“青 済”，哪张处理过一眼就能看出来。

---

## 安装方法

1. 从 [Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest) 下载 APK
2. 点击下载好的 APK
3. 如果提示“未知来源应用”，为浏览器（或文件管理器）打开 **允许来自此来源的应用**
4. 点“安装”

> 由于不是从 Google Play 安装，可能会出现 Play 保护机制的警告。遇到时请点“详细信息”→“仍然安装”。

---

## 运行环境

| 项目 | 内容 |
|---|---|
| Android | **7.0 及以上**（API 24+） |
| 目标版本 | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 照片 | 蔡司 Xperia 拍摄的 JPEG（带 EXIF） |

---

## 使用的权限

| 权限 | 用途 |
|---|---|
| 照片和视频（`READ_MEDIA_IMAGES`） | 查找设备中的照片并添加水印（Android 13 及以上） |
| 读取存储（`READ_EXTERNAL_STORAGE`） | 同上（Android 12 及以下） |
| 写入存储（`WRITE_EXTERNAL_STORAGE`） | 保存加了水印的图片（Android 9 及以下） |
| 网络（`INTERNET` 等） | 由应用内置的库声明 |

水印在设备本地绘制（使用 Android 的 Canvas）。

---

## 常见问题

**Q. 照片没有出现在列表里**
A. 非蔡司 Xperia 拍摄的照片，或 EXIF（拍摄信息）已被删除的照片不会显示。从社交平台保存的图片、用修图应用导出的图片，EXIF 常常已经没了。

**Q. 会覆盖原照片吗？**
A. 不会。加了水印的图片会 **另存为新文件**。

**Q. 无法保存到 SD 卡**
A. 没有插 SD 卡或无法识别时，会显示“本体ストレージ (SD未検出)”（内部存储，未检测到 SD），并保存到内部存储。

**Q. 想再处理一次同一张照片**
A. 带“済”标记的照片重新选中后就可以 **再次保存**。

**Q. 无法从 Test Beta 3 覆盖更新**
A. v1.0 的包名（`com.connectan.xperiawatermark.zeiss`）和签名都变了，会被当作另一个应用。请先卸载 Test Beta 3 再安装。

---

## 作者

**こねくたん（Connectan）**，又名 晓玲 清風
- 网站：https://connectan.github.io

深陷无技适国产手机坑的人。

---

## 注意

- “Xperia”是 Sony Group Corporation 的商标，“ZEISS”是 Carl Zeiss AG 的商标。
- 本应用是 **个人制作的非官方应用**，与 Sony、ZEISS 无关。
- 使用风险请自行承担。
