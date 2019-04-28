---
title: _fcvt
ms.date: 04/05/2018
apiname:
- _fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: ae9323e3bb629fd61b35a8c844b00bfcc73235bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334841"
---
# <a name="fcvt"></a>_fcvt

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

*dec*<br/>
格納された小数点位置を指すポインター。

*sign*<br/>
格納された符号インジケーターを指すポインター。

## <a name="return-value"></a>戻り値

**_fcvt**桁の数字の文字列へのポインターを返します**NULL**エラーが発生します。

## <a name="remarks"></a>Remarks

**_Fcvt**関数は、浮動小数点数を文字の null で終わる文字列に変換します。 *値*パラメーターは変換する浮動小数点数です。 **_fcvt**の桁を格納*値*を文字列として null 文字 ('\0') を追加します。 *カウント*パラメーターは、小数点より後に格納される桁数を指定します。 余分な桁は丸め*カウント*を配置します。 も少なかった場合*カウント*桁の文字列、有効桁数が 0 で埋められます。

によって返される総桁数 **_fcvt**が超えない **_CVTBUFSIZE**します。

文字列には数字だけが格納されます。 符号、小数点の位置*値*から取得できます*dec*と呼び出しの後にサインオンします。 *Dec*パラメーターが指す整数値です。 この整数値では、文字列の先頭に対する小数点の位置。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 パラメーター*サインオン*の符号を示す整数を指す*値*します。 場合、整数は 0 に設定されて*値*が正の値および数値の場合は 0 以外の値に設定されている*値*が負の値。

間の差 **_ecvt**と **_fcvt**の解釈には、*カウント*パラメーター。 **_ecvt**解釈*カウント*として、出力文字列に数字の合計数は **_fcvt**解釈*カウント*の後の桁数として、小数点 10 進数。

**_ecvt**と **_fcvt**変換に 1 つの静的に割り当てられたバッファーを使用します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 場合*dec*または*サインオン*は**NULL**、または*カウント*が 0 の場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**と**NULL**が返されます。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
