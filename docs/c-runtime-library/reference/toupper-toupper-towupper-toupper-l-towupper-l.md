---
title: toupper、_toupper、towupper、_toupper_l、_towupper_l
ms.date: 4/2/2020
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
- _o__toupper
- _o__toupper_l
- _o__towupper_l
- _o_toupper
- _o_towupper
api_location:
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 85c218fdb3f5153e572e434bffbdb64510554d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362324"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper、_toupper、towupper、_toupper_l、_towupper_l

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

*C*<br/>
変換する文字。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、可能であれば*c*のコピーを変換し、結果を返します。

*c*がワイド文字で **、iswlower**が 0 以外の場合[、iswupper](isupper-isupper-l-iswupper-iswupper-l.md)がゼロ以外のワイド文字が対応している場合 **、towupper**は対応するワイド文字を返します。それ以外**の場合は、towupper**は*c*を変更せずに返します。

エラーを示す戻り値は予約されていません。

**toupper が**期待した結果を得るためには[、__isascii](isascii-isascii-iswascii.md)と[islower の両方が](islower-iswlower-islower-l-iswlower-l.md)0 以外を返さなければなりません。

## <a name="remarks"></a>解説

これらの各ルーチンは、変換が可能で適切な場合に、指定した小文字を適宜大文字に変換します。 **towupper**の大文字と小文字の変換はロケールに固有です。 現在のロケールに関連する文字の大文字/小文字のみが変換されます。 **_l**サフィックスを持たない関数は、現在設定されているロケールを使用します。 **_l**サフィックスを持つこれらの関数のバージョンは、ロケールをパラメーターとして受け取り、現在設定されているロケールの代わりにそれを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**toupper が**期待した結果を得るためには[、__isascii](isascii-isascii-iswascii.md)と[夕食の](isupper-isupper-l-iswupper-iswupper-l.md)両方がゼロ以外を返さなければなりません。

[データ変換ルーチン](../../c-runtime-library/data-conversion.md)

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**Toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l**と **_towupper_l**はロケール依存性を持たないため、直接呼び出されるものではありません。 これらは **、_totupper_l**によって内部使用のために提供されています。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**Toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[to 系関数](../../c-runtime-library/to-functions.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[to 系関数](../../c-runtime-library/to-functions.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
