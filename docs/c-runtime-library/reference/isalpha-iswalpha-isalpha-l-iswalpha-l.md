---
title: isalpha、iswalpha、_isalpha_l、_iswalpha_l
ms.date: 11/04/2016
apiname:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
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
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 47b7e43172884524e50e332dcb421e84a99b9806
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591751"
---
# <a name="isalpha-iswalpha-isalphal-iswalphal"></a>isalpha、iswalpha、_isalpha_l、_iswalpha_l

整数が英字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

*locale*<br/>
現在のロケールの代わりに使用するロケール。

## <a name="return-value"></a>戻り値

これらのルーチンを返します。 0 以外の場合の各*c*英文字の特定の表現です。 **isalpha**場合は、0 以外の値を返します*c*が A-Z または a-z の範囲内で。 **iswalpha**をワイド文字に対してのみ、0 以外の値を返します[iswupper](isupper-isupper-l-iswupper-iswupper-l.md)または**iswlower** 0 以外の場合以外は、すべての文字は実装定義セットのいずれかのどの**iswcntrl**、 **iswdigit**、 **iswpunct**、または**iswspace**が 0 以外。 これらのルーチンの各場合 0 を返します*c*テスト条件を満たしていません。

これらの関数がのバージョン、 **_l**サフィックスが、現在のロケールの代わりに渡されるロケール パラメーターを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

動作**isalpha**と **_isalpha_l**場合は定義されません*c* EOF がないか 0 ~ 0 xff の包括的な範囲内で。 CRT デバッグ ライブラリを使用する場合と*c*アサーションは、発生のこれらの値のいずれかにありません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> または \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
