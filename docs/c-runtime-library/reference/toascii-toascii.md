---
description: 詳細については、「toascii」、「__toascii」を参照してください。
title: toascii、__toascii
ms.date: 11/04/2016
api_name:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 9f1718da5e7d701bb6cc6ea68c1e21b6fe4283f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318352"
---
# <a name="toascii-__toascii"></a>toascii、__toascii

切り捨てにより文字を 7 ビット ASCII に変換します。

## <a name="syntax"></a>構文

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>パラメーター

*c*<br/>
変換する文字。

## <a name="return-value"></a>戻り値

**__toascii** *c* の値を7ビット ASCII の範囲に変換し、その結果を返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>解説

**__Toascii** ルーチンは、指定された文字を下位7ビットに切り捨てることによって、ASCII 文字に変換します。 その他の変換は適用されません。

**__Toascii** ルーチンは、プリプロセッサマクロ _CTYPE_DISABLE_MACROS が定義されていない限り、マクロとして定義されます。 旧バージョンとの互換性のために、 **toascii** はマクロとして定義されていますが、 [&#95;&#95;STDC&#95;&#95;](../../preprocessor/predefined-macros.md) が定義されていないか、0として定義されています。それ以外の場合は未定義です。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**toascii**、 **__toascii**|40u-c \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

**Toascii** マクロは posix 拡張機能であり、 **__toascii** は posix 拡張の Microsoft 固有の実装です。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[関数に](../../c-runtime-library/to-functions.md)<br/>
