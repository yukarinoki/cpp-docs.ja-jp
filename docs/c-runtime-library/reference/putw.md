---
description: '詳細については、次を参照してください: _putw'
title: _putw
ms.date: 4/2/2020
api_name:
- _putw
- _o__putw
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putw
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
ms.openlocfilehash: e49240d7410f47042f515f310ba79f9a9eb38398
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146394"
---
# <a name="_putw"></a>_putw

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

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

書き込まれた値を返します。 **EOF** の戻り値は、エラーを示している可能性があります。 **EOF** も正当な整数値であるため、 **ferror** を使用してエラーを確認します。 *Stream* が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は **errno** を **EINVAL** に設定し、 **EOF** を返します。

これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Putw** 関数は、型のバイナリ値を **`int`** ストリームの現在位置に書き込み *ます。* **_putw** は、ストリーム内の項目の配置には影響しません。また、特別な配置を想定していません。 **_putw** は、主に以前のライブラリとの互換性を維持するためのものです。 のサイズ **`int`** と内のバイトの順序が **`int`** システム間で異なるため、_putw で移植性の問題が発生する可能性があります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_putw**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
