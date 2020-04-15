---
title: isprint、iswprint、_isprint_l、_iswprint_l
ms.date: 4/2/2020
api_name:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
- _o_isprint
- _o_iswprint
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
- iswprint
- _istprint
- isprint
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
ms.openlocfilehash: f09168e8e010fb59d748c109d4a41c533318e2eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342894"
---
# <a name="isprint-iswprint-_isprint_l-_iswprint_l"></a>isprint、iswprint、_isprint_l、_iswprint_l

整数が印刷可能な文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
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

*c*が印刷可能文字の特定の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 **isprint**は *、c*が印刷可能文字である場合は 0 以外の値を返します。 *c が*印刷可能なワイド文字である場合 **、iswprint**は 0 以外の値を返します。 c がテスト条件を満た*さない場合*、これらのルーチンはそれぞれ 0 を返します。

これらの関数のテスト条件の結果は、ロケールの**LC_CTYPE**カテゴリ設定によって異なります。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) **_l**サフィックスを持たないこれらの関数のバージョンでは、ロケールに依存する動作に対して現在のロケールが使用されます。**_l**サフィックスを持つバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が EOF でない場合、または 0 から 0xFF の範囲内である場合 **、isprint**および **_isprint_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_Unicode が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_****イストプリント**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isprint**|\<ctype.h>|
|**iswprint**|\<ctype.h> または \<wchar.h>|
|**_isprint_l**|\<ctype.h>|
|**_iswprint_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
