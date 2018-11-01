---
title: isprint、iswprint、_isprint_l、_iswprint_l
ms.date: 11/04/2016
apiname:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
ms.openlocfilehash: 826bc825824054a5a6716f8074690f18a2c3f016
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556404"
---
# <a name="isprint-iswprint-isprintl-iswprintl"></a>isprint、iswprint、_isprint_l、_iswprint_l

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

*c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらのルーチンを返します。 0 以外の場合の各*c*印刷可能な文字の特定の表現です。 **isprint**場合は、0 以外の値を返します*c*が印刷可能な文字: 空白文字が含まれます (0x20 - 0x7E)。 **iswprint**場合は、0 以外の値を返します*c*が印刷できるワイド文字、空白ワイド文字が含まれます。 これらのルーチンの各場合 0 を返します*c*テスト条件を満たしていません。

これらの関数のテスト条件の結果によって異なります、 **LC_CTYPE**ロケールのカテゴリの設定; を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 これらの関数バージョンがない、 **_l** 、ロケールに依存する動作の現在のロケールのサフィックス使用; が付いているバージョン、 **_l**を使用する点を除いて、サフィックスと同じですが、代わりに渡されるロケールです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

動作**isprint**と **_isprint_l**場合は定義されません*c* EOF がないか 0 ~ 0 xff の包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、発生のこれらの値のいずれかにありません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_Unicode が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isprint**|\<ctype.h>|
|**iswprint**|\<ctype.h> または \<wchar.h>|
|**_isprint_l**|\<ctype.h>|
|**_iswprint_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
