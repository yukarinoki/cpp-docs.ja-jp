---
description: '詳細については、次を参照してください: _ecvt'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9226ac29827db8d412a1266eeba1ccd2b889e2ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332858"
---
# <a name="_ecvt"></a>_ecvt

数値を **`double`** 文字列に変換します。 この関数のセキュリティが強化されたバージョンについては、「[_ecvt_s](ecvt-s.md)」をご覧ください。

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

*alpha*<br/>
格納された小数点位置。

*sign*<br/>
変換後の数値の符号。

## <a name="return-value"></a>戻り値

**_ecvt** は、数字の文字列へのポインターを返します。エラーが発生した場合は **NULL** です。

## <a name="remarks"></a>解説

**_Ecvt** 関数は、浮動小数点数を文字列に変換します。 *値* パラメーターは、変換される浮動小数点数です。 この関数は、最大 *数* の *値* を文字列として格納し、null 文字 (' \ 0 ') を追加します。 [ *値* ] の桁数が *count* を超えている場合は、下位の桁が丸められます。 *Count* の桁数よりも小さい場合は、文字列に0が埋め込まれます。

**_Ecvt** によって返された合計桁数が **_CVTBUFSIZE** を超えてはなりません。

文字列には数字だけが格納されます。 小数点の位置と *値* の符号は *dec* から取得でき、呼び出しの後に *符号* を付けます。 *Dec* パラメーターは、文字列の先頭に対する小数点の位置を示す整数値を指します。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 *Sign* パラメーターは、変換後の数値の符号を示す整数を指します。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。

**_Ecvt** と **_fcvt** の違いは、 *count* パラメーターの解釈です。 **_ecvt** は、 *カウント* を出力文字列の合計桁数として解釈しますが、 **_fcvt** は小数点の後の桁数 *として解釈し* ます。

**_ecvt** と **_fcvt** は、静的に割り当てられた1つのバッファーを使用して変換を行います。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 *Dec* または *sign* が **NULL** の場合、または *count* が0の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno** は **EINVAL** に設定され、 **NULL** が返されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

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
[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
