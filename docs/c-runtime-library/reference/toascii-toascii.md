---
title: toascii、__toascii
ms.date: 11/04/2016
apiname:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 22f76bdbdb21eb5b3cc9a226c111e321ee2fd0ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578972"
---
# <a name="toascii-toascii"></a>toascii、__toascii

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

**_ _toascii**の値に変換*c*を 7 ビット ASCII の範囲し、結果を返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>Remarks

**_ _Toascii**ルーチンの下位 7 ビットに切り捨てることで、ASCII 文字に、特定の文字を変換します。 その他の変換は適用されません。

**_ _Toascii**プリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、ルーチンがマクロとして定義されます。 旧バージョンと互換性のため、 **toascii**はマクロとして定義されている場合にのみ[ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md)が定義されていないか 0 として定義されてそれ以外の場合、定義されていません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**toascii**、 **_ _toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

**Toascii**マクロは POSIX の拡張機能、および **_ _toascii**は POSIX 拡張機能の Microsoft 固有の実装です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[to 系関数](../../c-runtime-library/to-functions.md)<br/>
