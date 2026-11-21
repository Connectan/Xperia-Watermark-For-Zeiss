# Xperia Watermark For Zeiss

**日本語** | [English](README.en.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [한국어](README.ko.md)

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/version-1.0.1-brightgreen)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**ZEISS レンズを積んだ Xperia で撮った写真に、Xperia × ZEISS のロゴと撮影情報の透かしを入れる Android アプリです。**

写真の EXIF から機種名・焦点距離・F 値・シャッター速度・ISO・撮影日時を読み取り、写真の下にロゴと撮影情報の帯を付けて保存します。
対象は **ZEISS 搭載の Xperia で撮った写真だけ** です（ほかの機種の写真は一覧に出ません）。

> ZEISS 以外も含めて、すべての Xperia で使える版はこちら → [Xperia All Watermark](https://github.com/Connectan/Xperia-All-Watermark)

---

## ⚠️ 最初に読むべし（作者より）

- 配布している APK は **v1.0.1（完成版）** です。v1.0 を入れている人は、アンインストールせずにそのまま上書きでアップデートできます（v1.0.1 はアプリ内部の名前から `com.example` を取り除いた版です）。パッケージ名を `com.connectan.xperiawatermark.zeiss` にして、デバッグビルドではないリリース版にしました。
- Test Beta 3（パッケージ名 `com.example`）とはパッケージ名と署名が違うので、上書きでアップデートできません。Test Beta 3 を入れている人は、**アンインストールしてから** v1.0.1 を入れてください。
- 作者が Xperia を売ってしまって **もう実機で試す環境がありません**。そのため、今後の更新は未定です（というかほぼない）。
- でも **一切のバグなく、問題なく使えます**（Test Beta 3 の時点で作者が実機で確認済み。v1.0 はパッケージ名と署名を変えただけで、中身は同じです）。安心して使って、どうぞ。

---

## ダウンロード

👉 **[Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest) から APK をダウンロード**

ファイル名：`XperiaWatermarkForZeiss_v1.0.1.apk`（約 20 MB）
SHA-256：`5e12351f28cc1490e7f41f12b46f90c718aa708dc477482bc8655e4c82379dd2`

---

## できること

| 機能 | 内容 |
|---|---|
|  Xperia の写真を自動で探す | 端末内の写真をスキャンして、EXIF のメーカー（Sony）と機種名から **ZEISS 搭載 Xperia で撮った写真だけ** を一覧にします |
|  透かしを入れる | 写真の下に、Xperia ロゴ・ZEISS ロゴ・機種名・撮影情報を描いた帯を付けて、新しい画像として保存します（元の写真はそのまま） |
|  背景スタイル 2 種類 | **Pure White（白）** と **Cyan Gradient（青）** から選べます |
|  撮影日時の表示 | 右下に撮影日付・時刻を表示。オフにすると日付を消して、カメラ情報を目立たせます |
|  まとめて処理 | 複数選択・「すべて選択」で一気に保存。未処理の写真だけをまとめて処理することもできます |
|  処理済みが一目でわかる | 保存済みの写真には「白 済」「青 済」の印が付きます。もう一度保存（再保存）もできます |
|  保存先を選べる | **本体ストレージ** か **SD カード** を選べます（SD カードが無いときは本体に保存） |

### 透かしに入る情報

| 項目 | 例 |
|---|---|
| ロゴ | Xperia ロゴ ＋ ZEISS ロゴ |
| 機種名 | Xperia 1 V |
| 焦点距離 | 24mm |
| F 値 | F1.9 |
| シャッター速度 | 1/125s |
| ISO | ISO 100 |
| 撮影日時（オン/オフ可） | 2024.05.01 12:34 |

※ 例の数値はイメージです。実際は写真の EXIF に入っている値がそのまま使われます。

---

## 対応機種

アプリ内の判定リストに入っている機種（すべて ZEISS レンズ搭載モデル）です。

| 機種 | docomo | au | SoftBank |
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

- SIM フリー版・海外版も、写真の EXIF の機種名が上の機種として判定できれば使えます。
- **ZEISS が付いていない Xperia（10 シリーズなど）や、ほかのメーカーの写真には使えません。**
- 判定は「どの端末にインストールしたか」ではなく **「どの機種で撮った写真か」** で行います。なので、写真さえ ZEISS 搭載 Xperia で撮ったものなら、ほかの Android 端末でも透かしを入れられます。

---

## 使い方

1. アプリを開いて、写真へのアクセスを **許可** します
2. 「Scanning storage for Xperia photos...」のあと、対応する写真が一覧に出ます
3. 透かしを入れたい写真をタップして選びます（「すべて選択」もあります）
4. **透かし背景スタイル** を選びます：Pure White（白）／ Cyan Gradient（青）
5. **撮影日時の表示** をオン／オフします
6. **透かし画像の出力先** を選びます：本体ストレージ／SD カード
7. 「選択した ○ 枚に透かしを保存」を押すと、透かし入りの画像が保存されます

保存した写真には「白 済」「青 済」が付くので、どれを処理したかすぐわかります。

---

## インストール方法

1. [Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest) から APK をダウンロード
2. ダウンロードした APK をタップ
3. 「提供元不明のアプリ」の許可を求められたら、ブラウザ（またはファイルアプリ）に **このソースからのアプリを許可** をオンにする
4. 「インストール」を押す

> Google Play 以外からのインストールになるので、Play プロテクトの警告が出ることがあります。その場合は「詳細」→「インストールする」で進めてください。

---

## 動作環境

| 項目 | 内容 |
|---|---|
| Android | **7.0 以上**（API 24〜） |
| ターゲット | Android 16（API 36） |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 写真 | ZEISS 搭載 Xperia で撮った JPEG（EXIF 付き） |

---

## 使う権限

| 権限 | 何に使うか |
|---|---|
| 写真と動画へのアクセス（`READ_MEDIA_IMAGES`） | 端末内の写真を探して、透かしを入れるため（Android 13 以降） |
| ストレージの読み取り（`READ_EXTERNAL_STORAGE`） | 同上（Android 12 以前） |
| ストレージへの書き込み（`WRITE_EXTERNAL_STORAGE`） | 透かし入り画像を保存するため（Android 9 以前） |
| インターネット（`INTERNET` ほか） | アプリに含まれているライブラリが宣言しているもの |

透かしの描画は端末の中（Android の Canvas）で行います。

---

## よくある質問

**Q. 写真が一覧に出てこない**
A. ZEISS 搭載 Xperia 以外で撮った写真、または EXIF（撮影情報）が消えている写真は出てきません。SNS から保存した画像や、編集アプリで書き出した画像は EXIF が消えていることが多いです。

**Q. 元の写真は上書きされる？**
A. されません。透かし入りの画像を **別のファイルとして** 保存します。

**Q. SD カードに保存できない**
A. SD カードが入っていないとき、または認識できないときは「本体ストレージ (SD未検出)」になり、本体に保存されます。

**Q. 同じ写真をもう一回処理したい**
A. 「済」が付いた写真も選び直せば **再保存** できます。

**Q. Test Beta 3 から上書きできない**
A. v1.0 はパッケージ名（`com.connectan.xperiawatermark.zeiss`）と署名が変わったので、別のアプリとして扱われます。Test Beta 3 をアンインストールしてから入れてください。

---

## 作った人

**こねくたん**（晓玲 清風）
- サイト：https://connectan.github.io
  
技適なし中華スマホ沼の住人。

---

## 注意

- 「Xperia」は Sony Group Corporation の、「ZEISS」は Carl Zeiss AG の商標です。
- このアプリは **個人が作った非公式アプリ** で、Sony・ZEISS とは関係ありません。
- 使用は自己責任でお願いします。
