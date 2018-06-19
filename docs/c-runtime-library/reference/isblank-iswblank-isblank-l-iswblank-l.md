---
title: isblank、iswblank、_isblank_l、_iswblank_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs:
- C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2787be85aa4e12bf22d1be14f90568891b83824
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403314"
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank、iswblank、_isblank_l、_iswblank_l

整数が空白文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
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

これらのルーチンを返す場合は 0 以外の各*c*空白文字または水平タブ文字の特殊表現またはテキスト行内で単語を区切るために使用される文字のロケール固有の一連の 1 つです。 **isblank**場合は 0 以外の値を返します*c*は空白文字 (0x20) または水平タブ文字 (0x09)。 テスト条件の結果、 **isblank**関数によって異なります、 **LC_CTYPE**カテゴリ; 詳細については、ロケールの設定、表示[setlocale、_wsetlocale](setlocale-wsetlocale.md). これらの関数がないバージョン、 **_l**サフィックスを使用してすべてのロケールに依存する動作に現在のロケール以外の付いているバージョン、 **_l**使用する点を除いて、サフィックスが同一で、代わりに渡されるロケールです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**iswblank**場合は 0 以外の値を返します*c*が標準的な場所に対応するワイド文字または水平タブ文字です。

動作**isblank**と **_isblank_l**場合に定義されていない*c* EOF ではありませんか 0 ~ 0 xff、包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、これらの値、関数の発生いない 1 つです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isblank**|\<ctype.h>|
|**iswblank**|\<ctype.h> または \<wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
