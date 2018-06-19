---
title: toascii、__toascii | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead516a7e298e56d13d8f1a09a054057796ca64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408423"
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

**_ _toascii**の値を変換*c*を 7 ビット ASCII の範囲し、結果を返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>コメント

**_ _Toascii**ルーチン下位 7 ビットを切り捨てて ASCII 文字に指定された文字を変換します。 その他の変換は適用されません。

**_ _Toascii**ルーチンはプリプロセッサ マクロ _CTYPE_DISABLE_MACROS が定義されていない場合、マクロとして定義します。 旧バージョンと互換性のため、 **toascii**マクロとして定義される場合にのみ[ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md)が定義されていないか、0 として定義されてそれ以外の場合は定義されません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**toascii**、 **_ _toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> または \<ctype.h>|

**Toascii**マクロは POSIX の拡張機能、および **_ _toascii** POSIX 拡張機能の Microsoft 固有実装です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
[to 系関数](../../c-runtime-library/to-functions.md)<br/>
