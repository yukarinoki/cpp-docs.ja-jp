---
description: '詳細については、次を参照してください: _fcvt'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 4d2439c586ec28526849e956b1302c444cafa3a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235763"
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

*alpha*<br/>
格納された小数点位置を指すポインター。

*sign*<br/>
格納された符号インジケーターを指すポインター。

## <a name="return-value"></a>戻り値

**_fcvt** は、数字の文字列へのポインターを返し、エラーの場合は **NULL** を返します。

## <a name="remarks"></a>解説

**_Fcvt** 関数は、浮動小数点数を null で終わる文字列に変換します。 *値* パラメーターは、変換される浮動小数点数です。 **_fcvt** は、 *値* の数字を文字列として格納し、null 文字 (' \ 0 ') を追加します。 *Count* パラメーターは、小数点の後に格納する桁数を指定します。 余分な数字は、 *カウント* するために丸められます。 有効桁数が *カウント* よりも小さい場合は、文字列に0が埋め込まれます。

**_Fcvt** によって返された合計桁数が **_CVTBUFSIZE** を超えてはなりません。

文字列には数字だけが格納されます。 小数点の位置と *値* の符号は *dec* から取得でき、呼び出しの後に符号を付けます。 *Dec* パラメーターは整数値を指します。この整数値は、文字列の先頭に対する小数点の位置を示します。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 パラメーター *sign* は、 *値* の符号を示す整数を指します。 Value が正で、*値* が負の場合は0以外の値に設定されて *いる場合、* 整数は0に設定されます。

**_Ecvt** と **_fcvt** の違いは、 *count* パラメーターの解釈です。 **_ecvt** は、 *カウント* を出力文字列の合計桁数として解釈しますが、 **_fcvt** は小数点の後の桁数 *として解釈し* ます。

**_ecvt** と **_fcvt** は、静的に割り当てられた1つのバッファーを使用して変換を行います。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

この関数は、パラメーターを検証します。 *Dec* または *sign* が **NULL** の場合、または *count* が0の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno** は **EINVAL** に設定され、 **NULL** が返されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

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
[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
