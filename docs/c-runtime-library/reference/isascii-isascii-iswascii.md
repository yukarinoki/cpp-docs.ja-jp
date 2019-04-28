---
title: isascii、__isascii、iswascii
ms.date: 11/04/2016
apiname:
- iswascii
- __isascii
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
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
ms.openlocfilehash: d150e7bb335dc77ed86f445128eebf97b8be5ac3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287470"
---
# <a name="isascii-isascii-iswascii"></a>isascii、__isascii、iswascii

特定の文字が ASCII 文字かどうかを判断します。

## <a name="syntax"></a>構文

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

これらのルーチンを返します。 0 以外の場合の各**c** ASCII 文字の特定の表現です。 **_ _isascii**場合は、0 以外の値を返します**c** ASCII 文字 (範囲内で、0x00 から 0x7F)。 **iswascii**場合は、0 以外の値を返します**c** ASCII 文字のワイド文字表現です。 これらのルーチンの各場合 0 を返します**c**テスト条件を満たしていません。

## <a name="remarks"></a>Remarks

両方 **_ _isascii**と**iswascii**プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして実装されます。

旧バージョンと互換性のため、 **isascii**場合のみマクロとして実装されます[ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md)が定義されていないか 0 として定義されてそれ以外の場合、定義されていません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|
|**iswascii**|C: \<wctype.h>、\<ctype.h>、または \<wchar.h><br /><br /> C++: \<cwctype>、\<cctype>、\<wctype.h>、\<ctype.h>、または \<wchar.h>|

**Isascii**、 **_ _isascii**と**iswascii**関数は、Microsoft 固有の仕様。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
