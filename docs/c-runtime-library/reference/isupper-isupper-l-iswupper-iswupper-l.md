---
title: isupper、_isupper_l、iswupper、_iswupper_l
ms.date: 4/2/2020
api_name:
- isupper
- iswupper
- _iswupper_l
- _isupper_l
- _o_isupper
- _o_iswupper
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
- isupper
- _istupper
- iswupper
helpviewer_keywords:
- istupper function
- iswupper function
- isupper_l function
- _isupper_l function
- iswupper_l function
- _istupper function
- _iswupper_l function
- isupper function
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
ms.openlocfilehash: 713689649b33873796b7a73bad6a4ac6e8acc998
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342796"
---
# <a name="isupper-_isupper_l-iswupper-_iswupper_l"></a>isupper、_isupper_l、iswupper、_iswupper_l

整数が大文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isupper(
   int c
);
int _isupper_l (
   int c,
   _locale_t locale
);
int iswupper(
   wint_t c
);
int _iwsupper_l(
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

*c*が大文字の特定の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 *c が*大文字 (A から Z) の場合 **、isupper**は 0 以外の値を返します。 **iswupper**は *、c*が大文字に対応するワイド文字である場合、または*c*が実装で定義されたワイド文字のセットの 1 つで、iswcntrl、iswdigit、iswpunct、または**iswspace**が 0 以外の場合は、ゼロ以外の値を返します。 **iswcntrl** **iswdigit** **iswpunct** c がテスト条件を満た*さない場合*、これらのルーチンはそれぞれ 0 を返します。

**_l**サフィックスを持つこれらの関数のバージョンでは、ロケールに依存する動作の現在のロケールの代わりに渡されたロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が EOF でない場合、または 0 から 0xFF の範囲内である場合 **、isupper**および **_isupper_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istupper**|**isupper**|[_ismbcupper](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**イズウィッパー**|
|**_istupper_l**|**_isupper_l**|[_ismbclower、_ismbclower_l、_ismbcupper、 _ismbcupper_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_iswupper_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isupper**|\<ctype.h>|
|**_isupper_l**|\<ctype.h>|
|**イズウィッパー**|\<ctype.h> または \<wchar.h>|
|**_iswupper_l**|\<ctype.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
