---
title: _putw
ms.date: 11/04/2016
apiname:
- _putw
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
- _putw
- putw
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
ms.openlocfilehash: 3fd18c2a8869d6b09703547f50ee6e096bd72395
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602684"
---
# <a name="putw"></a>_putw

ストリームに整数を書き込みます。

## <a name="syntax"></a>構文

```C
int _putw(
   int binint,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*binint*<br/>
出力されるバイナリ整数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

書き込まれた値を返します。 戻り値**EOF**エラーを示している可能性があります。 **EOF**は有効な整数値、使用でも**ferror**にエラーを確認します。 場合*ストリーム*null ポインターの場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**EOF**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**_Putw**関数は、型のバイナリ値を書き込みます**int**の現在位置に*ストリーム。* **_putw**ストリーム内の項目の配置には影響しませんも、その特殊な配置を想定しています。 **_putw**は主に以前のライブラリとの互換性。 移植性の問題が発生する可能性 **_putw**ためのサイズ、 **int**と内のバイトの順序付け、 **int**システム間で異なります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_putw**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_putw.c
/* This program uses _putw to write a
* word to a stream, then performs an error check.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   unsigned u;
   if( fopen_s( &stream, "data.out", "wb" ) )
      exit( 1 );
   for( u = 0; u < 10; u++ )
   {
      _putw( u + 0x2132, stream );   /* Write word to stream. */
      if( ferror( stream ) )         /* Make error check. */
      {
         printf( "_putw failed" );
         clearerr_s( stream );
         exit( 1 );
      }
   }
   printf( "Wrote ten words\n" );
   fclose( stream );
}
```

### <a name="output"></a>出力

```Output
Wrote ten words
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_getw](getw.md)<br/>
