---
title: islower、iswlower、_islower_l、_iswlower_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- iswlower
- _islower_l
- islower
- _iswlower_l
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
- _istlower
- islower
- _ismbclower_l
- _liswlower_l
- _istlower_l
- _iswlower_l
- _islower _l
- _islower_l
- iswlower
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14fb6eae9e06e973413c21607f2ca2881f33aa38
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401832"
---
# <a name="islower-iswlower-islowerl-iswlowerl"></a>islower、iswlower、_islower_l、_iswlower_l

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

*c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらのルーチンを返す場合は 0 以外の各*c*小文字の特定の表現です。 **islower**場合は 0 以外の値を返します*c*小文字 (a ~ z)。 **iswlower**場合は 0 以外の値を返します*c*英小文字に対応するワイド文字または*c* のワイド文字、実装定義セットの1つです**iswcntrl**、 **iswdigit**、 **iswpunct**、または**iswspace**は 0 以外。 これらの各ルーチン 0 を返します*c*テスト条件を満たしていません。

これらの関数を持つバージョン、 **_l**サフィックス、現在のロケールの代わりに、ロケールに依存する動作には、渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

動作**islower**と **_islower_l**場合に定義されていない*c* EOF ではありませんか 0 ~ 0 xff、包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、これらの値、関数の発生いない 1 つです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istlower**|**islower**|[_ismbclower](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**iswlower**|
|**_istlower_l**|`_islower _l`|[_ismbclower_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_liswlower_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**islower**|\<ctype.h>|
|**iswlower**|\<ctype.h> または \<wchar.h>|
|**_islower_l**|\<ctype.h>|
|**_swlower_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
