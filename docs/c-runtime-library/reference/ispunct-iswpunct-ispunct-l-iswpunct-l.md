---
title: ispunct、iswpunct、_ispunct_l、_iswpunct_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
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
- iswpunct
- _istpunct
- ispunct
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9509270906de3f0a9c7a20fd5f126ecffcafcff0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402671"
---
# <a name="ispunct-iswpunct-ispunctl-iswpunctl"></a>ispunct、iswpunct、_ispunct_l、_iswpunct_l

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

*c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらのルーチンを返す場合は 0 以外の各*c*区切り文字の特定の表現です。 **ispunct**空白文字、または対象の文字は印刷可能な文字の 0 以外の値を返します**isalnum**は 0 以外。 **iswpunct**は、空白ワイド文字でも、ワイド文字を印刷可能なワイド文字の 0 以外の値を返します**iswalnum**は 0 以外。 これらの各ルーチン 0 を返します*c*テスト条件を満たしていません。

テスト条件の結果、 **ispunct**関数によって異なります、 **LC_CTYPE** 、ロケールのカテゴリの設定; 参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 これらの関数がないバージョン、 **_l**サフィックスを使用してすべてのロケールに依存する動作に現在のロケール以外の付いているバージョン、 **_l**使用する点を除いて、サフィックスが同一で、代わりに渡されるロケールです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

動作**ispunct**と **_ispunct_l**場合に定義されていない*c* EOF ではありませんか 0 ~ 0 xff、包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、これらの値、関数の発生いない 1 つです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ispunct**|\<ctype.h>|
|**iswpunct**|\<ctype.h> または \<wchar.h>|
|**_ispunct_l**|\<ctype.h>|
|**_iswpunct_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
