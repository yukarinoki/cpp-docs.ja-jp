---
title: c16rtomb、c32rtomb1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- c16rtomb
- c32rtomb
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs:
- C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3282fb13e5b59ad3214c67410eef5186687114e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394545"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb、c32rtomb

UTF-16 または UTF-32 ワイド文字を現在のロケールのマルチバイト文字に変換します。

## <a name="syntax"></a>構文

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>パラメーター

*mbchar*<br/>
変換されたマルチバイト文字を格納する配列へのポインター。

*wchar*<br/>
変換するワイド文字。

*state*<br/>
ポインター、 **mbstate_t**オブジェクト。

## <a name="return-value"></a>戻り値

配列オブジェクトに格納されるバイト数*mbchar*、シフト シーケンスを含むです。 場合*wchar*は有効なワイド文字値はありません (**size_t**)(-1) が返されます、 **errno**に設定されている**EILSEQ**の値*状態*は指定されていません。

## <a name="remarks"></a>コメント

**C16rtomb**関数 utf-16 文字に変換*wchar*を現在のロケールで同等のマルチバイトのナロウ文字シーケンスです。 場合*mbchar*が null ポインター、配列オブジェクトに変換されたシーケンスを指す関数ストア*mbchar*です。 最大**MB_CUR_MAX**に格納されるバイト*mbchar*、および*状態*が結果として得られるシフト状態に設定します。    場合*wchar* null ワイド文字に必要なシーケンスは、初期のシフト状態が格納されている、必要な場合、復元後に、null 文字で、および*状態*が初期変換状態に設定します。 **C32rtomb**関数は同一ですが、utf-32 文字に変換します。

場合*mbchar* null ポインターでは、動作は同等の内部バッファーを置換する関数への呼び出しに*mbchar*とのワイド null 文字*wchar*です。

*状態*変換状態オブジェクトは、この関数とマルチバイト出力のシフト状態を維持するその他の再開可能な関数を続けて呼び出すことができます。 結果はへの呼び出しまたは再開可能なと再開不可能関数の使用を混在させた場合に定義されていない**setlocale、_wsetlocale**が再開可能な関数呼び出しの間で行われます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**c16rtomb**、 **c32rtomb**|C、C++: \<uchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16、mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
