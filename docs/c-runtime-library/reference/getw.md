---
title: _getw
ms.date: 11/04/2016
apiname:
- _getw
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: 615d3ac9bdc73ad200368eaeabf7c84951bc91ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487608"
---
# <a name="getw"></a>_getw

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

**_getw**読み取られた整数値を返します。 戻り値**EOF**エラーまたはファイルの末尾のいずれかを示します。 ただし、ため、 **EOF**値も有効な整数値を使用して**feof**または**ferror**ファイルの終端またはエラー条件を確認します。 場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**EOF**します。

## <a name="remarks"></a>Remarks

**_Getw**関数は次のような種類のバイナリ値を読み取ります**int**に関連付けられているファイルから*ストリーム*ポイントに関連付けられたファイル ポインター (存在する場合) をインクリメントして次の未読文字。 **_getw**ストリーム内の項目の特殊な配置を想定しません。 移植の問題が発生する **_getw**ためのサイズ、 **int**型と内のバイトの順序付け、 **int**システム間で型が異なります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

### <a name="input-crtgetwtxt"></a>入力: crt_getw.txt

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
