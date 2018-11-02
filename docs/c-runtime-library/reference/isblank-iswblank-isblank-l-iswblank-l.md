---
title: isblank、iswblank、_isblank_l、_iswblank_l
ms.date: 11/04/2016
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
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: eb088c4056e2277e188d7f98a57dd36216d013ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497319"
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

これらのルーチンを返します。 0 以外の場合の各*c*が特定の表現の空白文字または水平タブ文字、またはテキスト行内で単語を分離するために使用される文字のロケール固有の一連の 1 つです。 **isblank**場合は、0 以外の値を返します*c*は空白文字 (0x20) または水平タブ文字 (0x09)。 テスト条件の結果、 **isblank**関数によって異なります、 **LC_CTYPE**カテゴリの詳細については、ロケールの設定、表示[setlocale、_wsetlocale](setlocale-wsetlocale.md). これらの関数バージョンがない、 **_l** 、ロケールに依存する動作の現在のロケールのサフィックス使用; が付いているバージョン、 **_l**を使用する点を除いて、サフィックスと同じですが、代わりに渡されるロケールです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**iswblank**場合は、0 以外の値を返します*c*が標準的な場所に対応するワイド文字または水平タブ文字。

動作**isblank**と **_isblank_l**場合は定義されません*c* EOF がないか 0 ~ 0 xff の包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、発生のこれらの値のいずれかにありません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
