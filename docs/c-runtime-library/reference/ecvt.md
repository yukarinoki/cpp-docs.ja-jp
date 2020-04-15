---
title: _ecvt
ms.date: 4/2/2020
api_name:
- _ecvt
- _o__ecvt
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 5e1760d5c68e650f6fbf44866d4e368b9d6233b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348025"
---
# <a name="_ecvt"></a>_ecvt

**倍**数を文字列に変換します。 この関数のセキュリティが強化されたバージョンについては、「[_ecvt_s](ecvt-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
変換される数値。

*count*<br/>
格納する桁数。

*12 月*<br/>
格納された小数点位置。

*署名*<br/>
変換後の数値の符号。

## <a name="return-value"></a>戻り値

**_ecvt**は、数字の文字列へのポインタを返します。エラーが発生した場合は**NULL。**

## <a name="remarks"></a>解説

**_ecvt**関数は、浮動小数点数を文字列に変換します。 *value*パラメーターは、変換される浮動小数点数です。 この関数は、*最大で値*の*桁数*を文字列として格納し、null 文字 ('\0') を追加します。 *値*の桁数が*count*を超える場合、下位桁は丸められます。 *カウント*桁数より少ない場合、文字列はゼロで埋め込まれます。

**_ecvt**によって返される桁数の合計は **、_CVTBUFSIZE**を超えない。

文字列には数字だけが格納されます。 小数点の位置と*値*の符号は、コール後の*dec*と*sign*から取得できます。 *dec*パラメータは、文字列の先頭を基準にして小数点の位置を示す整数値を指します。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 *符号*パラメーターは、変換された数値の符号を示す整数を指します。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。

**_ecvt**と **_fcvt**の違いは、*カウント*パラメータの解釈にあります。 **_ecvt**は *、カウント*を出力文字列の合計桁数として解釈しますが **、_fcvt**はカウントを小数点以下の*桁数として解釈*します。

**_ecvt**と **_fcvt**変換に 1 つの静的に割り当てられたバッファーを使用します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 *dec*または*sign*が**NULL**の場合、または*count*が 0 の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され **、NULL**が戻されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
