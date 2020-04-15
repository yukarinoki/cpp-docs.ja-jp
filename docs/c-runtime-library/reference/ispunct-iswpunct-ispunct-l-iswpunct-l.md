---
title: ispunct、iswpunct、_ispunct_l、_iswpunct_l
ms.date: 4/2/2020
api_name:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
- _o_ispunct
- _o_iswpunct
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswpunct
- _istpunct
- ispunct
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
ms.openlocfilehash: 3072f147d2adff2c50304d2d2052947ca32cb060
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342807"
---
# <a name="ispunct-iswpunct-_ispunct_l-_iswpunct_l"></a>ispunct、iswpunct、_ispunct_l、_iswpunct_l

整数が区切り文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int ispunct(
   int c
);
int iswpunct(
   wint_t c
);
int _ispunct_l(
   int c,
   _locale_t locale
);
int _iswpunct_l(
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

*c*が特定の句読点文字の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 **ispunct は**、空白文字でない、または**isalnum**が 0 以外の文字の印刷可能文字に対して、ゼロ以外の値を戻します。 **iswpunct は**、空白ワイド文字でも **、iswalnum**が 0 以外のワイド文字でもない印刷可能ワイド文字に対して、ゼロ以外の値を戻します。 c がテスト条件を満た*さない場合*、これらのルーチンはそれぞれ 0 を返します。

**ispunct**関数のテスト条件の結果は、ロケールの**LC_CTYPE**カテゴリ設定によって異なります。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) **_l**サフィックスを持たないこれらの関数のバージョンでは、ロケールに依存する動作に対して現在のロケールが使用されます。**_l**サフィックスを持つバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が EOF でない場合、または 0 から 0xFF の範囲内である場合 **、ispunct**および **_ispunct_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_****イストウント**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ispunct**|\<ctype.h>|
|**iswpunct**|\<ctype.h> または \<wchar.h>|
|**_ispunct_l**|\<ctype.h>|
|**_iswpunct_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
