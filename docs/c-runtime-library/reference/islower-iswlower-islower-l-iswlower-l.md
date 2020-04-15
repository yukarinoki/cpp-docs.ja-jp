---
title: islower、iswlower、_islower_l、_iswlower_l
ms.date: 4/2/2020
api_name:
- iswlower
- _islower_l
- islower
- _iswlower_l
- _o_islower
- _o_iswlower
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
- _istlower
- islower
- _ismbclower_l
- _liswlower_l
- _istlower_l
- _iswlower_l
- _islower _l
- _islower_l
- iswlower
helpviewer_keywords:
- _islower _l function
- _ismbclower_l function
- islower function
- _iswlower_l function
- _liswlower_l function
- _istlower_l function
- istlower function
- _istlower function
- iswlower function
- _islower_l function
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
ms.openlocfilehash: 64fbde1db738dda694a911557748f2b46b6d8af8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343795"
---
# <a name="islower-iswlower-_islower_l-_iswlower_l"></a>islower、iswlower、_islower_l、_iswlower_l

整数が小文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int islower(
   int c
);
int iswlower(
   wint_t c
);
int islower_l(
   int c,
   _locale_t locale
);
int _iswlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
テストする整数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*c*が小文字の特定の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 *c が*小文字 (a - z) の場合 **、islower**は 0 以外の値を返します。 **iswlower**は *、c*が小文字に対応するワイド文字である場合、または*c*が実装で定義されたワイド文字のセットの 1 つで、iswcntrl、iswdigit、iswpunct、または**iswspace**が 0 以外の場合は、ゼロ以外の値を返します。 **iswcntrl** **iswdigit** **iswpunct** c がテスト条件を満た*さない場合*、これらのルーチンはそれぞれ 0 を返します。

**_l**サフィックスを持つこれらの関数のバージョンでは、ロケールに依存する動作の現在のロケールの代わりに渡されたロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が EOF でない場合、または 0 から 0xFF の範囲内である場合 **、islower**および **_islower_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istlower**|**islower**|[_ismbclower](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**より低い**|
|**_istlower_l**|`_islower _l`|[_ismbclower_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_liswlower_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**islower**|\<ctype.h>|
|**より低い**|\<ctype.h> または \<wchar.h>|
|**_islower_l**|\<ctype.h>|
|**_swlower_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
