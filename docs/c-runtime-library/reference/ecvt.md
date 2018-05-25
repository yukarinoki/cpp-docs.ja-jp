---
title: _ecvt | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63514db5abe0a7cd531590dd419aa4b5931e7729
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="ecvt"></a>_ecvt

変換、**二重**数値を文字列にします。 この関数のセキュリティが強化されたバージョンについては、「[_ecvt_s](ecvt-s.md)」をご覧ください。

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

*値*<br/>
変換される数値。

*count*<br/>
格納する桁数。

*dec*<br/>
格納された小数点位置。

*sign*<br/>
変換後の数値の符号。

## <a name="return-value"></a>戻り値

**_ecvt**桁の文字列へのポインターを返します**NULL**場合はエラーが発生しました。

## <a name="remarks"></a>コメント

**_Ecvt**関数が文字の文字列に浮動小数点数値を変換します。 *値*パラメーターは変換する浮動小数点数。 この関数は最大格納*カウント*の桁*値*を文字列として null 文字 ('\0') を追加するとします。 場合の桁数*値*を超えています*カウント*下位の桁は丸められます。 も少ない場合*カウント*数字、文字列はゼロで埋められます。

によって返される総桁数 **_ecvt**を超えない **_CVTBUFSIZE**です。

文字列には数字だけが格納されます。 小数点の記号の位置*値*から取得できます*dec*と*記号*呼び出しの後です。 *Dec*パラメーターは、文字列の先頭に対する、小数点の位置を示す整数値を指します。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 *記号*パラメーターを変換後の数値の符号を示す整数をポイントします。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。

違い **_ecvt**と **_fcvt**の解釈時に、*カウント*パラメーター。 **_ecvt**解釈*カウント*として出力文字列に数字の合計数が **_fcvt**解釈*カウント*後に数字の数として、10 進数のポイント。

**_ecvt**と **_fcvt**変換に 1 つの静的に割り当てられたバッファーを使用します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 場合*dec*または*記号*は**NULL**、または*カウント*が 0 の無効なパラメーター ハンドラーが呼び出されます」の説明に従って場合、[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**と**NULL**が返されます。

## <a name="requirements"></a>要件

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
