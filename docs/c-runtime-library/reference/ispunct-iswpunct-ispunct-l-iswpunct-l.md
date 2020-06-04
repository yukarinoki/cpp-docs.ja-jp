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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d0585e9a80919c63dd9aa650dc1544e95569bc8b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916676"
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

*40u-c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、 *c*が区切り文字の特殊表現である場合は0以外の値を返します。 **ispunct**は、空白文字以外の印刷可能な文字または**isalnum**が0以外の文字に対して0以外の値を返します。 **iswpunct**は、空白ワイド文字でも、 **iswalnum**が0以外のワイド文字でもない、印刷可能なワイド文字に対して0以外の値を返します。 これらの各ルーチンは、 *c*がテスト条件を満たしていない場合は0を返します。

**Ispunct**関数のテスト条件の結果は、ロケールの**LC_CTYPE**カテゴリの設定によって異なります。詳細について[は、「setlocale、_wsetlocale](setlocale-wsetlocale.md) 」を参照してください。 **_L**サフィックスが付いていないこれらの関数のバージョンは、ロケールに依存する動作に現在のロケールを使用します。**_l**サフィックスが付いているバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*C*が EOF でない場合、または 0 ~ 0xff の範囲内にある場合、 **ispunct**と **_ispunct_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され、 *c*がこれらの値のいずれでもない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

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
[国](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
