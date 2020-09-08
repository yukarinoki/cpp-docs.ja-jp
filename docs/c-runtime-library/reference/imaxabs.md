---
title: imaxabs
description: Imaxabs の API リファレンス。任意のサイズの整数の絶対値を計算します。
ms.date: 04/05/2018
api_name:
- imaxabs
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- imaxabs
helpviewer_keywords:
- imaxabs function
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
ms.openlocfilehash: 599e8a0cb20f24bda24201be40fa1acc0ade993c
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555502"
---
# <a name="imaxabs"></a>imaxabs

任意のサイズの整数の絶対値を計算します。

## <a name="syntax"></a>構文

```C
intmax_t imaxabs(
   intmax_t n
);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数値。

## <a name="return-value"></a>戻り値

**Imaxabs**関数は、引数の絶対値を返します。 エラーの戻り値はありません。

> [!NOTE]
> **Intmax_t**を使用して表すことができる負の整数の範囲は、表すことができる正の整数の範囲より大きいため、変換できない引数を**imaxabs**に渡すことができます。 引数の絶対値を戻り値の型で表すことができない場合、 **imaxabs** の動作は未定義になります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**imaxabs**|\<inttypes.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_imaxabs.c
// Build using: cl /W3 /Tc crt_imaxabs.c
// This example calls imaxabs to compute an
// absolute value, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x = LLONG_MIN + 2;

   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));
}
```

```Output
The absolute value of -9223372036854775806 is 9223372036854775806
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
