---
description: '詳細については、次を参照してください: tolower、_tolower、towlower、_tolower_l、_towlower_l'
title: tolower、_tolower、towlower、_tolower_l、_towlower_l
ms.date: 4/2/2020
api_name:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
- _o__tolower
- _o__tolower_l
- _o__towlower_l
- _o_tolower
- _o_towlower
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
ms.openlocfilehash: 5b686d9b511fe4864724f85be78ac511a6351ef7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318326"
---
# <a name="tolower-_tolower-towlower-_tolower_l-_towlower_l"></a>tolower、_tolower、towlower、_tolower_l、_towlower_l

文字を小文字に変換します。

## <a name="syntax"></a>構文

```C
int tolower(
   int c
);
int _tolower(
   int c
);
int towlower(
   wint_t c
);
int _tolower_l(
   int c,
   _locale_t locale
);
int _towlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
変換する文字。

*locale*<br/>
ロケール固有の変換に使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、変換が可能な場合は *c* のコピーを小文字に変換し、結果を返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>解説

これらの各ルーチンは、変換が可能で適切な場合に、指定した大文字を適宜小文字に変換します。 **Towlower** の大文字と小文字の変換は、ロケール固有です。 現在のロケールに関連する文字の大文字/小文字のみが変換されます。 **_L** サフィックスが付いていない関数は、現在設定されているロケールを使用します。 **_L** サフィックスを持つこれらの関数のバージョンは、ロケールをパラメーターとして受け取り、現在設定されているロケールの代わりにそれを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**_Tolower** が予期される結果を得るためには、 [__isascii](isascii-isascii-iswascii.md)と [isupper](isupper-isupper-l-iswupper-iswupper-l.md)の両方が0以外の値を返す必要があります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**tolower**|**_mbctolower**|**towlower**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** と **_towlower_l** はロケールに依存せず、直接呼び出すためのものではありません。 これらは、 **_totlower_l** によって内部で使用するために用意されています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**tolower**|\<ctype.h>|
|**_tolower**|\<ctype.h>|
|**towlower**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[to 系関数](../../c-runtime-library/to-functions.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[関数に](../../c-runtime-library/to-functions.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
