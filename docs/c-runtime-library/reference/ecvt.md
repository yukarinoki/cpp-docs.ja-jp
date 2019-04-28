---
title: _ecvt
ms.date: 04/05/2018
apiname:
- _ecvt
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
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 36c9cb2e8cd9eb4dd67bb91e9e4dbd36d8d1fc8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288673"
---
# <a name="ecvt"></a>_ecvt

変換を**二重**数値を文字列にします。 この関数のセキュリティが強化されたバージョンについては、「[_ecvt_s](ecvt-s.md)」をご覧ください。

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

*dec*<br/>
格納された小数点位置。

*sign*<br/>
変換後の数値の符号。

## <a name="return-value"></a>戻り値

**_ecvt**桁の文字列へのポインターを返します**NULL**場合は、エラーが発生しました。

## <a name="remarks"></a>Remarks

**_Ecvt**関数は、浮動小数点数を文字の文字列に変換します。 *値*パラメーターは変換する浮動小数点数です。 この関数は最大格納*カウント*の桁*値*を文字列として null 文字 ('\0') を追加します。 場合の桁数*値*を超える*カウント*下位の桁は丸められます。 も少なかった場合*カウント*数字、文字列が 0 で埋められます。

によって返される総桁数 **_ecvt**が超えない **_CVTBUFSIZE**します。

文字列には数字だけが格納されます。 符号、小数点の位置*値*から取得できます*dec*と*サインオン*呼び出しの後にします。 *Dec*パラメーターが指す文字列の先頭に対する小数点の位置を示す整数値。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 *サインオン*パラメーターは変換後の数値の符号を示す整数を指します。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。

間の差 **_ecvt**と **_fcvt**の解釈には、*カウント*パラメーター。 **_ecvt**解釈*カウント*として、出力文字列に数字の合計数は **_fcvt**解釈*カウント*の後の桁数として、小数点 10 進数。

**_ecvt**と **_fcvt**変換に 1 つの静的に割り当てられたバッファーを使用します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 場合*dec*または*サインオン*は**NULL**、または*カウント*が 0 の場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**と**NULL**が返されます。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
