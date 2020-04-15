---
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: a017ed58b962520793d5b10b088793dbc9b8a83d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347423"
---
# <a name="_fcvt"></a>_fcvt

浮動小数点数を文字列に変換します。 この関数のセキュリティが強化されたバージョンについては、「[_fcvt_s](fcvt-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_fcvt(
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
小数点以下の桁数。

*12 月*<br/>
格納された小数点位置を指すポインター。

*署名*<br/>
格納された符号インジケーターを指すポインター。

## <a name="return-value"></a>戻り値

**_fcvt**は、エラー時に**NULL**の数字の文字列へのポインターを返します。

## <a name="remarks"></a>解説

**_fcvt**関数は、浮動小数点数を NULL で終わる文字列に変換します。 *value*パラメーターは、変換される浮動小数点数です。 **_fcvt**は *、値*の数字を文字列として格納し、null 文字 ('\0') を追加します。 *count*パラメーターは、小数点の後に格納される桁数を指定します。 桁数が大きくなり、桁数が*丸*められます。 精度の*カウント*桁数より少ない場合、文字列はゼロで埋め込まれます。

**_fcvt**によって返される桁数の合計は **、_CVTBUFSIZE**を超えない。

文字列には数字だけが格納されます。 小数点の位置と*値*の符号は、コール後の*dec*とsignから取得できます。 *dec*パラメータは整数値を指します。この整数値は、文字列の先頭に対する小数点の位置を示します。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 パラメータ*記号*は *、値*の符号を示す整数を指します。 *値*が正の場合は 0 に設定され、*値*が負の場合は 0 以外の数値に設定されます。

**_ecvt**と **_fcvt**の違いは、*カウント*パラメータの解釈にあります。 **_ecvt**は *、カウント*を出力文字列の合計桁数として解釈しますが **、_fcvt**はカウントを小数点以下の*桁数として解釈*します。

**_ecvt**と **_fcvt**変換に 1 つの静的に割り当てられたバッファーを使用します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 *dec*または*sign*が**NULL**の場合、または*count*が 0 の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され **、NULL**が戻されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
