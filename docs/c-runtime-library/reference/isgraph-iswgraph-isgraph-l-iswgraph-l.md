---
title: isgraph、iswgraph、_isgraph_l、_iswgraph_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
- _isgraph_l
- _iswgraph_l
- _ismbcgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
dev_langs:
- C++
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b60e022471bdfa7cbbddb6b5263f757438572a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401273"
---
# <a name="isgraph-iswgraph-isgraphl-iswgraphl"></a>isgraph、iswgraph、_isgraph_l、_iswgraph_l

整数がグラフィカルな文字を表すかどうかを判定します。

## <a name="syntax"></a>構文

```C
int isgraph(
   int c
);
int iswgraph(
   wint_t c
);
int _isgraph_l(
   int c,
   _locale_t locale
);
int _iswgraph_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

これらのルーチンを返す場合は 0 以外の各*c*スペース以外印刷可能な文字の特定の表現です。 **isgraph**場合は 0 以外の値を返します*c*スペース以外印刷可能な文字です。 **iswgraph**場合は 0 以外の値を返します*c*ワイド文字のスペース以外印刷可能なワイド文字します。 これらの各ルーチン 0 を返します*c*テスト条件を満たしていません。

これらの関数を持つバージョン、 **_l**サフィックス、現在のロケールの代わりに、ロケールに依存する動作には、渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

動作**isgraph**と **_isgraph_l**場合に定義されていない*c* EOF ではありませんか 0 ~ 0 xff、包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、これらの値、関数の発生いない 1 つです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isgraph**|\<ctype.h>|
|**iswgraph**|\<ctype.h> または \<wchar.h>|
|**_isgraph_l**|\<ctype.h>|
|**_iswgraph_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
