---
title: _getw
ms.date: 4/2/2020
api_name:
- _getw
- _o__getw
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: eddb68ae6108c8a66966472cebca60a9969b78d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344162"
---
# <a name="_getw"></a>_getw

ストリームから整数を取得します。

## <a name="syntax"></a>構文

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**_getw**は、読み取られた整数値を返します。 **EOF**の戻り値は、エラーまたはファイルの終わりを示します。 ただし **、EOF**値は正規の整数値でもあるので **、feof**または**ferror**を使用してファイルの終わりまたはエラー状態を確認してください。 *stream*が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され、関数は**EOF**を返します。

## <a name="remarks"></a>解説

**_getw**関数は *、ストリーム*に関連付けられたファイルから**int**型の次のバイナリ値を読み取り、関連付けられたファイル ポインタ (存在する場合) をインクリメントして、次の未読文字を指します。 **_getw**ストリーム内の項目の特別な配置を想定していません。 _getwでの移植の問題は **、int**型のサイズと**int**型内のバイトの順序がシステムによって異**なるため、** 発生する可能性があります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crt_getwtxt"></a>入力: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
