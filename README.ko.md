# Xperia Watermark For Zeiss

[日本語](README.md) | [English](README.en.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | **한국어**

![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![Target](https://img.shields.io/badge/target-Android%2016%20(API%2036)-blue)
![Status](https://img.shields.io/badge/status-Test%20Beta%203-orange)
![Made with](https://img.shields.io/badge/Jetpack%20Compose-Kotlin-7F52FF?logo=kotlin&logoColor=white)

**ZEISS 렌즈를 탑재한 Xperia로 찍은 사진에 Xperia × ZEISS 로고와 촬영 정보 워터마크를 넣는 Android 앱입니다.**

사진의 EXIF에서 기종명, 초점 거리, F값, 셔터 속도, ISO, 촬영 일시를 읽어, 사진 아래에 로고와 촬영 정보 띠를 붙여 저장합니다.
대상은 **ZEISS 탑재 Xperia로 찍은 사진뿐** 입니다(다른 기종의 사진은 목록에 나오지 않습니다).

> ZEISS 모델뿐 아니라 모든 Xperia에서 쓸 수 있는 버전은 여기 → [Xperia All Watermark](https://github.com/Connectan/Xperia-All-Watermark)

---

## ⚠️ 꼭 읽어 주세요 (제작자로부터)

- 배포 중인 APK는 **아직 샘플 상태(Test Beta 3)** 입니다. 패키지명이 `com.example` 그대로이고, 디버그 빌드입니다.
- 제작자가 Xperia를 팔아 버려서 **이제 실기기로 테스트할 환경이 없습니다**. 그래서 앞으로의 업데이트는 미정입니다(사실상 거의 없을 겁니다).
- 그래도 **버그 하나 없이 문제없이 쓸 수 있습니다**(제작자가 실기기에서 확인 완료). 안심하고 쓰세요.

---

## 다운로드

👉 **[Releases에서 APK 다운로드](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)**

파일명: `Xperia_Watermark_TestBeta.3_Lastest.apk`(약 22 MB)

---

## 주요 기능

| 기능 | 내용 |
|---|---|
| Xperia 사진 자동 탐색 | 기기 안의 사진을 스캔해서, EXIF의 제조사(Sony)와 기종명으로 **ZEISS 탑재 Xperia로 찍은 사진만** 목록으로 보여 줍니다 |
| 워터마크 넣기 | 사진 아래에 Xperia 로고, ZEISS 로고, 기종명, 촬영 정보를 그린 띠를 붙여 새 이미지로 저장합니다(원본 사진은 그대로) |
| 배경 스타일 2종 | **Pure White(흰색)** 와 **Cyan Gradient(파란색)** 중에서 고를 수 있습니다 |
| 촬영 일시 표시 | 오른쪽 아래에 촬영 날짜와 시간을 표시합니다. 끄면 날짜를 지워서 카메라 정보가 돋보이게 합니다 |
| 일괄 처리 | 다중 선택이나 "모두 선택"으로 한 번에 저장합니다. 미처리 사진만 모아서 처리할 수도 있습니다 |
| 처리 여부를 한눈에 | 저장한 사진에는 "白 済"(흰색 완료), "青 済"(파란색 완료) 표시가 붙습니다. 다시 저장할 수도 있습니다 |
| 저장 위치 선택 | **내장 저장소** 또는 **SD 카드** 를 고를 수 있습니다(SD 카드가 없으면 내장 저장소에 저장) |

### 워터마크에 들어가는 정보

| 항목 | 예시 |
|---|---|
| 로고 | Xperia 로고 + ZEISS 로고 |
| 기종명 | Xperia 1 V |
| 초점 거리 | 24mm |
| F값 | F1.9 |
| 셔터 속도 | 1/125s |
| ISO | ISO 100 |
| 촬영 일시(켜기/끄기 가능) | 2024.05.01 12:34 |

※ 예시 값은 참고용입니다. 실제로는 사진 EXIF에 들어 있는 값이 그대로 사용됩니다.

---

## 지원 기종

앱 안의 판정 목록에 들어 있는 기종입니다(모두 ZEISS 렌즈 탑재 모델).

| 기종 | docomo | au | SoftBank |
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

- 자급제판·해외판도 사진 EXIF의 기종명이 위 기종으로 판정되면 사용할 수 있습니다.
- **ZEISS가 없는 Xperia(10 시리즈 등)나 다른 제조사의 사진에는 사용할 수 없습니다.**
- 판정은 "어느 기기에 설치했는지"가 아니라 **"어느 기종으로 찍은 사진인지"** 로 합니다. 그래서 ZEISS 탑재 Xperia로 찍은 사진이라면 다른 Android 기기에서도 워터마크를 넣을 수 있습니다.

---

## 사용 방법

1. 앱을 열고 사진 접근을 **허용** 합니다
2. "Scanning storage for Xperia photos..." 이후 지원되는 사진이 목록에 나타납니다
3. 워터마크를 넣고 싶은 사진을 탭해서 선택합니다("모두 선택"도 있습니다)
4. **워터마크 배경 스타일** 을 고릅니다: Pure White(흰색) / Cyan Gradient(파란색)
5. **촬영 일시 표시** 를 켜거나 끕니다
6. **워터마크 이미지 저장 위치** 를 고릅니다: 내장 저장소 / SD 카드
7. "선택한 ○장에 워터마크 저장"을 누르면 워터마크가 들어간 이미지가 저장됩니다

※ 앱 화면은 일본어입니다. 위의 일부 버튼 이름은 번역한 것입니다.

저장한 사진에는 "白 済", "青 済" 표시가 붙어서 어떤 사진을 처리했는지 바로 알 수 있습니다.

---

## 설치 방법

1. [Releases](https://github.com/Connectan/Xperia-Watermark-For-Zeiss/releases/latest)에서 APK 다운로드
2. 다운로드한 APK를 탭
3. "출처를 알 수 없는 앱" 허용을 요청하면 브라우저(또는 파일 앱)의 **이 출처 허용** 을 켭니다
4. "설치"를 누릅니다

> Google Play 외부에서 설치하는 것이라 Play 프로텍트 경고가 나올 수 있습니다. 그럴 때는 "세부정보" → "무시하고 설치"로 진행해 주세요.

---

## 동작 환경

| 항목 | 내용 |
|---|---|
| Android | **7.0 이상**(API 24+) |
| 타깃 | Android 16(API 36) |
| CPU | arm64-v8a / armeabi-v7a / x86 / x86_64 |
| 사진 | ZEISS 탑재 Xperia로 찍은 JPEG(EXIF 포함) |

---

## 사용하는 권한

| 권한 | 용도 |
|---|---|
| 사진 및 동영상(`READ_MEDIA_IMAGES`) | 기기 안의 사진을 찾아 워터마크를 넣기 위해(Android 13 이상) |
| 저장소 읽기(`READ_EXTERNAL_STORAGE`) | 위와 같음(Android 12 이하) |
| 저장소 쓰기(`WRITE_EXTERNAL_STORAGE`) | 워터마크를 넣은 이미지를 저장하기 위해(Android 9 이하) |
| 인터넷(`INTERNET` 등) | 앱에 포함된 라이브러리가 선언한 것 |

워터마크는 기기 안에서(Android의 Canvas로) 그립니다.

---

## 자주 묻는 질문

**Q. 사진이 목록에 나오지 않아요**
A. ZEISS 탑재 Xperia 이외의 기기로 찍은 사진이나 EXIF(촬영 정보)가 지워진 사진은 나오지 않습니다. SNS에서 저장한 이미지나 편집 앱에서 내보낸 이미지는 EXIF가 지워져 있는 경우가 많습니다.

**Q. 원본 사진이 덮어쓰기 되나요?**
A. 아닙니다. 워터마크를 넣은 이미지는 **별도 파일로** 저장됩니다.

**Q. SD 카드에 저장이 안 돼요**
A. SD 카드가 없거나 인식되지 않을 때는 "本体ストレージ (SD未検出)"(내장 저장소, SD 미검출)로 표시되고 내장 저장소에 저장됩니다.

**Q. 같은 사진을 한 번 더 처리하고 싶어요**
A. "済"(완료) 표시가 붙은 사진도 다시 선택하면 **다시 저장** 할 수 있습니다.

**Q. 다른 `com.example` 앱과 함께 설치할 수 없어요**
A. 샘플 상태라서 패키지명이 `com.example`로 되어 있습니다. 같은 패키지명의 앱이 이미 설치되어 있으면 덮어쓰거나 충돌할 수 있습니다.

---

## 만든 사람

**こねくたん(Connectan)**, 晓玲 清風
- 사이트: https://connectan.github.io

일본 미인증 중국폰 늪의 주민.

---

## 주의

- "Xperia"는 Sony Group Corporation의, "ZEISS"는 Carl Zeiss AG의 상표입니다.
- 이 앱은 **개인이 만든 비공식 앱** 이며 Sony·ZEISS와는 관계가 없습니다.
- 사용은 본인 책임입니다.
