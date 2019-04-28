---
title: _ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l
ms.date: 11/04/2016
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
ms.openlocfilehash: d2a5d0336e5ed4ad8bbb19f8a259128ab33d004e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286734"
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l

**コード ページ 932 固有の関数**

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _ismbchira(
   unsigned int c
);
int _ismbchira_l(
   unsigned int c,
   _locale_t locale
);
int _ismbckata(
   unsigned int c
);
int _ismbckata_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 場合*c* < = 255 は、対応する **_ismbb 系**ルーチン (たとえば、 **_ismbcalnum**に対応する **_ismbbalnum**)、結果は、戻り値に対応する **_ismbb 系**ルーチン。

## <a name="remarks"></a>Remarks

これらの各関数は特定の条件で特定のマルチバイト文字をテストします。

これらの関数のバージョン、 **_l**ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用することを除き、サフィックスは同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

|ルーチンによって返される値|テスト条件 (コード ページ 932 のみ)|
|-------------|-------------------------------------------|
|**_ismbchira**|2 バイトひらがな: 0x829F < =*c*< = 0x82F1。|
|**_ismbchira_l**|2 バイトひらがな: 0x829F < =*c*< = 0x82F1。|
|**_ismbckata**|2 バイトカタカナ: 0x8340 < =*c*< = 0x8396。|
|**_ismbckata_l**|2 バイトカタカナ: 0x8340 < =*c*< = 0x8396。|

**コード ページ 932 固有情報終了**

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ismbchira**|\<mbstring.h>|
|**_ismbchira_l**|\<mbstring.h>|
|**_ismbckata**|\<mbstring.h>|
|**_ismbckata_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
