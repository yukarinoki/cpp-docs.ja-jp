---
title: toupper、_toupper、towupper、_toupper_l、_towupper_l
ms.date: 11/04/2016
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: 7e0ae3f1c69b0e5f77ea2ed8141a93867fd43b33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608892"
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper、_toupper、towupper、_toupper_l、_towupper_l

文字を大文字に変換します。

## <a name="syntax"></a>構文

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
変換する文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンのコピーを変換*c*、可能な場合、結果を返します。

場合*c*をワイド文字は、 **iswlower**が 0 以外の場合は、対応するワイド文字があると[iswupper](isupper-isupper-l-iswupper-iswupper-l.md) 0 以外の場合、 **towupper**は対応するワイド文字を返しますそれ以外の場合、 **towupper**返します*c*変更されません。

エラーを示す戻り値は予約されていません。

順序で**toupper**予想どおりの結果を[_ _isascii](isascii-isascii-iswascii.md)と[islower](islower-iswlower-islower-l-iswlower-l.md)がどちらも返す 0 以外の値。

## <a name="remarks"></a>Remarks

これらの各ルーチンは、変換が可能で適切な場合に、指定した小文字を適宜大文字に変換します。 大文字/小文字変換**towupper**ロケールに固有です。 現在のロケールに関連する文字の大文字/小文字のみが変換されます。 せず、関数、 **_l**サフィックスを使用して、現在設定されているロケール。 これらの関数のバージョン、 **_l**サフィックス ロケールをパラメーターとして受け取って現在設定されているのではなく使用するロケール。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

順序で**toupper**予想どおりの結果を[_ _isascii](isascii-isascii-iswascii.md)と[isupper](isupper-isupper-l-iswupper-iswupper-l.md)がどちらも返す 0 以外の値。

[データ変換ルーチン](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**変数**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l**と **_towupper_l**ロケールの依存関係はありません。 して直接呼び出すためのものではありません。 による内部使用に提供されます**変数**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[to 系関数](../../c-runtime-library/to-functions.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[to 系関数](../../c-runtime-library/to-functions.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
