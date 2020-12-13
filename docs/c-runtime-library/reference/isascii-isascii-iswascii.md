---
description: 詳細については、「isascii、__isascii、iswascii」を参照してください。
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0d0a7964ba5b9a3133f100ea94fd4bac95407627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332733"
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

*c*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、 **c** が ASCII 文字の特殊表現である場合は0以外の値を返します。 **c** が ASCII 文字 (0X00 から0x7f の範囲内) の場合、 **__isascii** は0以外の値を返します。 **c** が ASCII 文字のワイド文字表現である場合、 **iswascii** は0以外の値を返します。 これらの各ルーチンは、 **c** がテスト条件を満たしていない場合は0を返します。

## <a name="remarks"></a>解説

プリプロセッサマクロ _CTYPE_DISABLE_MACROS が定義されていない場合、 **__isascii** と **iswascii** の両方がマクロとして実装されます。

旧バージョンとの互換性のために、 **isascii** はマクロとしてのみ実装されます [&#95;&#95;STDC&#95;&#95;](../../preprocessor/predefined-macros.md) が定義されていないか、0として定義されている場合のみです。それ以外の場合は未定義です。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isascii**、 **__isascii**|40u-c \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|
|**iswascii**|C: \<wctype.h> 、 \<ctype.h> 、または \<wchar.h><br /><br /> C++: \<cwctype> 、 \<cctype> 、 \<wctype.h> 、 \<ctype.h> 、または \<wchar.h>|

**Isascii**、 **__isascii** および **iswascii** の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
