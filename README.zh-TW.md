# Xperia Watermark For Zeiss

[日本語](README.md) | [English](README.en.md) | [简体中文](README.zh-CN.md) | **繁體中文** | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/version-1.0-brightgreen)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**一款替搭載蔡司（ZEISS）鏡頭的 Xperia 拍攝的照片，加上 Xperia × ZEISS 標誌和拍攝資訊浮水印的 Android App。**

從照片的 EXIF 讀取機型、焦距、光圈、快門速度、ISO 和拍攝時間，在照片下方加上帶有標誌和拍攝資訊的橫條後儲存。
只支援 **蔡司 Xperia 拍攝的照片**（其他機型的照片不會出現在清單中）。

> 想要不限蔡司、所有 Xperia 都能用的版本 → [Xperia All Watermark](https://github.com/Connectan/Xperia-All-Watermark)

---

## ⚠️ 必讀（來自作者）

- 這裡發布的 APK 是 **v1.0（正式版）**。套件名稱改成了 `com.connectan.xperiawatermark.zeiss`，而且是正式（release）版本，不再是除錯版本。
- Test Beta 3（套件名稱 `com.example`）的套件名稱和簽章都不同，無法覆蓋更新。裝了 Test Beta 3 的話，請 **先解除安裝** 再安裝 v1.0。
- 作者已經把 Xperia 賣掉了，**沒有實機可以測試了**。所以之後會不會更新還沒決定（其實大概不會了）。
- 不過 **完全沒有 bug，可以正常使用**（作者在 Test Beta 3 時已在實機上確認；v1.0 只改了套件名稱和簽章，內容完全相同）。放心用吧。

---

## 下載

👉 **[從 Releases 下載 APK](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)**

檔名：`XperiaWatermarkForZeiss_v1.0.apk`（約 20 MB）
SHA-256：`bf27ae5e4213ba6d2950033f721773c0476f0d0b467b7f476002890671daff2a`

---

## 功能

| 功能 | 說明 |
|---|---|
| 自動尋找 Xperia 照片 | 掃描裝置中的照片，依 EXIF 中的廠商（Sony）和機型，只列出 **蔡司 Xperia 拍攝的照片** |
| 加上浮水印 | 在照片下方加上畫有 Xperia 標誌、蔡司標誌、機型和拍攝資訊的橫條，另存成新圖片（原始照片保持不變） |
| 2 種背景樣式 | 可選 **Pure White（白）** 和 **Cyan Gradient（青）** |
| 顯示拍攝時間 | 在右下角顯示拍攝日期和時間。關閉後會隱藏日期，讓相機資訊更顯眼 |
| 批次處理 | 多選或「全選」後一次儲存。也可以只把未處理的照片一起處理 |
| 處理狀態一目了然 | 已儲存的照片會標上「白 済」「青 済」（済＝已完成）。也可以再次儲存 |
| 可選儲存位置 | 可選 **內部儲存空間** 或 **SD 卡**（沒有 SD 卡時儲存到內部儲存空間） |

### 浮水印包含的資訊

| 項目 | 範例 |
|---|---|
| 標誌 | Xperia 標誌 ＋ 蔡司標誌 |
| 機型 | Xperia 1 V |
| 焦距 | 24mm |
| 光圈 | F1.9 |
| 快門速度 | 1/125s |
| ISO | ISO 100 |
| 拍攝時間（可開關） | 2024.05.01 12:34 |

※ 範例數值僅供參考，實際會直接使用照片 EXIF 中的數值。

---

## 支援機型

以下是 App 內判定清單中的機型（全部為搭載蔡司鏡頭的機型）。

| 機型 | docomo | au | SoftBank |
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

- SIM-free 版、海外版只要照片 EXIF 中的機型能被判定為上述機型，也可以使用。
- **不支援沒有蔡司鏡頭的 Xperia（如 10 系列）以及其他廠商的照片。**
- 判斷依據不是「裝在哪支手機上」，而是 **「照片是哪個機型拍的」**。所以只要照片是蔡司 Xperia 拍的，在其他 Android 手機上也能加浮水印。

---

## 使用方式

1. 開啟 App，**允許** 存取照片
2. 顯示「Scanning storage for Xperia photos...」之後，支援的照片會出現在清單裡
3. 點選想加浮水印的照片（也有「全選」）
4. 選擇 **浮水印背景樣式**：Pure White（白）／ Cyan Gradient（青）
5. 開啟或關閉 **拍攝時間顯示**
6. 選擇 **浮水印圖片的輸出位置**：內部儲存空間／SD 卡
7. 點「為選取的 ○ 張儲存浮水印」，就會儲存加上浮水印的圖片

※ App 介面為日文，上面部分按鈕名稱為翻譯。

儲存過的照片會標上「白 済」「青 済」，哪張處理過一眼就看得出來。

---

## 安裝方式

1. 從 [Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest) 下載 APK
2. 點擊下載好的 APK
3. 如果出現「不明來源的應用程式」提示，請為瀏覽器（或檔案管理 App）開啟 **允許這個來源的應用程式**
4. 點「安裝」

> 由於不是從 Google Play 安裝，可能會出現 Play 安全防護的警告。遇到時請點「詳細資料」→「仍要安裝」。

---

## 運作環境

| 項目 | 內容 |
|---|---|
| Android | **7.0 以上**（API 24+） |
| 目標版本 | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 照片 | 蔡司 Xperia 拍攝的 JPEG（含 EXIF） |

---

## 使用的權限

| 權限 | 用途 |
|---|---|
| 相片和影片（`READ_MEDIA_IMAGES`） | 尋找裝置中的照片並加上浮水印（Android 13 以上） |
| 讀取儲存空間（`READ_EXTERNAL_STORAGE`） | 同上（Android 12 以下） |
| 寫入儲存空間（`WRITE_EXTERNAL_STORAGE`） | 儲存加上浮水印的圖片（Android 9 以下） |
| 網路（`INTERNET` 等） | 由 App 內建的函式庫宣告 |

浮水印在裝置本機繪製（使用 Android 的 Canvas）。

---

## 常見問題

**Q. 照片沒有出現在清單裡**
A. 非蔡司 Xperia 拍攝的照片，或 EXIF（拍攝資訊）已被刪除的照片不會顯示。從社群平台儲存的圖片、用修圖 App 匯出的圖片，EXIF 常常已經不見了。

**Q. 會覆蓋原始照片嗎？**
A. 不會。加上浮水印的圖片會 **另存成新檔案**。

**Q. 無法儲存到 SD 卡**
A. 沒有插 SD 卡或無法辨識時，會顯示「本体ストレージ (SD未検出)」（內部儲存空間，未偵測到 SD），並儲存到內部儲存空間。

**Q. 想再處理一次同一張照片**
A. 帶有「済」標記的照片重新選取後就可以 **再次儲存**。

**Q. 無法從 Test Beta 3 覆蓋更新**
A. v1.0 的套件名稱（`com.connectan.xperiawatermark.zeiss`）和簽章都變了，會被當作另一個 App。請先解除安裝 Test Beta 3 再安裝。

---

## 作者

**こねくたん（Connectan）**，又名 晓玲 清風
- 網站：https://connectan.github.io

深陷無技適中國手機坑的人。

---

## 注意

- 「Xperia」是 Sony Group Corporation 的商標，「ZEISS」是 Carl Zeiss AG 的商標。
- 本 App 是 **個人製作的非官方 App**，與 Sony、ZEISS 無關。
- 使用風險請自行承擔。
