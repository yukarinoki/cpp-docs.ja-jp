---
title: isascii、__isascii、iswascii
ms.date: 4/2/2020
api_name:
- iswascii
- __isascii
- _o_iswascii
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
ms.openlocfilehash: aeb9c27fee4d179cc16caa50c6f0aae521402beb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343921"
---
# <a name="isascii-__isascii-iswascii"></a>isascii、__isascii、iswascii

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

*C*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

**c**が ASCII 文字の特定の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 **__isascii****は、c**が ASCII 文字 (0x00 から 0x7F の範囲) の場合、ゼロ以外の値を返します。 **c**が ASCII 文字のワイド文字表現である場合 **、iswascii**はゼロ以外の値を戻します。 c がテスト条件を満た**さない場合**、これらのルーチンはそれぞれ 0 を返します。

## <a name="remarks"></a>解説

**__isascii**と**iswascii**は、プリプロセッサ マクロ _CTYPE_DISABLE_MACROSが定義されていない限り、マクロとして実装されます。

後方互換性のために **、ISASCII**はマクロとして実装されるのは[、stDC&#95;&#95;が](../../preprocessor/predefined-macros.md)定義されていないか、または 0 として定義されている場合&#95;&#95;だけです。それ以外の場合は未定義です。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isascii** **,__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|
|**iswascii**|C: \<wctype.h>、\<ctype.h>、または \<wchar.h><br /><br /> C++: \<cwctype>、\<cctype>、\<wctype.h>、\<ctype.h>、または \<wchar.h>|

**isascii** **、__isascii、** および**iswascii**関数は、マイクロソフト固有のものです。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
